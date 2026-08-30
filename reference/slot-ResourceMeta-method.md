# Access or set slot of S4 object

See [`methods::slot()`](https://rdrr.io/r/methods/slot.html). This
version allows using "property" consistently for both LiteralMeta and
ResourceMeta (which internally uses "rel" because RDFa does), which is
easier to program. It also allows using "meta" as an alias for
"children" for ResourceMeta, to be consistent with the corresponding
slot for instances of `Annotated`.

## Usage

``` r
# S4 method for class 'ResourceMeta'
slot(object, name)

# S4 method for class 'ResourceMeta'
slot(object, name) <- value
```

## Arguments

- object:

  the object

- name:

  name of the slot

- value:

  the new value

## See also

[`methods::slot()`](https://rdrr.io/r/methods/slot.html)
