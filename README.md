## NOTE: This is a fork!

This repository is a modified fork of [libConfuse](https://github.com/libconfuse/libconfuse).

Changes made:

1) Add CMake Support
2) Remove legacy build system files and support

libConfuse
==========
[![Badge][]][ISC]

* [Introduction](#introduction)
* [Documentation](#documentation)
* [Examples](#examples)
* [Build & Install](#build--install)
* [Origin & References](#origin--references)

### Local changes
- Added CMake-based build support for Windows and cross-platform builds
- Added feature detection for:
  `fmemopen`, `reallocarray`, `strdup`, `strndup`, `strcasecmp`

Original project copyright and license are preserved in `LICENSE`.

Introduction
------------

libConfuse is a configuration file parser library written in C.  It
supports sections and (lists of) values, as well as other features such
as single/double quoted strings, environment variable expansion,
functions and nested include statements.  Values can be strings,
integers, floats, booleans, and sections.

The goal is not to be _the_ configuration file parser library with a
gazillion of features.  Instead, it aims to be easy to use and quick to
integrate with your code.

> Please ensure you download a <ins>versioned archive</ins> from:
> <https://github.com/libconfuse/libconfuse/releases/>


Documentation
-------------

* [API reference manual](http://www.nongnu.org/confuse/manual/)
* [Tutorial](http://www.nongnu.org/confuse/tutorial-html/)


Examples
--------

* [simple.c](examples/simple.c) and [simple.conf](examples/simple.conf)
  shows how to use the "simple" versions of options
* [cfgtest.c](examples/cfgtest.c) and [test.conf](examples/test.conf)
  show most of the features of confuse, including lists and functions


Build & Install
---------------

This fork of libConfuse uses CMake as its build system. To configure, build, and install the library:

    cmake -B build
    cmake --build build
    sudo cmake --install build

Origin & References
-------------------

libConfuse was created by Martin Hedenfalk and released as open source
software under the terms of the [ISC license][1].  It was previously
called libcfg, but the name was changed to not confuse with other
similar libraries.  It is currently developed and maintained at GitHub.
Please use the [issue tracker][2] to report bugs and feature requests.


[1]:                http://en.wikipedia.org/wiki/ISC_license
[2]:                https://github.com/libconfuse/libconfuse/issues
[ISC]:              https://en.wikipedia.org/wiki/ISC_license
[Badge]:            https://img.shields.io/badge/License-ISC-blue.svg
[GitHub]:           https://github.com/libconfuse/libconfuse/actions/workflows/build.yml/
[GitHub Status]:    https://github.com/libconfuse/libconfuse/actions/workflows/build.yml/badge.svg
[Coverity Scan]:    https://scan.coverity.com/projects/6674
[Coverity Status]:  https://scan.coverity.com/projects/6674/badge.svg
