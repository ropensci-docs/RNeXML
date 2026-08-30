# Write nexml files

Write nexml files

## Usage

``` r
nexml_write(
  x = nexml(),
  file = NULL,
  trees = NULL,
  characters = NULL,
  meta = NULL,
  ...
)
```

## Arguments

- x:

  a nexml object, or any phylogeny object (e.g. phylo, phylo4) that can
  be coerced into one. Can also be omitted, in which case a new nexml
  object will be constructed with the additional parameters specified.

- file:

  the name of the file to write out

- trees:

  phylogenetic trees to add to the nexml file (if not already given
  in x) see
  [`add_trees`](https://docs.ropensci.org/RNeXML/reference/add_trees.md)
  for details.

- characters:

  additional characters

- meta:

  A meta element or list of meta elements, see
  [`add_meta`](https://docs.ropensci.org/RNeXML/reference/add_meta.md)

- ...:

  additional arguments to add\_\_basic_meta, such as the title. See
  [`add_basic_meta`](https://docs.ropensci.org/RNeXML/reference/add_basic_meta.md).

## Value

Writes out a nexml file

## See also

[`add_trees`](https://docs.ropensci.org/RNeXML/reference/add_trees.md)
[`add_characters`](https://docs.ropensci.org/RNeXML/reference/add_characters.md)
[`add_meta`](https://docs.ropensci.org/RNeXML/reference/add_meta.md)
[`nexml_read`](https://docs.ropensci.org/RNeXML/reference/nexml_read.md)

## Examples

``` r
 ## Write an ape tree to nexml, analgous to write.nexus:
 library(ape); data(bird.orders)
 ex <- tempfile(fileext=".xml")
 write.nexml(bird.orders, file=ex)
#> [1] "/tmp/RtmpDZ5JZn/file65578297a7e.xml"
```
