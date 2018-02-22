# CAnDL Demo

## Introduction

This is a gui to demonstrate the Compiler Analysis Description Language (CAnDL). Please refer to [Philip Ginsbach, Lewis Crawford and Michael O’Boyle. CAnDL: A Domain Specific Language for Compiler Analysis. 27th ACM International Conference on Compiler Construction](https://www.conference-publishing.com/list.php?Event=CC18) for details.

## Dependencies

* Everything required to build [llvm and clang](https://llvm.org/docs/GettingStarted.html#software)
* [Python 2.7](https://www.python.org) with [GTK+3 bindings](http://python-gtk-3-tutorial.readthedocs.io/en/latest/install.html)
* [ninja](https://ninja-build.org)
* [ghc](https://www.haskell.org/ghc)
* [pypy](https://pypy.org)

## Installation

Please set up the gui directory as follows:

```sh
git clone https://github.com/cc18ginsbach/CAnDL-Demo
cd CAnDL-Demo
git clone https://github.com/cc18ginsbach/llvm
cd llvm/tools
git clone https://github.com/cc18ginsbach/clang
cd ../..
mkdir build
cd build
cmake ../llvm -DCMAKE_BUILD_TYPE=RELEASE -GNinja -DLLVM_PARALLEL_LINK_JOBS=1
ninja
```

## Usage

On the left side, enter valid C++ code. Load existing files into the editor using _File->Open_.
Selecting _Compiler->Compile_ will run this code through a modified version of clang that implements compiler analyses using the CAnDL programming language.
The progress can be observed in the message box at the bottom.

As a result of running _Compiler->Compile_, LLVM IR will appear in the _compiler IR code_ tab and the detected instances will appear in the _detection results_ tab.
By default, the program will look for polyhedral [SCoPs](http://perso.ens-lyon.fr/christophe.alias/impact2011/impact-07.pdf).

To run different analysis routines than SCoPs, modify the _Experiment_ specification in the _constraint specifications_ tab.

![Screenshot of CAnDL GUI](https://github.com/cc18ginsbach/CAnDL-Demo/raw/master/candl_gui_screenshot-2.jpg?raw=true "CAnDL GUI")

## Contact

If you have further questions, please contact me at philip.ginsbach@ed.ac.uk.

