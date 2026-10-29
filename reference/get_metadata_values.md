# Get the value(s) for metadata

Extracts the values from the metadata annotations for the given property
or properties, and returns the result.

## Usage

``` r
get_metadata_values(nexml, annotated = NULL, props)
```

## Arguments

- nexml:

  a nexml object

- annotated:

  the nexml component object from which to obtain metadata annotations,
  defaults to the nexml object itself

- props:

  a character vector of property names for which to extract metadata
  annotations

## Value

a named character vector, giving the values and names being the property
names

## Details

For matching property identifiers (i.e., URIs), prefixes in the input
list as well as in the `annotated` object will be expanded using the
namespaces of the `nexml` object. Names in the returned vector are
mapped to the (possibly prefixed) form in the input list.
