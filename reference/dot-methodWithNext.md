# Saves the next method in the method meta data

Promotes the given method definition to an instance of `MethodWithNext`,
thereby recording the next method in the `nextMethod` slot.

## Usage

``` r
.methodWithNext(method, nextMethod, .cache = FALSE)
```

## Arguments

- method:

  the `MethodDefinition` object to promote

- nextMethod:

  the `MethodDefinition` object to record as the next method

- .cache:

  whether to cache the promoted method definition object (using
  [`methods::cacheMethod()`](https://rdrr.io/r/methods/MethodSupport.html))

## Value

an instance of `MethodWithNext`, which has the next method in the
`nextMethod` slot

## Note

`MethodWithNext` objects are normally returned by
[`methods::addNextMethod()`](https://rdrr.io/r/methods/RMethodUtils.html),
but a constructor function for the class seems missing (or is
undocumented?). This provides one.
