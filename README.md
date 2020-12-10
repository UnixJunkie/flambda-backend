# flambda-backend
The Flambda backend project for OCaml.

## Installation instructions

Only currently tested on Linux/x86-64 and macOS/x86-64.
```
$ opam switch 4.11.1
$ eval $(opam env)
$ git clone https://github.com/ocaml-flambda/dune
$ cd dune
$ git checkout origin/special_dune
$ make release
$ cd ..
$ git clone https://github.com/ocaml-flambda/flambda-backend
$ cd flambda-backend
$ git checkout origin/4.11
```
For the moment, if running on macOS, edit `Makefile.in` at this point to remove the `-L` from the `cp` commands (there is a comment).  Then on all platforms:
```
$ autoconf
$ ./configure --prefix=/path/to/install/dir --enable-middle-end=closure --with-dune=$(pwd)/../dune/dune.exe
$ make
$ make install
```

Note that `make install` completely overwrites the given `--prefix` directory.

You can also specify `--enable-middle-end=flambda`.
