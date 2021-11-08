# Godod Builds
This repository contains few CI workflows to generate linux template, editor and editor with mono builds with and without support for address, undefined and leak sanitizer.

Ready to use binaries are in [actions](https://github.com/qarmin/GodotBuilds/actions) or [releases](https://github.com/qarmin/GodotBuilds/releases) tab.

Provided binaries are from the latest commit of each Godot branch - 3.4, 3.x and master

**What is this?**
This are normal Godot builds compiled with Address, Leak and Undefined sanitizers support.
- Leak sanitizer - at the end prints info about leaked memory
- Undefined sanitizer - during run prints info about undefined C/C++ behaviour like dereferencing null pointer
- Address sanitizer - crashes entire app when critical event happens like e.g. usage after free or array overflow and prints exact place when memory was allocated, freed etc.

**Why I may need this?**
Sometimes game/app crash, even if looks that code looks fine.  
It is possible that engine doesn't work properly, so with this binaries, you can get backtrace of crash which will help to find similar issues in which you may find solution to your problems or you may create bug report which with such detailed backtrace may be more valuable.

**Why Godot don't provide such binaries?**
Mostly because they are heavy, slow and used by only a few people.  
This files weight much more than normal Godot binaries (100MB vs 1,5 GB or more), because contains debug symbols and many functions to provide additional info to user.  
Also usually they works ~5/10 times slower, so they should be only used to debug problems.

**Requirements**
`libasan5` for all binaries, on Ubuntu this should be installed by `sudo apt install libasan5`  
`mono-complete` 6.12 only if using mono version - can be downloaded from https://www.mono-project.com/download/stable/

**How to use them?**
This are normal Godot binaries, so you can use them exactly as you use Godot.

**Why only Linux binaries?**
Compiling binaries on Linux is really simple, only require to add specific compile commands. This binaries can be easily run in CI etc.  
Windows binaries probably require to use Visual Studio. Also binaries with address sanitizer don't work under Wine, so I can't test them.  
Mac is Mac, so it is possible to generate such binaries, but probably Apple require some signing, so I don't even have possibility to test if it works.

