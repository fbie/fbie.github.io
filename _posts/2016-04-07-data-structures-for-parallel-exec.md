---
title: Guy Steele on Parallel Execution of Functional Code
layout: post
---

Last week I came across a talk from ICFP 2009 by Guy Steele of Sun Microsystems. He argues for using trees instead of linear, ```cons``` style data structures because trees are directly parallelizable. He also argues for high-level operations to abstract away the underlying micro-optimizations. The Fortress language illustrates this greatly, where all bulk-operations can conveniently be implemented using "big Sigma" style notations and array comprehensions.

In Funcalc, there is no way to express such micro-optimizations in the first place (writing to the same memory location instead of passing values via the stack etc.), so the spirit of the talk fits well to my project.

Even though this talk is already seven years old, I feel that this hasn't really arrived in many people's mindsets. It's a great motivation for my own work, so I'll just post it here.

- [The talk on Vimeo](https://vimeo.com/6624203)
- [Reference on ACM](http://dl.acm.org/citation.cfm?doid=1596550.1596551)

Unfortunately, the link to the slides is not working anymore (since Sun since was bought by Oracle, who'd guessed?) and I haven't found a replacement link anywhere.
