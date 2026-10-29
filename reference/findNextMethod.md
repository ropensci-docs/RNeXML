# Finds the method that callNextMethod() should chain to

Attempts to find the "next" method in the inheritance chain. This would
(ideally) be the method that
[`methods::callNextMethod()`](https://rdrr.io/r/methods/NextMethod.html)
would chain to, as a result of the method
[`methods::addNextMethod()`](https://rdrr.io/r/methods/RMethodUtils.html)
would find (and return in the `nextMethod` slot of the `MethodWithNext`
object). Hence, in theory one shouldn't ever need this, but
unfortunately `addNextMethod()` is broken (and errors out) if one of the
classes in the signature name-clashes with an S4 class defined in
another package that is loaded.

## Usage

``` r
findNextMethod(method, f = NULL, envir = topenv())
```

## Arguments

- method:

  `MethodDefinition`, the method for which to find the next method

- f:

  `standardGeneric`, the standard generic for which to find the next
  method. By default this will be obtained from `method`.

- envir:

  the environment in which to find the method

## Value

a `MethodDefinition` object that is the next method in the chain by
inheritance

## Details

The next method will be determined by the S4 inheritance chain. However,
this function will walk only the inheritance chain of those arguments in
the signature that are defined in the package of the generic method from
which this function was invoked (directly or indirectly). If there are
no such parameters in the signature, or if there is more than one,
finding the next method is handed off to
[`methods::addNextMethod()`](https://rdrr.io/r/methods/RMethodUtils.html).

## Note

In theory a class name clash between packages shouldn't be a problem
because class names can be namespaced, and the `MethodDefinition` object
passed to `addNextMethod()` has all the necessary namespace information.
Hopefully, at some point this gets fixed in R, and then we don't need
this anymore.
