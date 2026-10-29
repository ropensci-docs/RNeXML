# get namespaces

get namespaces

## Usage

``` r
get_namespaces(nexml)
```

## Arguments

- nexml:

  a nexml object

## Value

a named character vector providing the URLs defining each of the
namespaces used in the nexml file. Names correspond to the prefix
abbreviations of the namespaces.

## Examples

``` r
comp_analysis <- system.file("examples", "comp_analysis.xml", package="RNeXML")
nex <- nexml_read(comp_analysis)
get_namespaces(nex)
#>                                                  
#>                      "http://www.nexml.org/2009" 
#>                                               dc 
#>               "http://purl.org/dc/elements/1.1/" 
#>                                              map 
#>          "http://purl.org/phylo/phylomap/terms#" 
#>                                              nex 
#>                      "http://www.nexml.org/2009" 
#>                                              rdf 
#>    "http://www.w3.org/1999/02/22-rdf-syntax-ns#" 
#>                                              xsd 
#>              "http://www.w3.org/2001/XMLSchema#" 
#>                                              xsi 
#>      "http://www.w3.org/2001/XMLSchema-instance" 
#>                                              xml 
#>           "http://www.w3.org/XML/1998/namespace" 
#>                                             cdao 
#>                "http://purl.obolibrary.org/obo/" 
#>                                          dcterms 
#>                      "http://purl.org/dc/terms/" 
#>                                            prism 
#> "http://prismstandard.org/namespaces/1.2/basic/" 
#>                                               cc 
#>                 "http://creativecommons.org/ns#" 
#>                                             ncbi 
#>          "http://www.ncbi.nlm.nih.gov/taxonomy#" 
#>                                               tc 
#>  "http://rs.tdwg.org/ontology/voc/TaxonConcept#" 
```
