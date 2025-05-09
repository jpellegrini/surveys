# Eval define

Passing a definition to `eval` may or may  not work according to R5RS.  Furthermore, in many Schemes, but not in R5RS, it's possible to call `eval` with just one argument, implying the interaction environment.  I tested the suite of Schemes to determine whether and how it's possible to add definitions to the interaction environment by evaluating the following four forms at the REPL:

```Scheme
(eval '(define x 32) (interaction-environment))
x
(eval '(define y 55))
y
```

The following Schemes allow definition by `eval`:

* Supports both `interaction-environment` and single-argument `eval`: Gambit, Chicken, Bigloo, Kawa, SISC, SCM, Chez, Larceny, NexJ, STklos, TinyScheme, Sizzle, Spark, LIPS

* Supports single-argument `eval` but not `interaction-environment`: Racket, RScheme, Scheme 9, S7, XLisp, Rep, Elk, UMB, VX, Llava, SXM, FemtoLisp, Inlab, Biwa (SXM provides `interaction-environment` but calling it signals an error)

* Supports `interaction-environment` but not single-argument `eval`: Gauche, Scheme48/scsh, Guile, Vicare, Ypsilon, IronScheme, SigScheme, Dream, BDC, Sagittarius

The following Schemes do *not* allow definition by `eval`:

* Does not support `interaction-environment` or single-argument `eval`: MIT, Mosh, KSi, Oaklisp, Dfsch, Owl Lisp

* Supports both `interaction-environment` and single-argument `eval`, but definitions aren't visible in the interaction environment: Chibi

* Supports `interaction-environment` but not single-argument `eval`, but definitions aren't visible in the interaction environment: Shoe

* Does not support `eval` at all: Scheme 9, Schemik
