# Class representing a NeXML document

The `nexml` class represents a NeXML document, and is the top of the
class hierarchy defined in this package, corresponding to the root node
of the corresponding XML document.

## Details

Normally objects of this type are created by the package as a result of
reading a NeXML file, or of converting from another type, such as
[`ape::phylo`](https://rdrr.io/pkg/ape/man/read.tree.html). Also,
interacting directly with the slots of the class is normally not
necessary. Instead, use the `get_XXX()` and `add_XXX()` functions in the
API.

## Slots

- `trees`:

  list, corresponding to the list of `<trees/>` elements in NeXML.
  Elements will be of class `trees`.

- `characters`:

  list, corresponding to the list of `<characters/>` elements in NeXML.
  Elements will be of class `characters`.

- `otus`:

  list, corresponding to the list of `<otus/>` elements in NeXML.
  Elements will be of class `otus`.

- `about`:

  inherited, see
  [Annotated](https://docs.ropensci.org/RNeXML/reference/Annotated-class.md)

- `meta`:

  inherited, see
  [Annotated](https://docs.ropensci.org/RNeXML/reference/Annotated-class.md)

- `xsi:type`:

  for internal use

- `version`:

  NeXML schema version, do not change

- `generator`:

  name of software generating the XML

- `xsi:schemaLocation`:

  for internal use, do not change

- `namespaces`:

  named character vector giving the XML namespaces

## See also

[`read.nexml()`](https://docs.ropensci.org/RNeXML/reference/nexml_read.md)

## Examples

``` r
nex <- nexml() # a nexml object with no further content
nex <- new("nexml") # accomplishes the same thing
nex@generator
#> [1] "RNeXML"
length(nex@trees)
#> [1] 0

data(bird.orders)
nex <- as(bird.orders, "nexml")
summary(nex)
#> $nblocks
#>      trees       otus characters 
#>          1          1          0 
#> 
#> $ncharacters
#> integer(0)
#> 
#> $nstates
#> integer(0)
#> 
#> $nnonstdstatedefs
#>      polymorphic uncertain
#> 
#> $nmatrixrows
#> integer(0)
#> 
#> $ntrees
#> block.1 
#>       1 
#> 
#> $notus
#> block.1 
#>      23 
#> 
#> $nmeta
#> $nmeta$nexml
#> [1] 0
#> 
#> $nmeta$otu
#> block.1 
#>       0 
#> 
#> $nmeta$char
#> integer(0)
#> 
#> $nmeta$state
#> integer(0)
#> 
#> 
length(nex@trees)
#> [1] 1
```
