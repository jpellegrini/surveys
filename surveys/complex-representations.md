# Complex representations

## Exact, inexact, and mixed complex numbers

Exact, inexact, and mixed complex number representations, where inexact and mixed numbers that are `=` are nevertheless distinct in the sense of `eqv?`: Gambit, Kawa, Chibi.  (Also CLISP, Pure.)

Exact, inexact, and mixed complex number representations, where inexact and mixed numbers that are `=` are the same in the sense of `eqv?`: MIT, STklos.

Exact and inexact complex number representations only (mixed complex numbers become inexact): Racket, Chicken 4 with the numbers egg, Chicken 5, Scheme48/scsh, Kawa, Chez, Vicare, Larceny, Ypsilon, IronScheme, Spark, Wraith, Sagittarius.  (Also ABCL, Allegro CL, Clozure CL, CMUCL, ECL, GNU CL, LispWorks, SBCL, Scieneer CL.)

Inexact complex number representations only: Gauche, Guile, SISC, SCM, KSi, S7, UMB, Stalin, Cyclone.  (Also Fortran, C/C++, Python, etc.)

Exact complex number representations only: Owl Lisp (which has no inexact numbers).

No complex numbers: plain Chicken 4, Bigloo, Ikarus, NexJ, SigScheme, Shoe, TinyScheme, Scheme 9, Dream, RScheme, BDC, XLisp, Rep, Schemik, Elk, VX, Oaklisp, Llava, SXM, Sizzle, FemtoLisp, Dfsch, Inlab.

Mosh has a bug whereby numbers that are `=` are always `eqv?` even if they differ in exactness; it supports exact, inexact, and mixed complex number representations, but doesn't differentiate exact from inexact properly.

## The imaginary part of an inexact real number

The value of `(imag-part 2.0)` is exact 0:  Racket, MIT, Gambit, plain Chicken, Guile, Kawa, Chez, Vicare, Larceny, Ypsilon, Mosh, IronScheme, STklos, RScheme (but see below), Sizzle, Spark, Chibi.

The value of `(imag-part 2.0)` is inexact 0.0:  Gauche, Chicken with the numbers egg, Scheme48/scsh, SISC, SCM, KSi, S7, UMB, SXM.

No `imag-part` procedure:  Bigloo, NexJ, Shoe, TinyScheme, Scheme 9, BDC, XLisp, Rep, Schemik, Elk, VX, Llava, FemtoLisp, Dfsch, Inlab.

No inexact numbers:  SigScheme, Dream, Oaklisp, Owl Lisp.

Integrating both sets of results, this means that Racket, Guile, Chez, Vicare, Larceny, Ypsilon, IronScheme, Spark behave *as if* they supported mixed-exactness complex numbers in the case where the real part is inexact and the imaginary part is exact 0, even though they do not support mixed-exactness complex numbers otherwise.

## Fake complex number support

Schemes that don't support non-real numbers can still fake support for `real-part` and `imag-part` by having the former return its argument and the latter return zero.  As usual, some do and some don't:

Fake support: plain Chicken, RScheme

No support: Shoe, TinyScheme, BDC, XLisp, Sizzle, Bigloo, Scheme 9, Elk, Rep, Owl Lisp

## Results of (imag-part 3.0+0) and (imag-part 3.0)

All R6RS systems behave the same way, returning 0.0 in the first case and 0 in the second.

Chicken 4 with the numbers egg, Chicken 5, and Scheme 48 return 0.0 in both cases.

Gambit, MIT, Chibi, and STklos return 0 in both cases.

All other systems lack support for either exact or inexact complex numbers or both.

## See also

See also: [Numeric tower](../numeric-tower/).
