# Constructor function for metadata nodes

Constructor function for metadata nodes

## Usage

``` r
meta(
  property = NULL,
  content = NULL,
  rel = NULL,
  href = NULL,
  datatype = NULL,
  id = NULL,
  type = NULL,
  children = list()
)
```

## Arguments

- property:

  specify the ontological definition together with it's namespace, e.g.
  dc:title

- content:

  content of the metadata field

- rel:

  Ontological definition of the reference provided in href

- href:

  A link to some reference

- datatype:

  optional RDFa field

- id:

  optional id element (otherwise id will be automatically generated).

- type:

  optional xsi:type. If not given, will use either "LiteralMeta" or
  "ResourceMeta" as determined by the presence of either a property or a
  href value.

- children:

  Optional element containing any valid XML block
  (XMLInternalElementNode class, see the XML package for details).

## Details

User must either provide property+content or rel+href. Mixing these will
result in potential garbage. The datatype attribute will be detected
automatically from the class of the content argument. Maps from R class
to schema datatypes are as follows: character - xs:string, Date -
xs:date, integer - xs:integer, numeric - xs:decimal, logical -
xs:boolean

## See also

[`nexml_write`](https://docs.ropensci.org/RNeXML/reference/nexml_write.md)

## Examples

``` r
meta(content="example", property="dc:title")
#> An object of class "LiteralMeta"
#> Slot "id":
#> [1] "m31"
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
```
