# publish nexml files to the web and receive a DOI

publish nexml files to the web and receive a DOI

## Usage

``` r
nexml_publish(nexml, ..., repository = "figshare")
```

## Arguments

- nexml:

  a nexml object (or file path)

- ...:

  additional arguments, depending on repository. See examples.

- repository:

  destination repository

## Value

a digital object identifier to the published data

## Examples

``` r
if (FALSE) { # \dontrun{
data(bird.orders)
birds <- add_trees(bird.orders)
doi <- nexml_publish(birds, visibility = "public", repository="figshare")
} # }
```
