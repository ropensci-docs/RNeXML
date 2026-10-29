# get_taxa_meta_list

Retrieve metadata of all species/otus otus (operational taxonomic units)
included in the nexml

## Usage

``` r
get_taxa_meta_list(nexml, what = "href")
```

## Arguments

- nexml:

  a nexml object

- what:

  One of href, rel, id, or xsi:type

## Value

the list of metadata for each taxon

## See also

[`get_item`](https://docs.ropensci.org/RNeXML/reference/nexml_get.md)

## Examples

``` r
if (FALSE) { # \dontrun{
data(bird.orders)
birds <- add_trees(bird.orders)
birds <- taxize_nexml(birds, "NCBI")
RNeXML:::get_taxa_meta_list(birds)
RNeXML:::get_taxa_meta_list(birds, 'rel')
RNeXML:::get_taxa_meta_list(birds, 'id')
RNeXML:::get_taxa_meta_list(birds, 'xsi:type')
} # }
```
