# Front-end to dplyr::coalesce to deal with NULL vectors

Replaces any NULL argument with a vector of `NA`, and casts every vector
to the same type as the last vector. After that, calls
[`dplyr::coalesce()`](https://dplyr.tidyverse.org/reference/coalesce.html).

## Usage

``` r
coalesce_(...)
```

## Arguments

- ...:

  the vectors to coalesce on NA

## Value

a vector of the same type and length as the last argument

## See also

[`dplyr::coalesce()`](https://dplyr.tidyverse.org/reference/coalesce.html)
