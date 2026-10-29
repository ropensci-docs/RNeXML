# publish nexml to figshare

publish nexml to figshare

## Usage

``` r
nexml_figshare(
  nexml,
  file = "nexml.xml",
  categories = "Evolutionary Biology",
  tags = list("phylogeny", "NeXML"),
  visibility = c("public", "private", "draft"),
  id = NULL,
  ...
)
```

## Arguments

- nexml:

  a nexml object (or file path to a nexml file)

- file:

  The filename desired for the object, if nexml is not already a file.
  if the first argument is already a path, this value is ignored.

- categories:

  The figshare categories, must match available set. see
  `fs_add_categories`

- tags:

  Any keyword tags you want to add to the data.

- visibility:

  whether the results should be published (public), or kept private, or
  kept as a draft for further editing before publication. (New versions
  can be updated, but any former versions that was once made public will
  always be archived and cannot be removed).

- id:

  an existing figshare id (e.g. from fs_create), to which this file can
  be appended.

- ...:

  additional arguments

## Value

the figshare id of the object

## Examples

``` r
if (FALSE) { # \dontrun{
data(bird.orders)
birds <- add_trees(bird.orders)
doi <- nexml_figshare(birds, visibility = "public", repository="figshare")
} # }
```
