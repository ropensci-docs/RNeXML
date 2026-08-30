# Concatenate meta elements into a ListOfmeta

Concatenate meta elements into a ListOfmeta

Concatenate ListOfmeta elements into a flat ListOfmeta

## Usage

``` r
# S4 method for class 'meta'
c(x, ..., recursive = TRUE)

# S4 method for class 'ListOfmeta'
c(x, ..., recursive = TRUE)
```

## Arguments

- x, ...:

  `meta` and `ListOfmeta` elements to be concatenated, see
  [`meta`](https://docs.ropensci.org/RNeXML/reference/meta.md)

- recursive:

  logical, if 'recursive=TRUE', the function recursively descends
  through lists and combines their elements into a flat vector. This
  method does not support `recursive=FALSE`, use
  [list](https://rdrr.io/r/base/list.html) instead.

## Value

a ListOfmeta object containing a flat list of meta elements.

## Examples

``` r
c(meta(content="example", property="dc:title"),
  meta(content="Carl", property="dc:creator"))
#> An object of class "ListOfmeta"
#> [[1]]
#> An object of class "LiteralMeta"
#> Slot "id":
#> [1] "m26"
#> 
#> Slot "property":
#> [1] "dc:title"
#> 
#> Slot "datatype":
#> [1] "xsd:string"
#> 
#> Slot "content":
#> [1] "example"
#> 
#> Slot "children":
#> list()
#> 
#> Slot "xsi:type":
#> [1] "LiteralMeta"
#> 
#> 
#> [[2]]
#> An object of class "LiteralMeta"
#> Slot "id":
#> [1] "m27"
#> 
#> Slot "property":
#> [1] "dc:creator"
#> 
#> Slot "datatype":
#> [1] "xsd:string"
#> 
#> Slot "content":
#> [1] "Carl"
#> 
#> Slot "children":
#> list()
#> 
#> Slot "xsi:type":
#> [1] "LiteralMeta"
#> 
#> 
#> Slot "names":
#> [1] NA NA
#> 
metalist <- c(meta(content="example", property="dc:title"),
              meta(content="Carl", property="dc:creator"))
out <- c(metalist, metalist) 
out <- c(metalist, meta(content="a", property="b")) 
```
