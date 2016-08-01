---
title: msbuild randomly hangs on Windows
layout: post
---

While working on a variant of ```zip``` or ```map2``` on Quad Ropes, I ran into the msbuild process hanging up multiple times. This makes a quick edit-compile cycle impossible because the only way to kill the processes is a re-start of the machine.

Turns out that this is caused by parallel compilation. msbuild.exe keeps some processes around for later re-use. Turns out this sometimes causes locking of files such that re-compilation becomes impossible. What a great feature.

Anyways, Jon Rea has posted on [Stackoverflow about this and his answer explains everything in much more detail.](http://stackoverflow.com/questions/13510465/the-mystery-of-stuck-inactive-msbuild-exe-processes-locked-stylecop-dll-nuget)
