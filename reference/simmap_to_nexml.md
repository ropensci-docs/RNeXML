# Convert phylo with attached simmap to nexml object

Convert phylo with attached simmap to nexml object

Convert nexml object with simmap to phylo

## Usage

``` r
simmap_to_nexml(phy, state_ids = NULL)

nexml_to_simmap(nexml)
```

## Arguments

- phy:

  a phylo object containing simmap `phy$maps` element, from the phytools
  package

- state_ids:

  a named character vector giving the state names corresponding to the
  ids used to refer to each state in nexml. If null ids will be
  generated and states taken from the phy\$states names.

- nexml:

  a nexml object

## Value

a nexml representation of the simmap

a simmap object (phylo object with a `$maps` element for use in phytools
functions).

## Functions

- `nexml_to_simmap()`: Convert nexml object with simmap to phylo

## Examples

``` r
simmap_ex <- read.nexml(system.file("examples","simmap_ex.xml", package="RNeXML"))
phy <- nexml_to_simmap(simmap_ex)
nex <- simmap_to_nexml(phy) 
```
