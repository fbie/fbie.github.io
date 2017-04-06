---
title: Omnisharp, Mono, Linux, Emacs in the year 2017
layout: post
---

I've been a long-time Omnisharp fan and it is kinda important that I
can work on C# code somewhat productively in order to get anywhere with my project. Nevertheless, some recent update of [ommisharp-emacs]() broke my setup and hence I set out in order to fix it.

Since it was quite a lengthy process to figure out what to do, I'll use this as a little note  to myself on how to get the setup straight:

1. Use [`omnisharp-mono.tar.gz`](https://github.com/OmniSharp/omnisharp-roslyn/releases) release if you are not running on dotnet core yet.
2. Install it into a proper location, e.g. `~/.emacs.d/omnisharp-roslyn-mono/`.
3. Locate `System.Native.so`:
   ```
   $ locate System.Native.so
   /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.4/System.Native.so
   /usr/share/dotnet/shared/Microsoft.NETCore.App/1.1.1/System.Native.so
   ```
4. Put a copy of the file next to `OmniSharp.exe` (I used the 1.0.4 version, the other one didn't seem to work) and call it `libSystem.Native.so` (see [this issue on GitHub](https://github.com/OmniSharp/omnisharp-roslyn/issues/600)).
5. Add a script that runs `OmniSharp.exe` with `mono` from its absolute path and call it `omnisharp.sh`:
   ```bash
   #!/bin/bash
   DIR="$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )"
   mono $DIR/OmniSharp.exe "$@"
   ```
6. Tell Emacs to run this script when starting OmniSharp:
   ```elisp
   (setq omnisharp-server-executable-path "~/.emacs.d/omnisharp-roslyn-mono/omnisharp.sh")
   ```
7. Make it start automatically when opening a `.cs` file, if it is not already running.


This used to be much easier. I hope that writing this down will spare me from having to figure all this stuff out again a second time.
