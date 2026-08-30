# Extracts meta objects matching properties

Extracts the metadata annotations for the given property or properties,
and returns the result as a list of `meta` objects.

## Usage

``` r
get_meta(nexml, annotated = NULL, props)
```

## Arguments

- nexml:

  a nexml object

- annotated:

  the nexml component object from which to obtain metadata annotations,
  or a list of such objects. Defaults to the nexml object itself.

- props:

  a character vector of property names for which to extract metadata
  annotations

## Value

a named list of the matching meta objects

## Details

For matching property identifiers (i.e., URIs), prefixes in the input
list as well as in the `annotated` object will be expanded using the
namespaces of the `nexml` object. Names in the returned list are mapped
to the (possibly prefixed) form in the input list. The resulting list is
flat, and hence does not retain the nesting hierarchy in the object's
annotation.
