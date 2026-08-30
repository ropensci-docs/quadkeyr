# Add the rows needed to complete a regular QuadKey polygon grid derived from the bounding box of the `quadkey` column of a data.frame.

This function estimates the bounding box of the quadkeys given in the
quadkey column and adds rows to complete the quadkeys and the geometry
needed to create a regular grid. All other columns for the introduced
QuadKeys will be filled with NAs.

For a detailed explanation on how to use this and other similar
`quadkeyr` functions, read the the vignette:
<https://docs.ropensci.org/quadkeyr/articles/quadkey_identified_data_to_raster.html>

## Usage

``` r
add_regular_polygon_grid(data)
```

## Arguments

- data:

  A data.frame with a `quadkey` column.

## Value

A list with three elements:

- `data` A `sf` POLYGON data.frame with all the QuadKeys within the
  bounding box of the ones provided in the `quadkey` column of the input
  dataset, and the rest of the original variables. The columns `quadkey`
  and `geometry` are returned for all the grid, The values of the newly
  added QuadKeys will be NA for the rest of the variables.

- `num_rows` The number of columns of the regular grid.

- `num_cols` The number of rows of the regular grid.

## Examples

``` r
# \donttest{
# Read the file with the data
path <- paste0(
  system.file("extdata", package = "quadkeyr"),
  "/cityA_2020_04_15_0000.csv"
)
data <- read.csv(path)
data <- format_fb_data(data)

add_regular_polygon_grid(data = data)
#> $data
#> Simple feature collection with 396 features and 9 fields
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -58.60107 ymin: -34.60156 xmax: -58.5022 ymax: -34.50203
#> Geodetic CRS:  WGS 84
#> # A tibble: 396 × 10
#>    quadkey      X date_time n_crisis percent_change day         hour tileX tileY
#>  * <chr>    <dbl> <chr>        <dbl>          <dbl> <date>     <dbl> <dbl> <dbl>
#>  1 2103213…   150 2020-04-…     NA            2.29  2020-04-15    NA 22112 39481
#>  2 2103213…   149 2020-04-…    212.           0.848 2020-04-15    NA 22114 39472
#>  3 2103213…   148 2020-04-…     NA           28.4   2020-04-15    NA 22109 39488
#>  4 2103213…   147 2020-04-…    179.           3.75  2020-04-15    NA 22102 39467
#>  5 2103213…   146 2020-04-…     20.3          2.81  2020-04-15    NA 22106 39487
#>  6 2103213…   145 2020-04-…     NA          -12.8   2020-04-15    NA 22108 39468
#>  7 2103213…   144 2020-04-…    127.          -5.37  2020-04-15    NA 22108 39470
#>  8 2103213…   143 2020-04-…     NA            6.60  2020-04-15    NA 22116 39482
#>  9 2103213…   142 2020-04-…     NA            3.16  2020-04-15    NA 22116 39485
#> 10 2103213…   141 2020-04-…     NA           -2.84  2020-04-15    NA 22108 39480
#> # ℹ 386 more rows
#> # ℹ 1 more variable: geometry <POLYGON [°]>
#> 
#> $num_cols
#> [1] 18
#> 
#> $num_rows
#> [1] 22
#> 
# }
```
