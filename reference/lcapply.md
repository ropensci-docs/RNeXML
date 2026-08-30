# Compact list then lapply

Compacts the list (i.e., removes NULL objects), then calls
[`lapply()`](https://rdrr.io/r/base/lapply.html) on the result with the
remaining parameters.

## Usage

``` r
lcapply(X, ...)
```

## Arguments

- X:

  the list object

- ...:

  remaining arguments to
  [`lapply()`](https://rdrr.io/r/base/lapply.html)
