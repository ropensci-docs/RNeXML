# taxize nexml

Check taxonomic names against the specified service and add appropriate
semantic metadata to the nexml OTU unit containing the corresponding
identifier.

## Usage

``` r
taxize_nexml(
  nexml,
  type = c("ncbi", "itis", "col", "tpl", "gbif", "wd"),
  warnings = TRUE,
  ...
)
```

## Arguments

- nexml:

  a nexml object

- type:

  the name of the identifier to use

- warnings:

  should we show warning messages if no match can be found?

- ...:

  additional arguments to `[taxadb::get_ids()]`

## Examples

``` r
if (FALSE) { # \dontrun{
data(bird.orders)
birds <- add_trees(bird.orders)
birds <- taxize_nexml(birds, "NCBI")
} # }
```
