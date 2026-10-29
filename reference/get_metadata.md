# get_metadata

get_metadata

## Usage

``` r
get_metadata(nexml, level = "nexml", simplify = TRUE)
```

## Arguments

- nexml:

  a nexml object

- level:

  the name of the level of element desired, see details

- simplify:

  logical, see Details

## Value

the requested metadata as a data.frame. Additional columns indicate the
parent element of the return value.

## Details

'level' should be either the name of a child element of a NeXML document
(e.g. "otu", "characters"), or a path to the desired element, e.g.
'trees/tree' will return the metadata for all phylogenies in all trees
blocks.

If a metadata element has other metadata elements nested within it, the
nested metadata are returned as well. A column "Meta" will contain the
IDs consolidated from the type-specific LiteralMeta and ResourceMeta
columns, and IDs are generated for meta elements that have nested
elements but do not have an ID ("blank nodes"). A column "meta" contains
the IDs of the parent meta elements for nested ones. This means that the
resulting table can be self-joined on those columns.

If `simplify` is `FALSE`, the type-specific "LiteralMeta" and
"ResourceMeta" columns will be retained even if a consolidated "Meta"
column is present. Otherwise, only the consolidated column will be
included in the result. Also, if `simplify` is `TRUE` the values for
"property" (LiteralMeta) and "rel" (ResourceMeta) will be consolidated
to "property", and "rel" will be removed from the result.

## Examples

``` r
if (FALSE) { # \dontrun{
comp_analysis <- system.file("examples", "primates.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_metadata(nex)
get_metadata(nex, "otus/otu")
} # }
```
