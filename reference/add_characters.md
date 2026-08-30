# Add character data to a nexml object

Add character data to a nexml object

## Usage

``` r
add_characters(x, nexml = new("nexml"), append_to_existing_otus = FALSE)
```

## Arguments

- x:

  character data, in which character traits labels are column names and
  taxon labels are row names. x can be in matrix or data.frame format.

- nexml:

  a nexml object, if appending character table to an existing nexml
  object. If omitted will initiate a new nexml object.

- append_to_existing_otus:

  logical. If TRUE, will add any new taxa (taxa not matching any
  existing otus block) to the existing (first) otus block. Otherwise
  (default), a new otus block is created, even though it may contain
  duplicate taxa to those already present. While FALSE is the safe
  option, TRUE may be appropriate when building nexml files from scratch
  with both characters and trees.
