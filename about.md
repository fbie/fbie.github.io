---
layout: page
title: About
permalink: /about/
---

My name is Florian Biermann and I studied [Digital Media](http://digitalmedia-bremen.de/en) at the
[University of Bremen](http://uni-bremen.de/), Graphics Design at the
[Art Institute of Boston at Lesley University](http://www.lesley.edu/college-art-and-design/)
and Software Development and Technology at the
[IT University of Copenhagen](https://itu.dk).

As of July 2015 I am working as a PhD student on spreadsheet array
programming as part of the
[Popular Parallel Programming project](https://itu.dk/people/sestoft/p3). My
principal supervisor is
[Prof. Peter Sestoft](https://itu.dk/people/sestoft). My secondary
supervisor is [Yu ZHANG](http://lcs.ios.ac.cn/~yzhang) from the
[Institute of Software at the Chinese Academy of Sciences](http://lcs.ios.ac.cn). I
am funded by the
[Sino-Danish Center for Education and Research](http://sinodanishcenter.com).

Before that I have been working part-time as a programmer at [Medical Insight](http://www.medical-insight.com/) (now part of Karos Health) and in the [PitLab](http://pitlab.itu.dk/) at ITU as a research assistant for [Prof. John Paulin Hansen](https://www.linkedin.com/in/johnpaulinhansen) (who is now at DTU).

You can download my public key [here](files/fbie_pubkey.asc).

## My PhD Project ##

In my PhD project I work on the spreadsheet language [Funcalc](http://www.itu.dk/people/sestoft/funcalc/). My goal is to give spreadsheet users access to the parallel capabilities of their computing hardware without adding complex controlling structures.

Spreadsheets can be seen as declarative and purely-functional programs that are laid out in a two-dimensional grid. The overall idea is to use *higher-order functions*, that is functions that either accept other functions as arguments or produce a function as a result, on contiguous spreadsheet cells, so-called *cell arrays*. Computations on arrays occur often in scientific and financial computations. Many higher-order functions on arrays perform homogeneous computations; the same function is applied to every cell in the array.

Higher-order functions enable *data-parallelism*. In a purely-functional language, such as Funcalc, we know in advance that there is no interdependency between single cells of an array. Therefore, it is safe to parallelize certain computations on arrays transparently to the user. Their program will run faster without them having to do anything.

Furthermore, I am interested in making array programming easier for non-programmers by finding representations of arrays that cater to straightforward and simple programming solutions.

The results of my PhD project do not only apply to spreadsheets but may be interesting for other high-level programming languages such as the [R language](https://www.r-project.org/), [Matlab](http://www.mathworks.com/products/matlab/) or [F#](http://fsharp.org/).

## Things I did and do ##

- Read my thesis [Connected Set Filtering on Shared Memory Multicore
Processors](files/thesis.pdf).

- Read my project [Morphological Segmentation of Blood Images for
Automated Malaria Diagnosis](files/morphological_segmentation_malaria.pdf).

- I programmed the first version of the gaze-controller Lego
  construction manual for children. It was featured on CES 2015 in Las
  Vegas and showcased in Lego stores in Copenhagen and Frankfurt. See
  the [ITU research video](IT University of Copenhagen).

- Visit me on [CiteULike](http://citeulike.org/user/fbie) which is a
  really nice and free tool to manage literature.

- Visit me on [GitHub](https://github.com/fbie) and [BitBucket](https://bitbucket.org/fbie).

- Visit my [Orcid profile](http://orcid.org/0000-0002-5814-3202).

- Visit the [Bloop Website](http://dm.tzi.de/bloop/) and check out the
video of the presentation at
[BlenderCon 2011](https://www.youtube.com/watch?v=Uwm57iTytZs).

- Check out my ["World to (H)ear"](https://vimeo.com/13737427)
project.


## Publications ##

- Hansen, J. P., *Biermann, F.*, Madsen, J. A., Jonassen, M., Lund,
  H., San Agustin, J., Sztuk, S., 2015. **A gaze interactive textual
  smartwatch interface.** In: Proceedings of the 2015 ACM
  International Joint Conference on Pervasive and Ubiquitous Computing
  and Proceedings of the 2015 ACM International Symposium on Wearable
  Computers. UbiComp '15. ACM, New York, NY, USA, pp. 839-847. URL
  [http://dx.doi.org/10.1145/2800835.2804332]()

- Hansen, J. P., *Biermann, F.*, M&oslash;llenbach, E., Lund, H., San
  Agustin, J., Sztuk, S., 2015. **A GazeWatch prototype.** In:
  Proceedings of the 17th International Conference on Human-Computer
  Interaction with Mobile Devices and Services Adjunct. MobileHCI
  '15. ACM, New York, NY, USA, pp. 615-621. URL
  [http://dx.doi.org/10.1145/2786567.2792899]()

- Walther-Franks, B., *Biermann, F.*, Steenbergen, N., Malaka,
  R., 2012. **The animation loop station: Near real-time animation
  production.** In: International Conference on Entertainment
  Computing (ICEC). Springer. URL
  [http://dx.doi.org/10.1007/978-3-642-33542-6_55]()
