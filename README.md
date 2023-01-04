# GNU Basic Calculator (bc) Functions

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a-Coffee-orange)](https://www.buymeacoffee.com/mpierce)

My working file of functions for 
[GNU bc](https://www.gnu.org/software/bc/).

### Functions

In addition to many basic functions,
this file contains implementations of the following:

  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    (`newton`)
    for approximating zeros of functions
  - [Boole's Rule](https://en.wikipedia.org/wiki/Boole's_rule)
    (`boole_`)
    for numerical integration
  - [Rational Approximation](https://en.wikipedia.org/wiki/Continued_fraction#Infinite_continued_fractions_and_convergents) 
    (`rational`)
    to a real number by a convergent of its continued fraction

### Conventions

  - Function names ending in `_` are *helper* functions,
    not intended to be called directly.
  - Since bc doesn't accept functions as parameters to other functions,
    any functions that morally should be a parameter must be defined globally.
    Such a function is named `f`. If there must be two functions,
    the other will be named `g`. If a function wants to know the derivative of `f`,
    it'll expect that derivative to be named `ff` (see `newton` for example).

### Aspirations

  - Remove the `n` parameter to `rational`
  - Improve numerical integral function by removing `n`
  - Add a numerical derivative function (see [this](https://en.wikipedia.org/wiki/Five-point_stencil))
  - Bernoulli numbers and polynomials
  - Euclidean algorithm for the GCD
  - If I compile bc myself, will it get GNU readline support?

### Allusions

  - [The GNU Basic Calculator (bc): a Quick-Start Guide for Mathematicians](https://org.coloradomesa.edu/~mapierce2/bc)
  - [GNU bc Manual](https://www.gnu.org/software/bc/manual/html_mono/bc.html)
  - [Library of bc function on phodd.net](http://phodd.net/gnu-bc/)
  - [Keith Matthews' number theory functions](http://www.numbertheory.org/gnubc/gnubc.html)
  - ["math and bitcoin tools in gnu bc and bash"](https://github.com/fivepiece/btc-bash-ng)

