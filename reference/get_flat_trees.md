# get_flat_trees

extract a single multiPhylo object containing all trees in the nexml

## Usage

``` r
get_flat_trees(nexml)
```

## Arguments

- nexml:

  a representation of the nexml object from which the data is to be
  retrieved

## Value

a multiPhylo object (list of ape::phylo objects). See details.

## Details

Note that this method collapses any hierarchical structure that may have
been present as multiple `trees` nodes in the original nexml (though
such a feature is rarely used). To preserve that structure, use
[`get_trees`](https://docs.ropensci.org/RNeXML/reference/get_trees.md)
instead.

## See also

[`get_trees`](https://docs.ropensci.org/RNeXML/reference/get_trees.md)
[`get_trees`](https://docs.ropensci.org/RNeXML/reference/get_trees.md)
[`get_item`](https://docs.ropensci.org/RNeXML/reference/nexml_get.md)

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_flat_trees(nex)
#> 1 phylogenetic tree
```
