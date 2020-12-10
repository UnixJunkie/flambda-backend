# flambda-backend
The Flambda backend project for OCaml

## Installation instructions

```
$ opam switch 4.11.1
$ eval $(opam env)
$ git clone https://github.com/ocaml-flambda/dune
$ cd dune
$ git checkout origin/special_dune
$ make release
$ cd ..
$ git clone https://github.com/ocaml-flambda/flambda-backend
$ git checkout origin/4.11
$ autoconf
$ ./configure --prefix=/path/to/install/dir --enable-middle-end=closure --with-dune=$(pwd)/../dune/dune.exe
$ make
$ make install
```

Note that `make install` completely overwrites the given `--prefix` directory.

You can also specify `--enable-middle-end=flambda`.