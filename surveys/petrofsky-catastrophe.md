# Petrofsky catastrophe

This is a test of the expression `(call-with-current-continuation (lambda (c) (0 (c 1))))` as described in [this comp.lang.scheme thread](https://groups.google.com/g/comp.lang.scheme/c/J2ut9mbyQrU/m/UbZCSoA4XhQJ) against the usual suite of Schemes.

Returns `1`:  Racket, Gauche, MIT, Gambit, Chicken, Bigloo, Guile, Chez, Vicare, Larceny, Ypsilon, Mosh, NexJ, STklos, KSi, Peroxide, Shoe, TinyScheme, Scheme9, RScheme, S7, BDC, XLisp, Rep, UMB, SXM, Sagittarius

Prints a "not a procedure" warning but returns `1` anyway: Scheme48/scsh, Kawa, SISC, Chibi

Prints a "not a procedure" error: SCM, IronScheme, JScheme, SigScheme, Elk, Llava, Sizzle, Inlab

Prints a "not a procedure" error and hangs: Owl Lisp

Crashes: Schemik

No support for `call-with-current-continuation`: FemtoLisp, Dfsch
