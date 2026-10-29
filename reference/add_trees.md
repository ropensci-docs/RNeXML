# add_trees

add_trees

## Usage

``` r
add_trees(phy, nexml = new("nexml"), append_to_existing_otus = FALSE)
```

## Arguments

- phy:

  a phylo object, multiPhylo object, or list of multiPhylo to be added
  to the nexml

- nexml:

  a nexml object to which we should append this phylo. By default, a new
  nexml object will be created.

- append_to_existing_otus:

  logical, indicating if we should make a new OTU block (default) or
  append to the existing one.

## Value

a nexml object containing the phy in nexml format.
