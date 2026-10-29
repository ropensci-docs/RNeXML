# validate nexml using the online validator tool

validate nexml using the online validator tool

## Usage

``` r
nexml_validate(
  file,
  schema = system.file("xsd/nexml.xsd", package = "RNeXML"),
  local = TRUE
)
```

## Arguments

- file:

  path to the nexml file to validate

- schema:

  URL of schema (for fallback method only, set by default).

- local:

  logical, if TRUE we skip the online validator and rely only on pure
  XML-schema validation. This may fail to detect invalid use of some
  semantic elements.

## Value

TRUE if the file is valid, FALSE or error message otherwise

## Details

Requires an internet connection if local=FALSE. see
http://www.nexml.org/nexml/phylows/validator for more information in
debugging invalid files

## Examples

``` r
if (FALSE) { # \dontrun{
data(bird.orders)
birds <- nexml_write(bird.orders, "birds_orders.xml")
nexml_validate("birds_orders.xml")
unlink("birds_orders.xml") # delete file to clean up
} # }
```
