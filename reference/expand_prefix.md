# Expand namespace-prefixed string

Substitutes the namespace prefix in the input vector of strings with the
corresponding namespaces.

## Usage

``` r
expand_prefix(x, namespaces = NULL)
```

## Arguments

- x:

  a character vector of potentially namespace-prefixed strings

- namespaces:

  a named vector of namespaces, with namespace prefixes being the names.
  A "base" namespace with an empty name can be included. If not
  provided, or if empty, the input vector is returned as is.

## Value

a character vector, of the same length as the input vector

## Details

Namespace prefixes are expected to be separated by one or more
semicolons. Prefixes that cannot be matched to the vector of namespaces
will be left as is. For strings that do not have a namespace prefix, the
vector of namespaces can contain a base namespace, identified as not
having a name, with which these strings will be expanded.

## Examples

``` r
uris <- c("cc:license", "dc:title")
ns <- c(dc = "http://purl.org/dc/elements/1.1/",
        dcterms = "http://purl.org/dc/terms/",
        dct = "http://purl.org/dc/terms/",
        cc = "http://creativecommons.org/ns#")
# expansion is vectorized
expand_prefix(uris, ns)
#> [1] "http://creativecommons.org/ns#license"
#> [2] "http://purl.org/dc/elements/1.1/title"

# strings with non-matching or no prefix are left as is
uris <- c(uris, "my:title", "title")
expand_prefix(uris, ns)
#> [1] "http://creativecommons.org/ns#license"
#> [2] "http://purl.org/dc/elements/1.1/title"
#> [3] "my:title"                             
#> [4] "title"                                

# NAs in the input list become NA in the output
uris <- c(uris, NA)
expand_prefix(uris, ns)
#> [1] "http://creativecommons.org/ns#license"
#> [2] "http://purl.org/dc/elements/1.1/title"
#> [3] "my:title"                             
#> [4] "title"                                
#> [5] NA                                     

# can include a "base" (unnamed) namespace for expanding unprefixed strings
ns <- c(ns, "//local/")
xuris <- expand_prefix(uris, ns)
xuris
#> [1] "http://creativecommons.org/ns#license"
#> [2] "http://purl.org/dc/elements/1.1/title"
#> [3] "my:title"                             
#> [4] "//local/title"                        
#> [5] NA                                     
xuris[uris == "title"] == paste0("//local/", uris[uris == "title"])
#> [1] TRUE   NA

# different prefixes may expand to the same result
expand_prefix("dcterms:modified", ns) == expand_prefix("dct:modified", ns)
#> [1] TRUE

# or they may result in different expansions
expand_prefix("dc:title", ns) != expand_prefix("dcterms:title", ns)
#> [1] TRUE
```
