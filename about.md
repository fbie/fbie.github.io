---
layout: page
title: About
permalink: /about/
---

My name is Florian Biermann I am about to graduate with a PhD in programming languages and parallel programming from the [IT University of Copenhagen](https://itu.dk).

I have a masters in Software Development and Technology from the [IT University of Copenhagen](https://itu.dk), a bachelor of science in [Digital Media](http://digitalmedia-bremen.de/en) from the [University of Bremen](http://uni-bremen.de/) and studied Graphics Design at the [Art Institute of Boston at Lesley University](http://www.lesley.edu/college-art-and-design/) and .  My Chinese name is 罗恩.

In August 2018, I will start as OCaml and C\# developer at SimCorp within IBOR.

From July 2015 to June 2018 I was working as a PhD student on spreadsheet array programming as part of the [Popular Parallel Programming project](https://itu.dk/people/sestoft/p3).  My supervisor was [Prof. Peter Sestoft](https://itu.dk/people/sestoft).  I was funded by the [Sino-Danish Center for Education and Research](http://sinodanishcenter.com).

Before that I have been working part-time as a programmer at [Medical Insight](http://www.medical-insight.com/) (now part of Karos Health) and in the [PitLab](http://pitlab.itu.dk/) at ITU as a research assistant for [Prof. John Paulin Hansen](https://www.linkedin.com/in/johnpaulinhansen) (who is now at DTU).

You can download my public key [here](https://itu.dk/people/fbie/fbie_pubkey.asc).


## My PhD Project ##

In my PhD project I work on the spreadsheet language [Funcalc](http://www.itu.dk/people/sestoft/funcalc/).  My goal is to give spreadsheet users access to the parallel capabilities of their computing hardware without adding complex controlling structures.

Spreadsheets can be seen as declarative and purely-functional programs that are laid out in a two-dimensional grid.  The overall idea is to use *higher-order functions*, that is functions that either accept other functions as arguments or produce a function as a result, on contiguous spreadsheet cells, so-called *cell arrays*.  Computations on arrays occur often in scientific and financial computations. Many higher-order functions on arrays perform homogeneous computations; the same function is applied to every cell in the array.

Higher-order functions enable *data-parallelism*.  In a purely-functional language, such as Funcalc, we know in advance that there is no interdependency between single cells of an array.  Therefore, it is safe to parallelize certain computations on arrays transparently to the user.  Their program will run faster without them having to do anything.

Furthermore, I am interested in making array programming easier for non-programmers by finding representations of arrays that cater to straightforward and simple programming solutions.

The results of my PhD project do not only apply to spreadsheets but may be interesting for other high-level programming languages such as the [R language](https://www.r-project.org/), [Matlab](http://www.mathworks.com/products/matlab/) or [F#](http://fsharp.org/).


## Things I did and do ##

- During March and April 2017, I visited [Wensheng Dou](http://www.tcse.cn/~wsdou/) at the Institute of Software, Chinese Academy of Sciences (ISCAS), where we worked on lifting dependency structures on spreadsheets to higher-order functional programs over arrays.

- I worked as TA for the Practical Concurrent and Parallel Programming Course at ITU in [Fall 2014](http://www.itu.dk/people/sestoft/itu/PCPP/E2014/), [Fall 2015](http://www.itu.dk/people/sestoft/itu/PCPP/E2015/) and [Fall 2017](http://itu.dk/people/rikj/PCPP2017/).

- In summer semester 2016, I gave three lectures on parallel functional programming in Racket and Java 8 at UCAS for students without prior functional programming experience.  My lectures where part of a course on functional programming taught by [Yu ZHANG](http://lcs.ios.ac.cn/~yzhang).  Take a look at the [course material](https://github.com/fbie/parallel-functional-lectures).

- I have written a small Emacs mode for systematic literature reviews on BibTex files called [SLIRM](https://github.com/fbie/slirm).

- Read my master's thesis [Connected Set Filtering on Shared Memory Multicore Processors](https://itu.dk/people/fbie/thesis.pdf).

- Read my student project [Morphological Segmentation of Blood Images for Automated Malaria Diagnosis](https://itu.dk/people/fbie/morphological_segmentation_malaria.pdf).

- I programmed the first version of the gaze-controller Lego construction manual for children.  It was featured on [CES 2015 in Las Vegas](https://www.youtube.com/watch?v=WgpbtsK7a88) and showcased in Lego stores in Copenhagen and Frankfurt.  See the [ITU research video](https://www.youtube.com/watch?v=vLMaMqkISR0).

- Visit me on [CiteULike](http://citeulike.org/user/fbie) which is a really nice and free tool to manage literature.

- Visit me on [GitHub](https://github.com/fbie) and [BitBucket](https://bitbucket.org/fbie).

- Visit my [Orcid profile](http://orcid.org/0000-0002-5814-3202).

- Visit me on [Twitter](https://twitter.com/florianbier), which I barely use.

- Visit the [Bloop Website](http://dm.tzi.de/bloop/) and check out the video of the presentation at [BlenderCon 2011](https://www.youtube.com/watch?v=Uwm57iTytZs).

- Check out my ["World to (H)ear"](https://vimeo.com/13737427) project.


## Publications ##

-   **[Puncalc: Task-Based Parallelism and Speculative Reevaluation in Spreadsheets]()**. *Florian Biermann* and Alexander Asp Bock. To be presented at HLPP'18.


-   **[Rewriting High-Level Spreadsheet Structures into Higher-Order Functional Programs](https://doi.org/10.1007/978-3-319-73305-0_2)**.
    *Florian Biermann*, Wensheng Dou and Peter Sestoft.
    PADL'18. [Preprint](https://pure.itu.dk/portal/files/82454108/rewriting_spreadsheet_structures.pdf).


-   **[Quad Ropes: Immutable, Declarative Arrays with Parallelizable Operations](http://dl.acm.org/citation.cfm?id=3091971)**.
    *Florian Biermann* and Peter Sestoft.
    ARRAY'17. [Preprint](https://pure.itu.dk/portal/files/82083562/array17_quad_ropes_camera_ready.pdf).


-   **[Declarative Parallel Programming in Spreadsheet End-User Development](https://pure.itu.dk/portal/files/80807389/ITU_TR_2016_192.pdf)**. *Florian Biermann*.
    Technical Report, 2016.

-   **[Wrist-worn Pervasive Gaze Interaction](http://dx.doi.org/10.1145/2857491.2857514)**.
    John Paulin Hansen, Haakon Lund, *Florian Biermann* , Emilie Møllenbach, Sebastian Sztuk and Javier San Agustin.
    ETRA '16.


-   **[A Gaze Interactive Textual Smartwatch Interface](http://dx.doi.org/10.1145/2800835.2804332)**.
    John Paulin Hansen, *Florian Biermann*, Janus Aksø Madsen, Morten Jonassen, Haakon Lund, Javier San Agustin and Sebastian Sztuk.
    UbiComp '15.


-   **[A GazeWatch Pototype](http://dx.doi.org/10.1145/2786567.2792899)**.
    John Paulin Hansen, *Florian Biermann*, Emilie Møllenbach, Haakon Lund, Javier San Agustin, Sebastian Sztuk.
    MobileHCI '15.


-   **[The Animation Loop Station: Near Real-Time Animation Production](http://dx.doi.org/10.1007/978-3-642-33542-6_55)**.
    Benjamin Walther-Franks, *Florian Biermann*, Nikolaas Steenbergen and Rainer Malaka.
    ICEC '12.
