# GNU Basic Calculator (bc) Functions

My working collection of functions and stuff for 
[GNU bc](https://www.gnu.org/software/bc/).
The code is split into two files:
`functions.bc` containing pure functions that only return a value,
and `routines.bc` containing functions I’ve found useful in practice as an instructor
that generally print information about some input.
Files like these can be loaded automatically by bc at startup
by setting this environment variable:

    export BC_ENV_ARGS="-lq /PATH/TO/functions.bc /PATH/TO/routines.bc"

## `functions.bc`

This file defines the following functions:

[`sgn`](https://en.wikipedia.org/wiki/Sign_function)
[`abs`](https://en.wikipedia.org/wiki/Absolute_value)
[`heavyside`](https://en.wikipedia.org/wiki/Heaviside_step_function)
`max`
[`int`](https://en.wikipedia.org/wiki/Truncation)
[`frac`](https://en.wikipedia.org/wiki/Truncation)
[`trunc`](https://en.wikipedia.org/wiki/Truncation)
[`intmod`](https://en.wikipedia.org/wiki/Modular_arithmetic)
[`isnearlyintegral`](https://en.wikipedia.org/wiki/Almost_integer)
`ln`
`log`
`logb`
[`pow`](https://en.wikipedia.org/wiki/Exponentiation)
`rad2deg`
`deg2rad`
[`dms2dd`](https://en.wikipedia.org/wiki/Minute_and_second_of_arc)
`cos`
`sin`
`tan`
`sec`
`csc`
`cot`
`arccos`
`arcsin`
`arctan`
[`atan2`](https://en.wikipedia.org/wiki/Atan2)
`arcsec`
`arccsc`
`arccot`
`cosh`
`sinh`
`tanh`
`sech`
`csch`
`coth`
`arcosh`
`arsinh`
`artanh`
`arsech`
`arcsch`
`arcoth`
[`factorial`](https://en.wikipedia.org/wiki/Factorial)
[`pick`](https://en.wikipedia.org/wiki/Permutation)
[`choose`](https://en.wikipedia.org/wiki/Combination)
[`fibonacci`](https://en.wikipedia.org/wiki/Fibonacci_sequence)
`derivative`
`newton`
`integral`
`gcd`
`lcm`
`prime`
`minkowski`

Most of these functions are either ubiquitous,
or, if not, can be quickly understood from their signature and brief definition.
Some of these functions however deserve an explanation:

  - [Numerical Differentiation](https://en.wikipedia.org/wiki/Finite_difference_coefficient)
    `derivative(x)`  
    Returns the derivative of the function *f* at *x*
    computed using a finite central distance with eight points.
  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    `newton(x)`  
    If it terminates, returns the zero of the (global) function *f*
    that results from iteratively applying Newton's Method with initial parameter *x*.
  - [Numerical Integration](https://en.wikipedia.org/wiki/Boole%27s_rule)
    `integral(a,b)`  
    Returns the value of the definite integral of the (global) function *f* between *a* and *b*
    computed using Boole's rule applied recursively to progressively finer subintervals.
  - [Minkowski's Question-Mark Function](https://en.wikipedia.org/wiki/Minkowski%27s_question-mark_function)
    `minkowski(x)`  
    Returns a number constructed in binary from the continued fraction of *x*.

## `routines.bc`

This file defines the following routines:

  - [Pythagorean Triple Generator](https://en.wikipedia.org/wiki/Pythagorean_triple#Generating_a_triple)
    `pythagtriple(m,n)`  
    Print the Pythagorean triple generated
    by two parameters *m* and *n*, and return the hypotenuse.
  - [Pythagorean Quadruple Generator](https://en.wikipedia.org/wiki/Pythagorean_quadruple#Parametrization_of_primitive_quadruples)
    `pythagquadruple(m,n,p,q)`  
    Print the Pythagorean quadruple generated 
    by parameters *m*, *n*, *p*, and *q*, and return the hypotenuse.
  - [Degrees/Minutes/Seconds (DMS)](https://en.wikipedia.org/wiki/Minute_and_second_of_arc)
    `dd2dms(x)`  
    Prints the decimal degree angle *x*
    in terms of DMS (degrees° minutes′ seconds″).
  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    `newtoniter(x)`  
    Iteratively applies Newton's Method, printing each result,
    with initial guess *x* and (global) function *f*.
  - [Quadratic Polynomial Solver](https://en.wikipedia.org/wiki/Quadratic_equation)
    `quadratic(a,b,c)`  
    Print the roots and vertex coordinates of *a*x²+*b*x+*c*.
  - [Simple Continued Fraction](https://en.wikipedia.org/wiki/Continued_fraction#Infinite_continued_fractions_and_convergents) 
    `contfrac(x)`  
    Print the coefficients of the simple continued fraction representation of *x*
    as well as each convergent obtained by truncating at that coefficient,
    giving successively better rational approximations to *x*.
  - [Different Base Expression](https://en.wikipedia.org/wiki/Radix) 
    `bases(n)`  
    Print `n` expressed in bases 2, 3, ..., 36.
  - [Prime Integer Factorization](https://en.wikipedia.org/wiki/Integer_factorization) 
    `factor(n)`  
    Print the prime integer factorization of *n*.
  - [Rectangular/Polar Conversion](https://en.wikipedia.org/wiki/Polar_coordinate_system) 
    `rect2pol(x,y)` / `pol2rect(r,θ)`  
    Convert two-dimensional rectangular coordinates 
    to polar coordinates and vice-versa respectively.
  - [Rectilinear/Cylindrical Conversion](https://en.wikipedia.org/wiki/Cylindrical_coordinate_system) 
    `rect2cyl(x,y,z)` / `cyl2rect(r,θ,z)`  
    Convert three-dimensional rectangular coordinates 
    to cylindrical coordinates and vice-versa respectively.
  - [Rectilinear/Spherical Conversion](https://en.wikipedia.org/wiki/Spherical_coordinate_system) 
    `rect2sphere(x,y,z)` / `sphere2rect(ρ,θ,φ)`  
    Convert three-dimensional rectangular coordinates 
    to spherical coordinates and vice-versa respectively,
    following the mathematician’s convention 
    with the zenith angle *θ* in the range [0,2π) with *θ* = 0 along the positive x-axis,
    and the azimuth angle *φ* in the range [0,π] with *φ* = 0 along the positive z-axis.
  - [Collazt (Hailstone) Sequence](https://en.wikipedia.org/wiki/Collatz_conjecture) 
    `collatz(n)`  
    Print the sequence of positive integers that results from 
    iteratively applying the function prescribed by the Collatz Conjecture.
  - [Sum of Consecutive Powers](https://en.wikipedia.org/wiki/Sums_of_powers)
    `sumofpowers(m)`  
    Print every way that *m* can be written as a sum 
    of powers of consecutive positive integers.
  - [Digits → List of Digits](https://en.wikipedia.org/wiki/Positional_notation)
    `intdigits(x)` / `fracdigits(x)` / `onlydigits(x, *d[])`  
    Create a list of the digits of *x* as a list.
    In particular, for any value of `obase`, 
    `intdigits` will create a list of the digits of the integer part of a number,
    `fracdigits` will create a list of the digits of the fractional part of a number,
    and `onlydigits` will return true if the number contains _only_ the digits
    specified in the list `d[]` as the indices with nonzero value.
  - [Zeckendorf Presentation](https://en.wikipedia.org/wiki/Zeckendorf%27s_theorem)
    `zeckendorf(n)`  
    Prints the unique sum of non-adjacent Fibonacci numbers equal to *n*.

## Conventions 

  - If a function in `routines.bc` defines or updates the value of a variable globally, 
    it will `print` that variable assignment explicitly.
  - Some functions in `functions.bc` that inherently entail a sequence of numbers
    (e.g. `fibonacci`, `prime`, etc) also create an array of the same name 
    containing all computed terms in the sequence.
  - There are functions not documented in this README with name ending in `_`. 
    These are *helper* functions, usually for the sake of recursion, 
    not intended to be called directly.
  - Since bc doesn't accept functions as parameters to other functions,
    any functions that morally should be a parameter must be defined globally.
    Such a function will be named `f`.
  - There are certain things bc is not designed for — 
    linear algebra, statistics, complex arithmetic, etc 
    — and should not be implemented in bc.
    These, if one so desires, should be implemented upstream 
    within a fork of the bc program itself.

## Aspirations

  - Add `cubic` and `quartic` functions that prints the details of a cubic and quartic polynomial.
  - Replace the discrete combinatorics functions (factorial, pick, choose, etc) with continuous (analytic?) analogous so I can remove the PRINT statements.
  - Add a function that finds constructable algebraic approximations to real numbers. (see [this](https://mathoverflow.net/q/2861/64073)).

## Allusions

  - [The GNU Basic Calculator (bc): a Quick-Start Guide for Mathematicians](https://org.coloradomesa.edu/~mapierce2/bc)
  - [GNU bc Manual](https://www.gnu.org/software/bc/manual/html_mono/bc.html)
  - [Library of bc function on phodd.net](http://phodd.net/gnu-bc/)
  - [Keith Matthews' number theory functions in bc](http://www.numbertheory.org/gnubc/gnubc.html)
  - [NIST Digital Library of Mathematical Functions](https://dlmf.nist.gov)

