# Concatenate nexml files

Concatenate nexml files

## Usage

``` r
# S4 method for class 'nexml'
c(x, ..., recursive = FALSE)
```

## Arguments

- x, ...:

  nexml objects to be concatenated, e.g. from
  [`write.nexml`](https://docs.ropensci.org/RNeXML/reference/nexml_write.md)
  or
  [`read.nexml`](https://docs.ropensci.org/RNeXML/reference/nexml_read.md).
  Must have unique ids on all elements

- recursive:

  logical. If 'recursive = TRUE', the function recursively descends
  through lists (and pairlists) combining all their elements into a
  vector. (Not implemented).

## Value

a concatenated nexml file

## Examples

``` r
if (FALSE) { # \dontrun{
f1 <- system.file("examples", "trees.xml", package="RNeXML")
f2 <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex1 <- read.nexml(f1)
nex2 <- read.nexml(f2)
nex <- c(nex1, nex2)
} # }
```
