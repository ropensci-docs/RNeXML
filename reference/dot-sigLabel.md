# Create a label for a method signature

Creates a label for a signature mirroring the result of `.sigLabel()` in
the `methods` package, which unfortunately does not export the function.
This is needed, for example, for the `excluded` slot in the
`MethodWithNext` class.

## Usage

``` r
.sigLabel(signature)
```

## Arguments

- signature:

  the signature for which to create a label, as a vector or list of
  strings, or as an instance of `signature`.

## Value

a character string
