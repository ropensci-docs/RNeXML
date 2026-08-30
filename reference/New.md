# new with namespaced class name

Convenience function for
[`methods::new()`](https://rdrr.io/r/methods/new.html) that ensures that
the provided class name is namespaced with a package name.

## Usage

``` r
New(Class, ...)
```

## Arguments

- Class:

  the name of the S4 class to be instantiated

- ...:

  additional parameters for
  [`methods::new()`](https://rdrr.io/r/methods/new.html)

## Details

If the provided class name is not already namespaced (see
[`methods::packageSlot()`](https://rdrr.io/r/methods/getPackageName.html)),
it will be namespaced with this package. This mechanism is used by
`new()` to disambiguate if the class name clashes with a class defined
in another package.

## Note

This may not completely eliminate messages on standard error about
classes with the same name having been found in different packages. If
they appear, they will most likely have come from the call to the
[`methods::initialize()`](https://rdrr.io/r/methods/new.html) generic
that `new()` issues at the end.
