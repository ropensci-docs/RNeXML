# extract all phylogenetic trees in ape format

extract all phylogenetic trees in ape format

## Usage

``` r
get_trees_list(nexml)
```

## Arguments

- nexml:

  a representation of the nexml object from which the data is to be
  retrieved

## Value

returns a list of lists of multiphylo trees, even if all trees are in
the same `trees` node (and hence the outer list will be of length

1.  or if there is only a single tree (and hence the inner list will
    also be of length 1. This ensures a consistent return type
    regardless of the number of trees present in the nexml file, and
    also preserves any grouping of trees.

## See also

[`get_trees`](https://docs.ropensci.org/RNeXML/reference/get_trees.md)
[`get_flat_trees`](https://docs.ropensci.org/RNeXML/reference/get_flat_trees.md)
[`get_item`](https://docs.ropensci.org/RNeXML/reference/nexml_get.md)

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_trees_list(nex)
#> [[1]]
#> 1 phylogenetic tree
#> 
```
