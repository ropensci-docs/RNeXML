# extract a phylogenetic tree from the nexml

extract a phylogenetic tree from the nexml

## Usage

``` r
get_trees(nexml)
```

## Arguments

- nexml:

  a representation of the nexml object from which the data is to be
  retrieved

## Value

an ape::phylo tree, if only one tree is represented. Otherwise returns a
list of lists of multiphylo trees. To consistently receive the list of
lists format (preserving the hierarchical nature of the nexml), use
[`get_trees_list`](https://docs.ropensci.org/RNeXML/reference/get_trees_list.md)
instead.

## See also

`get_trees`
[`get_flat_trees`](https://docs.ropensci.org/RNeXML/reference/get_flat_trees.md)
[`get_item`](https://docs.ropensci.org/RNeXML/reference/nexml_get.md)

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_trees(nex)
#> 
#> Phylogenetic tree with 10 tips and 9 internal nodes.
#> 
#> Tip labels:
#>   taxon_8, taxon_9, taxon_10, taxon_1, taxon_2, taxon_3, ...
#> 
#> Rooted; includes branch length(s).
```
