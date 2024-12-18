# GNU Basic Calculator (bc) Functions

My working collection of functions for 
[GNU bc](https://www.gnu.org/software/bc/).
The functions are split into two files:
`functions.bc` containing simple “pure” functions, 
and `routines.bc` containing functions 
that I’ve found useful in practice as a math instructor.

## `functions.bc`

Here is a list of the functions this file defines:

[`sgn`](https://en.wikipedia.org/wiki/Sign_function)
[`abs`](https://en.wikipedia.org/wiki/Absolute_value)
[`heavyside`](https://en.wikipedia.org/wiki/Heaviside_step_function)
[`int`](https://en.wikipedia.org/wiki/Truncation)
`ln`
`log`
`logb`
[`pow`](https://en.wikipedia.org/wiki/Exponentiation)
`rad2deg`
`deg2rad`
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
`newton`
`integrate`
`prime`

Alongside the ubiquitous mathematical functions in this list,
this file contains implementations of the following:

  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    (`newton(x)`)
    which approximates a zero of a smooth function `f` near `x`.
    Note that `f` and its derivative `ff` must be globally defined.
  - [Numerical Integration](https://en.wikipedia.org/wiki/Boole%27s_rule)
    (`integrate(a,b,n)`)
    which numerically computes the value of a definite integral 
    of a function `f` between `a` and `b` using 
    [Boole's Rule](https://en.wikipedia.org/wiki/Boole's_rule) (`boole_`)
    with `n` subdivisions.
    Note that `f` must be globally defined.

## `routines.bc`

Here is a list of the functions this file defines:

  - [Pythagorean Triple Generator](https://en.wikipedia.org/wiki/Pythagorean_triple#Generating_a_triple)
    (`pythagtriple(m,n)`)
    which prints the Pythagorean triple 
    generated by two parameters `m` and `n`.
  - [Pythagorean Quadruple Generator](ihttps://en.wikipedia.org/wiki/Pythagorean_quadruple#Parametrization_of_primitive_quadruples)
    (`pythagquadruple(m,n,p,q)`)
    which prints the primitive Pythagorean quadruple 
    generated by four parameters `m`, `n`, `p`, and `q`.
  - [Newton's Method](https://en.wikipedia.org/wiki/Newton's_method)
    (`newtoniter(x,n)`)
    which iteratively approximates a zero 
    of a smooth function `f` near `x` a total of `n` times,
    printing each successive approximation.
    Note that `f` and its derivative `ff` must be globally defined.
  - [Quadratic Polynomial Solver](https://en.wikipedia.org/wiki/Quadratic_equation)
    (`quadratic(a,b,c)`)
    which prints the roots and vertex of a degree-two polynomial
    given its coefficients as input.
  - [Rational Approximation](https://en.wikipedia.org/wiki/Continued_fraction#Infinite_continued_fractions_and_convergents) 
    (`rational(x)`)
    which displays subsequently better rational approximations to `x` —
    the convergents of its continued fraction presentation —
    until finding the first one equal to `x` up to `scale`.
  - [Different Base Expression](https://en.wikipedia.org/wiki/Radix) 
    (`bases(n)`)
    which displays a number `n` in bases 2, 3, …, 36.
  - [Prime Integer Factorization](https://en.wikipedia.org/wiki/Integer_factorization) 
    (`factor(n)`)
    which displays the prime integer factors of `n`.
  - [Rectangular/Polar Conversion](https://en.wikipedia.org/wiki/Polar_coordinate_system) 
    (`rect2pol(x,y)`) and (`pol2rect(r,θ)`)
    which convert two-dimensional rectangular coordinates 
    to polar coordinates and vice-versa respectively.
  - [Rectilinear/Cylindrical Conversion](https://en.wikipedia.org/wiki/Cylindrical_coordinate_system) 
    (`rect2cyl(x,y,z)`) and (`cyl2rect(r,θ,z)`)
    which convert three-dimensional rectilinear coordinates 
    to cylindrical coordinates and vice-versa respectively.
  - [Rectilinear/Spherical Conversion](https://en.wikipedia.org/wiki/Spherical_coordinate_system) 
    (`rect2sphere(x,y,z)`) and (`sphere2rect(ρ,θ,φ)`)
    which convert three-dimensional rectilinear coordinates 
    to spherical coordinates and vice-versa respectively.
  - [Collazt (Hailstone) Sequence](https://en.wikipedia.org/wiki/Collatz_conjecture) 
    (`collatz(n)`)
    which prints the hailstone sequence obtained
    by iteratively applying the transformation prescribed by the Collatz Conjecture.
  - Sum of Consecutive Powers
    (`sumofpowers(n,p)`)
    which prints every way that `n` can be expressed as a sum
    of consecutive `p`th itegral powers.

## Conventions

  - Function names ending in `_` are *helper* functions,
    not intended to be called directly.
  - _Some_ functions that return the nth number in a sequence
    (e.g. `fibonacci`,  `prime`) create an array of the same name as the function
    containing all previous terms in the sequence used to compute the nth term.
  - In the file `routines.bc` if a function changes/defines a variable globally, 
    the function will `print` that variable assignment explicitly.
  - Since bc doesn't accept functions as parameters to other functions,
    any functions that morally should be a parameter must be defined globally.
    Such a function is named `f`. If there must be two functions,
    the other will be named `g`. If a function wants to know the derivative of `f`,
    it'll expect that derivative to be named `ff` (e.g. `newton`).

## Aspirations

  - Add `cubic` and `quartic` functions
    that prints the details of a cubic and quartic polynomial.
  - Address issues with the numerical integration `integrate` function:
    There must be a way to remove the need for the parameter `n`,
    Also, I'm concerned this function is inaccurate for large values of |b – a|.
  - Add a function that finds constructable algebraic approximations to real numbers. (see [this](https://mathoverflow.net/q/2861/64073)).
  - Add a numerical derivative function (see [this](https://en.wikipedia.org/wiki/Five-point_stencil)).

## Allusions

  - [The GNU Basic Calculator (bc): a Quick-Start Guide for Mathematicians](https://org.coloradomesa.edu/~mapierce2/bc)
  - [GNU bc Manual](https://www.gnu.org/software/bc/manual/html_mono/bc.html)
  - [Library of bc function on phodd.net](http://phodd.net/gnu-bc/)
  - [Keith Matthews' number theory functions](http://www.numbertheory.org/gnubc/gnubc.html)
  - ["math and bitcoin tools in gnu bc and bash"](https://github.com/fivepiece/btc-bash-ng)

