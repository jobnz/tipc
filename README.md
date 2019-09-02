# tipc
A compiler from TIP to llvm bitcode

## TIP tools

TIP is a "Tiny Imperative Programming" language developed by Anders M\oller and Michael I. Schwartzbach for the [Static Program Analysis](https://cs.au.dk/~amoeller/spa/ "Static Program Analysis") they developed for graduate instruction at Aarhus University[^1].

[^1]: A big thanks to Anders and Michael for making TIP available to the community.

Accompanying those notes is a [Scala implementation](https://github.com/cs-au-dk/TIP/) that provides a number of static analysis implementations and interpreter-based evaluators.

## Dependencies

Install: java8, cpp, cmake, antlr4, llvm (we use v7)

## Building the executable

This project uses CMake to manage the build process.  We follow the cmake build model for the [ANTLR4 Cpp target](https://github.com/antlr/antlr4/tree/master/runtime/Cpp/cmake).  The `cmake` directory stores ANTLR4 related cmake files. 

`tipc` has a `CMakeLists.txt` file in the `src` directory.  This file configures the ANTLR4 and Cpp build process, e.g., source files, targets, libaries, etc.

There is a `build` directory within which you will build `tipc`.  To get started you should create that, empty, build directory if it doesn't exist.  All of the generated runtime files for ANTLR4 will be built the first time and stored in the build directory; this may take some time.

To build a tipc:
  1. `cd build`
  2. `cmake ../src`
  3. `make`

NB: You may see warnings related to ignored type attribute ATN that are due to s
ome type gymnastics in the current implementation of the ANTLR4 Visitor implemen
tation.

During development you need only run steps 1 and 2 a single time, 
unless you modify the CmakeLists.txt file.  Just run make in the build directory to rebuild after making changes to your tool source.

Note that the `tipg4` directory has a standalone ANTLR4 grammar.  It's README describes how to build it and run it using `grun`.

## Limitations

no records

no type checking

## Tests

unit testing 

fuzz testing 

differential testing with Scala tip

## Documentation

To understand this code, and perhaps extend it, you will want to become familiar with the core LLVM classes:
  * http://llvm.org/docs/ProgrammersManual.html#the-core-llvm-class-hierarchy-re
ference

The LLVM tutorials are a great starting point for understanding the APIs in the context of compiling:
  * https://llvm.org/docs/tutorial/