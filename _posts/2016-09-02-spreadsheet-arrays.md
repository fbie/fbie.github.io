---
title: Cell Arrays in Spreadsheets
layout: post
---

## From the series "Notes to my future self:" ##

During my stay at the Institute of Software at the Chinese Academy of Sciences (CAS) in Beijing, I met Wensheng Dou, who is working on analysis of errors and "smells" in spreadsheets. He has given me access to his research and his most recent paper ["CACheck: Detecting and Repairing Cell Arrays in Spreadsheets"](dx.doi.org/10.1145/1117389.1117401) makes some very interesting observations about usage of array-like computations in spreadsheets.

Dou et al. investigated how arrays are used in the EUSES and Enron spreadsheet corpora, and found that 55.1% of all the spreadsheets use *well-formed* cell arrays (they define well-formedness of cell arrays in their paper). This is an interesting finding, because if half of all spreadsheet use cell arrays in some way, my work on spreadsheet array programming is well motivated. Furthermore, they observe that the EUSES and Enron spreadsheet corpora independently from each other have comparable percentages of inhomogeneous cell arrays.

What is a cell array? Dou et al.'s definition (slightly simplified and paraphrased) is that a cell array is a row or column of contiguous cells that have the same semantics, never mind the syntax. This leaves out two-dimensional arrays (which are still counted as individual column or row cell arrays).

In their paper, Dou et al. make a certain distinction between two kinds of cell arrays: homogeneous cell arrays only reference cells that are part of the array; an inhomogeneous cell array also reference cells outside of itself. They found 21% of all cell arrays to be inhomogeneous and 79% to be homogeneous.

As a quick example, a homogeneous array looks like this:

```
1 | 1 | A1 + B1 | B1 + C1 | C1 + D1 | ... | [n-2]1 + [n-1]1
```

(The hypothetical ```[]``` operator translates numeric values to columns.)

There are many different interpretations possible. For instance, the above Fibonacci sequence could be implemented by using an array ```unfold``` operation. Other homogeneous cell arrays might be easily expressed as ```scan``` or ```prefixSum``` computations, or maybe using stencils.

This is an exciting opportunity. Using Dou et al.'s method to detect homogeneous and inhomogeneous arrays, we could implement a tool in Funcalc that proposes to convert a cell array into a real array computation. Such an array computation is much easier to maintain, can be implemented using e.g. quad ropes and other array programming techniques and therefore be computed faster.

## References ##

["Dou et al.: CACheck: Detecting and Repairing Cell Arrays in Spreadsheets"](dx.doi.org/10.1145/1117389.1117401)
