# Get the desired element from the nexml object

Get the desired element from the nexml object

## Usage

``` r
nexml_get(
  nexml,
  element = c("trees", "trees_list", "flat_trees", "metadata", "otu", "taxa",
    "characters", "characters_list", "namespaces"),
  ...
)
```

## Arguments

- nexml:

  a nexml object (from read_nexml)

- element:

  the kind of object desired, see details.

- ...:

  additional arguments, if applicable to certain elements

## Value

return type depends on the element requested. See details.

## Details

- "tree" an ape::phylo tree, if only one tree is represented. Otherwise
  returns a list of lists of multiphylo trees. To consistently receive
  the list of lists format (preserving the hierarchical nature of the
  nexml), use `trees` instead.

- "trees" returns a list of lists of multiphylo trees, even if all trees
  are in the same `trees` node (and hence the outer list will be of
  length 1) or if there is only a single tree (and hence the inner list
  will also be of length 1. This ensures a consistent return type
  regardless of the number of trees present in the nexml file, and also
  preserves any hierarchy/grouping of trees.

- "flat_trees" a multiPhylo object (list of ape::phylo objects) Note
  that this method collapses any hierarchical structure that may have
  been present as multiple `trees` nodes in the original nexml (though
  such a feature is rarely used). To preserve that structure, use
  `trees` instead.

- "metadata"Get metadata from the specified level (default is top/nexml
  level)

- "otu" returns a named character vector containing all available
  metadata. names indicate `property` (or `rel` in the case of
  links/resourceMeta), while values indicate the `content` (or `href`
  for links).

- "taxa" alias for otu

For a slightly cleaner interface, each of these elements is also defined
as an S4 method for a nexml object. So in place of
`get_item(nexml, "tree")`, one could use `get_tree(nexml)`, and so forth
for each element type.

## See also

[`get_trees`](https://docs.ropensci.org/RNeXML/reference/get_trees.md)

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
nexml_get(nex, "trees")
#> 
#> Phylogenetic tree with 10 tips and 9 internal nodes.
#> 
#> Tip labels:
#>   taxon_8, taxon_9, taxon_10, taxon_1, taxon_2, taxon_3, ...
#> 
#> Rooted; includes branch length(s).
nexml_get(nex, "characters_list")
#> $cs15
#>          <NA> log snout-vent length
#> taxon_8  ou10            -3.2777799
#> taxon_9  ou11             2.0959433
#> taxon_10 ou12             3.1373971
#> taxon_1   ou3             4.7532824
#> taxon_2   ou4            -2.7624146
#> taxon_3   ou5             2.1049413
#> taxon_4   ou6            -4.9504770
#> taxon_5   ou7             1.2714718
#> taxon_6   ou8             6.2593966
#> taxon_7   ou9             0.9099634
#> 
#> $cs31
#>          reef-dwelling
#> taxon_8              0
#> taxon_9              1
#> taxon_10             0
#> taxon_1              1
#> taxon_2              0
#> taxon_3              0
#> taxon_4              0
#> taxon_5              1
#> taxon_6              1
#> taxon_7              1
#> 
```
