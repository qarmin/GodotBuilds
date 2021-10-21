# Godod Builds
This repository contains few CI workflows to generate linux template, editor and editor with mono builds with and without support for address, undefined and leak sanitizer.

All builds contains debug symbols.

The only requirement is to have installed `libasan5` on OS if you use Godot with sanitizers(on Ubuntu or similar `sudo apt install libasan5`)

Minimal supported OS is Ubuntu 20.04
