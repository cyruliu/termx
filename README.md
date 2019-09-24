## TermX86 Project Guide
Ubuntu:
## Install llvm-4.0 & ocaml llvm-4.0 binding
```
sudo apt install llvm-4.0
opam init
opam switch 4.05.0
opam install llvm.4.0.0
opam install thrift oasis

```

## Fetch termx86 repo & pull git submodules
```
git clone git@bitbucket.org:avta/termx86.git
cd termx86/llvm-tcfa
git submodule update --init --recursive

```
## Fetch cpathriftserver (run it before compiling llvm-tcfa) :
```
git clone git@github.com:erickoskinen/cpathriftserver.git
to compile and run cpathriftserver locally, please refer to its README.

```

## Compile and run llvm-tcfa
```
cd termx86/llvm-tcfa
oasis setup
make clean
make
./run.sh 
(you can edit this script to change the example you want to test)

```
## CPAChecker & Temper Running Commands
```
scripts/cpa.sh -preprocess -spec ~/path/to/repo/temper/deps/cpathriftserver/src/main/resource/error_reach.prp -config config/predicateAnalysis.properties ~/path/to/source/simple1_fail.c

./temper.native -cpa ~/path/to/source/simple1_fail.c

```

