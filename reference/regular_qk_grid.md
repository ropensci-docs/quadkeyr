# Convert a incomplete QuadKey `sf` POINT data.frame into a regular grid.

This function completes `sf` POINT data.frame grid of QuadKeys using the
bounding box of the data provided.

## Usage

``` r
regular_qk_grid(data)
```

## Arguments

- data:

  A `sf` POINT data.frame

## Value

A list with three elements:

- `data` A `sf` POINT data.frame, with the rows needed to complete the
  grid.

- `num_rows` The number of columns of the regular grid.

- `num_cols` The number of rows of the regular grid.

## See also

[`create_qk_grid`](https://docs.ropensci.org/quadkeyr/reference/create_qk_grid.md)

[`quadkey_to_latlong`](https://docs.ropensci.org/quadkeyr/reference/quadkey_to_latlong.md)

## Examples

``` r

quadkey_vector <- c("213", "210", "211")

qtll <- quadkey_to_latlong(quadkey = quadkey_vector)

regular_qk_grid(qtll)
#> $data
#> Simple feature collection with 4 features and 1 field
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -90 ymin: -40.9799 xmax: -45 ymax: 0
#> Geodetic CRS:  WGS 84
#>    quadkey             geometry
#> 1      212 POINT (-90 -40.9799)
#> 3      211        POINT (-45 0)
#> 2      210        POINT (-90 0)
#> 11     213 POINT (-45 -40.9799)
#> 
#> $num_rows
#> [1] 2
#> 
#> $num_cols
#> [1] 2
#> 
```
