# GNU Basic Calculator (bc) Functions

My working collection of functions for 
[GNU bc](https://www.gnu.org/software/bc/).
The functions are split into two files:
`functions.bc` containing pure functions that only return a value,
and `routines.bc` containing functions that I’ve found useful in practice as an instructor
that, generally, print information about some input.
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
`prime`

Alongside the ubiquitous mathematical functions in this list,
this file contains implementations of the following:

  - [Numerical Differentiation](https://en.wikipedia.org/wiki/Finite_difference_coefficient)
    `derivative(x)`  
    Returns the derivative of the (global) function `f` at `x`
    using a finite central distance with eight points.
  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    `newton(x)`  
    Returns the zero of the (global) function `f`
    that results from iteratively applying Newton's Method 
    with initial parameter `x`.
  - [Numerical Integration](https://en.wikipedia.org/wiki/Boole%27s_rule)
    `integral(a,b)`  
    Returns the value of the definite integral 
    of the (global) function `f` between `a` and `b`.

## `routines.bc`

This file defines the following routines:

  - [Pythagorean Triple Generator](https://en.wikipedia.org/wiki/Pythagorean_triple#Generating_a_triple)
    (`pythagtriple(m,n)`) –
    Print the Pythagorean triple generated
    by two parameters `m` and `n`, and return the hypotenuse.
  - [Pythagorean Quadruple Generator](ihttps://en.wikipedia.org/wiki/Pythagorean_quadruple#Parametrization_of_primitive_quadruples)
    (`pythagquadruple(m,n,p,q)`) –
    Print the Pythagorean quadruple generated 
    by parameters `m`, `n`, `p`, and `q`, and return the hypotenuse.
  - [Degrees/Minutes/Seconds (DMS)](https://en.wikipedia.org/wiki/Minute_and_second_of_arc)
    (`dd2dms(x)`) –
    which prints the angle `x`, presumed to be measured in degrees,
    in terms of degrees° minutes′ seconds″.
    Prints the angle `x`, presumed as a decimal number of degrees,
    in DMS (degrees° minutes′ seconds″) notation.
  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    (`newtoniter(x,n)`) –
    Iteratively applies Newton's Method `n` times, printing each result,
    with initial guess `x` and (global) function `f`.
  - [Quadratic Polynomial Solver](https://en.wikipedia.org/wiki/Quadratic_equation)
    (`quadratic(a,b,c)`) –
    Print the roots and vertex coordinates of ax²+bx+c.
  - [Simple Continued Fraction](https://en.wikipedia.org/wiki/Continued_fraction#Infinite_continued_fractions_and_convergents) 
    (`contfrac(x)`) –
    Print the coefficients of the simple continued fraction representation of x
    as well as each convergent obtained by truncating at that coefficient,
    which are successively better rational approximations to the number x.
  - [Different Base Expression](https://en.wikipedia.org/wiki/Radix) 
    (`bases(n)`) –
    Print `n` expressed in bases 2, 3, ..., 36.
  - [Prime Integer Factorization](https://en.wikipedia.org/wiki/Integer_factorization) 
    (`factor(n)`) –
    Print the prime integer factorization of `n`.
  - [Rectangular/Polar Conversion](https://en.wikipedia.org/wiki/Polar_coordinate_system) 
    (`rect2pol(x,y)`) and (`pol2rect(r,θ)`) –
    Convert two-dimensional rectangular coordinates 
    to polar coordinates and vice-versa respectively.
  - [Rectilinear/Cylindrical Conversion](https://en.wikipedia.org/wiki/Cylindrical_coordinate_system) 
    (`rect2cyl(x,y,z)`) and (`cyl2rect(r,θ,z)`) –
    Convert three-dimensional rectangular coordinates 
    to cylindrical coordinates and vice-versa respectively.
  - [Rectilinear/Spherical Conversion](https://en.wikipedia.org/wiki/Spherical_coordinate_system) 
    (`rect2sphere(x,y,z)`) and (`sphere2rect(ρ,θ,φ)`) –
    Convert three-dimensional rectangular coordinates 
    to spherical coordinates and vice-versa respectively,
    following the mathematician’s convention 
    with the zenith angle θ in the range [0,2π) with θ = 0 along the positive x-axis,
    and the azimuth angle φ in the range [0,π] with φ = 0 along the positive z-axis.
  - [Collazt (Hailstone) Sequence](https://en.wikipedia.org/wiki/Collatz_conjecture) 
    (`collatz(n)`) –
    Print the sequence of positive integers that results from 
    iteratively applying the function prescribed by the Collatz Conjecture.
  - [Sum of Consecutive Powers](https://en.wikipedia.org/wiki/Sums_of_powers)
    (`sumofpowers(m)`) –
    Print every way that `m` can be written as a sum 
    of powers of consecutive positive integers.
  - [Zeckendorf Presentation](https://en.wikipedia.org/wiki/Zeckendorf%27s_theorem)
    (`zeckendorf(n)`) –
    Prints the unique sum of non-adjacent Fibonacci numbers equal to `n`.

## Conventions 

  - If a function in `routines.bc` defines or updates the value of a variable globally, 
    it will `print` that variable assignment explicitly.
  - Since bc doesn't accept functions as parameters to other functions,
    any functions that morally should be a parameter must be defined globally.
    Such a function will be named `f`.
  - Function names ending in `_` are *helper* functions
    not intended to be called directly.
  - Some functions that return the nth number in a sequence
    (e.g. `fibonacci`, `prime`) create an array of the same name as the function
    containing all previous terms in the sequence used to compute the nth term.
  - There are certain things bc is not designed for
    — linear algebra, statistics, and complex arithmetic among others —
    and should not be implemented in bc.
    These, if one so desires, should be implemented upstream 
    within a fork of the bc program itself.

## Aspirations

  - Add `cubic` and `quartic` functions that prints the details of a cubic and quartic polynomial.
  - Replace the discrete combinatorics functions (factorial, pick, choose, etc) with continuous (analytic?) analogous so I can remove the PRINT statements.
  - Add a function that finds constructable algebraic approximations to real numbers. (see [this](https://mathoverflow.net/q/2861/64073)).
  - Browse the [NIST Digital Library of Mathematical Functions](https://dlmf.nist.gov) for thoughts.

## Allusions

  - [The GNU Basic Calculator (bc): a Quick-Start Guide for Mathematicians](https://org.coloradomesa.edu/~mapierce2/bc)
  - [GNU bc Manual](https://www.gnu.org/software/bc/manual/html_mono/bc.html)
  - [Library of bc function on phodd.net](http://phodd.net/gnu-bc/)
  - [Keith Matthews' number theory functions](http://www.numbertheory.org/gnubc/gnubc.html)

