# SDPB

SDPB is an open-source, arbitrary-precision, parallelized semidefinite
program solver, designed for the conformal bootstrap.

It solves the following type of optimization problem

```
maximize:  b_0 + \sum_n b_n y_n over (y_1,...,y_N),

such that: M_{0j}(x) + \sum_n y_n M_{nj}(x) is positive semidefinite
           for all x >= 0 and 1 <= j <= J,

where each M_{nj}(x) is a polynomial matrix in x.
```

For more information, see [A Semidefinite Program Solver for the Conformal Bootstrap](http://arxiv.org/abs/1502.02033)
and the manual in the `docs` folder.

## Installation and Requirements

SDPB requires

- [Boost C++ Libraries](http://www.boost.org/) (tested with Boost 1.54).

- [The GNU Multiprecision Library](https://gmplib.org/).

To install, you must first edit the `Makefile` to define the variables
`GMPINCLUDEDIR`, `BOOSTINCLUDEDIR`, and `LIBDIR.` Then type `make` to
build the `sdpb` executable.

SDPB has only been tested on Linux (and only on a small number of
distrubtions). If you want to install SDPB on Mac OS X, be prepared
for adventure. Please use the issue tracker if you encounter
installation problems. For those with experience packaging software,
I'd appreciate help making SDPB easier to install.

## Usage

Type `sdpb --help` for the syntax and a list of options.

The input format for SDPB is XML-based and described in the manual.
The Mathematica file `SDPB.m` includes code to export semidefinite
programs in this format, along with some examples.

## Author

- David Simmons-Duffin (davidsd@gmail.com)

As of February 2015, I am supported by DOE grant number DE-SC0009988
and a William D. Loughlin Membership at the Institute for Advanced
Study.

## Attribution

If you use SDPB in work that results in publication, please cite

- D. Simmons-Duffin, "A Semidefinite Program Solver for the
  Conformal Bootstrap", [arXiv:1502.02033 \[hep-th\]](http://arxiv.org/abs/1502.02033).

Depending on how SDPB is used, please also consider the following sources:

The first use of semidefinite programming in the bootstrap:

- D. Poland, D. Simmons-Duffin and A. Vichi, "Carving Out the Space of
  4D CFTs," JHEP 1205, 110 (2012) [arXiv:1109.5176 \[hep-th\]](http://arxiv.org/abs/1109.5176).

The generalization of semidefinite programming methods to arbitrary
spacetime dimension:

- F. Kos, D. Poland and D. Simmons-Duffin, "Bootstrapping the O(N)
  Vector Models," JHEP 1406, 091 (2014) [arXiv:1307.6856 \[hep-th\]](http://arxiv.org/abs/1307.6856).

The generalization of semidefinite programming methods to arbitrary
systems of correlation functions:

- F. Kos, D. Poland and D. Simmons-Duffin, "Bootstrapping Mixed
  Correlators in the 3D Ising Model," [arXiv:1406.4858 \[hep-th\]](http://arxiv.org/abs/1406.4858).

## Acknowledgements

- SDPB Makes extensive use of [MPACK](http://mplapack.sourceforge.net/), the multiple precision linear algebra library written by Nakata Maho.  Several source files from MPACK are included in the SDPB source tree (see the license at the top of those files).

- SDPB uses Lee Thomason's [tinyxml2](http://www.grinninglizard.com/tinyxml2/) library (included in the source tree) for parsing.

- The design of SDPB was partially based on the solvers [SDPA](http://sdpa.sourceforge.net/) and SDPA-GMP, which were essential sources of inspiration and examples.

- Thanks to Filip Kos, David Poland, and Alessandro Vichi for collaboration in developing semidefinite programming methods for the conformal bootstrap and assistance testing SDPB.

- Thanks to Amir Ali Ahmadi, Hande Benson, Pablo Parrilo, and Robert Vanderbei for advice and discussions about semidefinite programming.
