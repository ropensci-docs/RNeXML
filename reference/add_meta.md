# Add metadata to a nexml file

Add metadata to a nexml file

## Usage

``` r
add_meta(
  meta,
  nexml = new("nexml"),
  level = c("nexml", "otus", "trees", "characters"),
  namespaces = NULL,
  i = 1,
  at_id = NULL
)
```

## Arguments

- meta:

  a meta S4 object, e.g. ouput of the function
  [`meta`](https://docs.ropensci.org/RNeXML/reference/meta.md), or a
  list of these meta objects

- nexml:

  (S4) object

- level:

  the level at which the metadata annotation should be added.

- namespaces:

  named character string for any additional namespaces that should be
  defined.

- i:

  for otus, trees, characters: if there are multiple such blocks, which
  one should be annotated? Default is first/only block.

- at_id:

  the id of the element to be annotated. Optional, advanced use only.

## Value

the updated nexml object

## See also

[`meta`](https://docs.ropensci.org/RNeXML/reference/meta.md)
[`add_trees`](https://docs.ropensci.org/RNeXML/reference/add_trees.md)
[`add_characters`](https://docs.ropensci.org/RNeXML/reference/add_characters.md)
[`add_basic_meta`](https://docs.ropensci.org/RNeXML/reference/add_basic_meta.md)

## Examples

``` r
## Create a new nexml object with a single metadata element: 
modified <- meta(property = "prism:modificationDate", content = "2013-10-04")
nex <- add_meta(modified) # Note: 'prism' is defined in nexml_namespaces by default.  

## Write multiple metadata elements, including a new namespace:  
website <- meta(href = "http://carlboettiger.info", 
                rel = "foaf:homepage")              # meta can be link-style metadata
nex <- add_meta(list(modified,  website), 
                namespaces = c(foaf = "http://xmlns.com/foaf/0.1/"))

## Append more metadata, and specify a level: 
history <- meta(property = "skos:historyNote",
                 content = "Mapped from the bird.orders data in the ape package using RNeXML")
data(bird.orders)
nex <- add_trees(bird.orders) # need to have created a trees block first
nex <- add_meta(history, 
                nexml = nex,
                level = "trees",
                namespaces = c(skos = "http://www.w3.org/2004/02/skos/core#"))
```
