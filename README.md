# GNU Basic Calculator (bc) Functions

My working file of functions for 
[GNU bc](https://www.gnu.org/software/bc/).

### Conventions

  - Function names ending in an underscore `_` are *helper* functions,
    not intended to be called directly.
  - Since bc doesn't accept functions as parameters to other functions,
    any functions that morally should be a parameter must be defined globally.
    Such a function is named `f`. If there must be two functions,
    the other will be named `g`. If a function wants to know the derivative of `f`,
    it'll expect that derivative to be named `ff` (see `newton` for example).

### Future Aspirations

  - Remove the `n` parameter to `approximate`
  - Improve numerical integral function by removing `n`
  - Add a numerical derivative function (see [this](https://en.wikipedia.org/wiki/Five-point_stencil))
  - Bernoulli numbers and polynomials

### Links and References

  - [The GNU Basic Calculator (bc): a Quick-Start Guide for Mathematicians](https://org.coloradomesa.edu/~mapierce2/bc)
  - [GNU bc Manual](https://www.gnu.org/software/bc/manual/html_mono/bc.html)
  - [Library of bc function on phodd.net](http://phodd.net/gnu-bc/)
  - [Keith Matthews' number theory functions](http://www.numbertheory.org/gnubc/gnubc.html)
