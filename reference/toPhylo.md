# nexml to phylo

nexml to phylo coercion

## Usage

``` r
toPhylo(tree, otus)
```

## Arguments

- tree:

  an nexml tree element

- otus:

  a character string of taxonomic labels, named by the otu ids. e.g.
  (from get_otu_maps for the otus set matching the relevant trees node.

## Value

phylo object. If a "reconstructions" annotation is found on the edges,
return simmap maps slot as well.
