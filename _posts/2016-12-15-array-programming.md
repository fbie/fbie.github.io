---
title: Array Programming Basics
layout: post
---

It seems that I have consistently misjudged how much the average computer scientists knows about declarative array programming. This post is an attempt to figure out how to present these concepts in a concise way such that higher-order functions like ```map``` and ```scan``` are easily understood by everyone.

## Mapping a List ##

Let's start by defining a standard list type.

```
type 'a lst =
    | nil
	| cons 'a * 'a lst

let (::) = cons
```

Let's assume that things like function abstraction and application are in place. So here is a simple implementation of ```map``` on this list type.

```
let map f nil = nil
let map f (x :: xs) = (f x) :: (map f xs)
```

The function ```map``` lifts a function on scalars to operate on collections of values. Instead of projecting a scalar value to a new value, using it together with map projects *the entire collection* to a new list of values. Let us apply it:

```
map (fun x -> x) (1 :: 2 :: 3 :: nil) = 1 :: 2 :: 3 :: nil
map (fun x -> x * 2) (1 :: 2 :: 3 nil) = 2 :: 4 :: 6 :: nil
map (fun x -> x * x) (1 :: 2 :: 3 nil) = 1 :: 4 :: 9 :: nil
```

We can generalize this to combine two lists using a function ```f``` of type ```'a -> 'c -> 'c```:

```
let map2 f nil nil = nil
let map2 f (x :: xs) (y :: ys) = (f x y) :: (map2 f xs ys)
```

Here, we assume that both, ```xs``` and ```ys``` are of the same size -- which is actually the precondition for ```map2``` -- and omit the erroneous case where they differ in length.

```
map (+) (1 :: 2 :: 3 :: nil) (1 :: 2 :: 3 :: nil) = 2 :: 4 :: 6 :: nil
```

We can generalize further, if we want to, to...

## Reduction ##

Sometimes, we would like to aggregate a list of numbers to a single number by means of summation. This is a special case of reduction.

```
let reduce f v nil = v
let reduce f v (cons x xs) = reduce (f v x) xs
```

We can now implement summation by means of reduction:

```
let sum = reduce (+) 0
```

The ```reduce``` function is actually a special case of ```mapreduce```:

```
let mapreduce f g v nil = v
let mapreduce f g v (cons x xs) = mapreduce f g (g (f x) v) xs
```

And we can implement ```reduce``` from mapreduce by using the identity function:

```
let reduce' = mapreduce (fun x -> x)
```

We can use ```mapreduce``` to count the number of elements in the list:

```
let len = mapreduce (fun _ -> 1) (+) 0
```

## Prefix Computations -- Scan ##

There exists a function that is closely related to ```reduce```, which is ```scan```, a function that computes the prefix-sum of a list. We start with the output first:

```
scan (+) 0 (1 :: 2 :: 3 :: nil) = 1 :: 3 :: 6 :: nil
scan (*) 1 (1 :: 2 :: 3 :: nil) = 1 :: 2 :: 6 :: nil
```

The ```scan``` function performs a kind of reduce where it retains all intermediate values. Therefore, we could in principle implement ```reduce``` in terms of ```scan```, but that would be very inefficient, as the memory consummation is O(n) instead of constant.

Here is a simple definition:

```
let scan f v nil = nil
let scan f v (x :: xs) = let v' = (f v x) in (v') :: (scan f v' xs)
```

Amongst others, Guy Blelloch argues that ```scan```, or prefix-sum, is a basic building block of array programming.
