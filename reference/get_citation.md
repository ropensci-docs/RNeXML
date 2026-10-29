# Get citation from metadata

Extracts the citation annotation from the metadata annotation of
the`nexml` object, and returns its value.

## Usage

``` r
get_citation(nexml)
```

## Arguments

- nexml:

  a nexml object

## Value

the citation if the metadata provides one that is non-empty, and NA
otherwise. If multiple non-empty annotations are found, only the first
one is returned.

## Details

Currently the implementation looks for `dcterms:bibliographicCitation`
annotations. (Note that these may be given with any prefix in the
metadata so long as they expand to the same full property URIs.)

## See also

[`get_metadata_values()`](https://docs.ropensci.org/RNeXML/reference/get_metadata_values.md)
