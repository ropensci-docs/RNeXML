# Calls the given generic with the given arguments

Calls the given generic with the given arguments, using the method whose
signature matches the arguments.

## Usage

``` r
.callGeneric(f, ..., .package = NULL)
```

## Arguments

- f:

  the generic, as a character string or a `standardGeneric` object

- ...:

  the arguments (named and/or unnamed) with which to call the matching
  method

- .package:

  the package name for finding the generic (if `f` is a character
  string); by default the package is determined from the calling
  environment

## Value

the value returned by the method

## Details

Uses
[`methods::selectMethod()`](https://rdrr.io/r/methods/getMethod.html) to
find the matching method. In theory, this is at best wholly redundant
with what standard S4 generics already do by themselves. However, the
generics dispatch for S4 seems (at least currently) broken at least if
the first argument in the signature is a class that name-clashes with a
class defined in another package. In that case, whether the standard
dispatch works correctly or not can depend on
[`search()`](https://rdrr.io/r/base/search.html) order, and can change
within a session depending on the order in which packages are loaded.
