# add elements to a new or existing nexml object

add elements to a new or existing nexml object

## Usage

``` r
nexml_add(
  x,
  nexml = new("nexml"),
  type = c("trees", "characters", "meta", "namespaces"),
  ...
)
```

## Arguments

- x:

  the object to be added

- nexml:

  an existing nexml object onto which the object should be appended

- type:

  the type of object being provided.

- ...:

  additional optional arguments to the add functions

## Value

a nexml object with the additional data

## See also

[`add_trees`](https://docs.ropensci.org/RNeXML/reference/add_trees.md)
[`add_characters`](https://docs.ropensci.org/RNeXML/reference/add_characters.md)
[`add_meta`](https://docs.ropensci.org/RNeXML/reference/add_meta.md)
[`add_namespaces`](https://docs.ropensci.org/RNeXML/reference/add_namespaces.md)
