# get_taxa

Retrieve names of all species/otus otus (operational taxonomic units)
included in the nexml

## Usage

``` r
get_taxa(nexml)
```

## Arguments

- nexml:

  a nexml object

## Value

the list of taxa

## See also

[`get_item`](https://docs.ropensci.org/RNeXML/reference/nexml_get.md)

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_taxa(nex)
#>             otu    label xsi.type otus
#> label...1   ou3  taxon_1       NA  os2
#> label...2   ou4  taxon_2       NA  os2
#> label...3   ou5  taxon_3       NA  os2
#> label...4   ou6  taxon_4       NA  os2
#> label...5   ou7  taxon_5       NA  os2
#> label...6   ou8  taxon_6       NA  os2
#> label...7   ou9  taxon_7       NA  os2
#> label...8  ou10  taxon_8       NA  os2
#> label...9  ou11  taxon_9       NA  os2
#> label...10 ou12 taxon_10       NA  os2
```
