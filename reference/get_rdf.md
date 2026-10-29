# Extract rdf-xml from a NeXML file

Extract rdf-xml from a NeXML file

## Usage

``` r
get_rdf(file)
```

## Arguments

- file:

  the name of a nexml file, or otherwise a nexml object.

## Value

an RDF-XML object (XMLInternalDocument). This can be manipulated with
tools from the XML R package, or converted into a triplestore for use
with SPARQL queries from the rdflib R package.
