# Get flattened list of meta annotations

Collects recursively (in the case of nested meta annotations) all meta
object annotations for the given object, and returns the result as a
flat list.

## Usage

``` r
get_all_meta(annotated)
```

## Arguments

- annotated:

  the object from which to extract meta object annotations

## Value

a flat list of `meta` objects

## Details

Does not check that the input object can actually have meta annotations.
An invalid slot error will be generated if it can't.
