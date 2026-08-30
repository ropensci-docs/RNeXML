# Flatten a multiphylo object

Flatten a multiphylo object

## Usage

``` r
flatten_multiphylo(object)
```

## Arguments

- object:

  a list of multiphylo objects

## Details

NeXML has the concept of multiple `<trees>` nodes, each with multiple
child `<tree>` nodes. This maps naturally to a list of multiphylo
objects. Sometimes this hierarchy conveys important structural
information, so it is not discarded by default. Occasionally it is
useful to flatten the structure though, hence this function. Note that
this discards the original structure, and the nexml file must be parsed
again to recover it.
