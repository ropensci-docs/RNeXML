# Extract the character matrix

Extract the character matrix

## Usage

``` r
get_characters_list(nexml, rownames_as_col = FALSE)
```

## Arguments

- nexml:

  nexml object (e.g. from read.nexml)

- rownames_as_col:

  option to return character matrix rownames (with taxon ids) as it's
  own column in the data.frame. Default is FALSE for compatibility with
  geiger and similar packages.

## Value

the list of taxa

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_characters_list(nex)
#> $cs15
#>          <NA> log snout-vent length
#> taxon_8  ou10            -3.2777799
#> taxon_9  ou11             2.0959433
#> taxon_10 ou12             3.1373971
#> taxon_1   ou3             4.7532824
#> taxon_2   ou4            -2.7624146
#> taxon_3   ou5             2.1049413
#> taxon_4   ou6            -4.9504770
#> taxon_5   ou7             1.2714718
#> taxon_6   ou8             6.2593966
#> taxon_7   ou9             0.9099634
#> 
#> $cs31
#>          reef-dwelling
#> taxon_8              0
#> taxon_9              1
#> taxon_10             0
#> taxon_1              1
#> taxon_2              0
#> taxon_3              0
#> taxon_4              0
#> taxon_5              1
#> taxon_6              1
#> taxon_7              1
#> 
```
