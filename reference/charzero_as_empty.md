# Treats zero-length character vectors as empty strings

If the argument is a zero-length character vector (character(0)),
returns an empty string (which is a character vector of length 1).
Otherwise passes through the argument.

## Usage

``` r
charzero_as_empty(x)
```

## Arguments

- x:

  the object to be tested for zero-length character vector

## Value

an empty string if `x` is a character vector of length zero, and `x`
otherwise
