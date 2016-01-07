---
title: Systematic literature reviews using BibTeX and Emacs
layout: post
---

For my PhD project, I need to conduct a systematic literature
review. Systematic literature reviews apparently are a huge thing in
medicine and also now in software engineering. There is quite a lot of
literature on how to conduct systematic literature reviews in software
engineering, most prominently the *Guidelines for performing
Systematic Literature Reviews in Software Engineering* by
[Kitchenham et al.][kitchenham]

Such systematic reviews are performed to accumulate the fragmented
contributions and insights of single publications. This is helpful to
gain new knowledge which single publications due to their limited
scope may be unable to produce themselves. They also make literature
reviews reproducible and help to identify advances in certain fields
when repeated. Even though in my case, a systematic mapping study, the
little brother of systematic literature review, will do, it turns out
that this is an awful lot of manual labor.

## Finding Literature  ##

It all starts with accumulating the publications that should be part
of the review. An easy way to do so is using the search engines of
publication databases, such as [ACM's](http://dl.acm.org) or
[IEEE's](http://ieeexplore.ieee.org) digital library or meta-search
engines such as [Google Scholar](https://scholar.google.com) or
[CiteSeerX](http://citeseerx.ist.psu.edu).

We need to formulate a query using the respective search engine's
syntax. If we want to find publications on end-user development in
spreadsheets, we'd search ACM's digital library with a query like:

```
(spreadsheet or excel) AND (end-user-development OR "end user development" OR "end-user development")
```

We need to cover different styles of spelling the same commonly used
expressions as these search engines have no understanding of the
semantics of our query. This query returns 389 publications, all of
which contain the search query in one form or another. We need to
perform some quality assurance, either by comparing the results to a
list with key publications in our field that must also be included in
the results or by having an acknowledged expert in the field tell us
that the results are not biased.

Now the real work starts.

## Reviewing the Results ##

Of course, not all of the 389 found publications are relevant. The
next step therefore is to take a look at each one of them and decide
if they should become part of our review. This is boring and manual
labor: for each not-yet reviewed publication, read at least the
abstract to identify its relevance to your subject. Do this preferably
in a group of two or more people and keep those that the majority
accepts.

Using ACM's web-interface, this means that you have to click on each
article once, read its abstract and keep track which articles you want
to keep. There exists software that helps you doing so, but you still
need to synchronize between reviewers somehow and if you don't use
fancy software for this, then all data must be handled manually.

## SLIRM: Systematic Literature Review Mode for Emacs ##

This seems too much of an overhead, I thought, so I spent two weeks
writing a systematic literature review mode for Emacs, short SLIRM. It
works on plain BibTeX files, performs user-based review annotations
and, because everything remains in plain text, can be synchronized
e.g. via Git. It also automatically downloads the abstract and on
demand also the full text from the corresponding web site, if
available.

Currently, you need to open the BibTeX file you want to process with
SLIRM in Emacs and then run ```slirm-start``` from within the
buffer. You'll be shown the first entry not yet reviewed by you. You
can add your review by pressing ```SPC``` or navigate back and forth
between entries by pressing ```n``` or ```p``` for next and
previous. You can also navigate to the next not yet reviewed entry via
```C-n``` or to the first not yet reviewed entry via ```C-f```.

SLIRM is still under development and will remain so, I guess. A bunch
of features are still missing, like extracting all accepted entries to
a new BibTeX file, actually downloading and caching the full text PDF
or starting SLIRM with a path to a BibTeX file instead of opening it
manually. Also, navigation is far from complete, e.g. move to next
accepted or rejected entry.

You can keep track of the development or fork and improve
[SLIRM on GitHub][slirm].

## The Real Review ##

When you and your team are done reviewing the entries in your shared
BibTeX file, the real review starts, which you maybe can but probably
shouldn't automate. You must read, annotated and most importantly
understand the until now accepted publications, map them out and draw
conclusions from what you read. I do not know yet if you can or should
use SLIRM for that.

I will write more about my own experiences another time.

## Resources ##

- [Kitchenham: Guidelines for performing Systematic Literature Reviews in Software Engineering, Version 2.3][kitchenham]
- [SLIRM on GitHub][slirm]


[kitchenham]: http://www.cse.chalmers.se/~feldt/advice/kitchenham_2007_systematic_reviews_report_updated.pdf
[slirm]: https://github.com/fbie/slirm
