# Caches next method in the calling environment

If the calling environment does not have the next method to be invoked
in the inheritance chain cached yet, this will find the next method
(using
[`findNextMethod()`](https://docs.ropensci.org/RNeXML/reference/findNextMethod.md),
and cache it in the calling environment such that a subsequent call to
[`methods::callNextMethod()`](https://rdrr.io/r/methods/NextMethod.html)
will find and use it.

## Usage

``` r
.cacheNextMethod()
```

## Details

As per the description, what this function does would normally already
be done by invoking
[`methods::callNextMethod()`](https://rdrr.io/r/methods/NextMethod.html),
so in theory this should be entirely redundant at best. However,
[`methods::addNextMethod()`](https://rdrr.io/r/methods/RMethodUtils.html),
which is invoked by `callNextMethod()` if a next method isn't cached
yet, is broken (errors out) if one of the classes in the signature
name-clashes with a class defined in another package. Calling this
function prior to `callNextMethod()` is meant to work around that.
