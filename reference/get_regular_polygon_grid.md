# Get regular QuadKey polygon grid derived from the bounding box of the `quadkey` column of a data.frame.

This function estimates the bounding box of the QuadKeys given in the
`quadkey` column and adds the rows needed to complete a regular grid.

For a detailed explanation on how to use this and other similar
`quadkeyr` functions, read the the vignette:
<https://docs.ropensci.org/quadkeyr/articles/facebook_mobility_csvs_to_raster_files.html>

## Usage

``` r
get_regular_polygon_grid(data)
```

## Arguments

- data:

  A data.frame with a `quadkey` column.

## Value

A list with three elements:

- `data` An `sf` POLYGON data.frame with all the QuadKeys within the
  bounding box of the `quadkey` column of a data.frame. Only the columns
  `quadkey`, `tileX`, `tileY` and `geometry` are returned.

- `num_rows` The number of columns of the regular grid.

- `num_cols` The number of rows of the regular grid.

## Examples

``` r
# \donttest{
# Data File
path <- paste0(
  system.file("extdata", package = "quadkeyr"),
  "/cityA_2020_04_15_0000.csv"
)
data <- read.csv(path)
data <- format_fb_data(data)

get_regular_polygon_grid(data = data)
#> $data
#> Simple feature collection with 396 features and 3 fields
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -58.60107 ymin: -34.60156 xmax: -58.5022 ymax: -34.50203
#> Geodetic CRS:  WGS 84
#> # A tibble: 396 × 4
#> # Rowwise: 
#>    quadkey                                                  geometry tileX tileY
#>  * <chr>                                               <POLYGON [°]> <dbl> <dbl>
#>  1 2103213001233302 ((-58.55713 -34.588, -58.55164 -34.588, -58.551… 22108 39485
#>  2 2103213001213202 ((-58.5791 -34.51561, -58.57361 -34.51561, -58.… 22104 39469
#>  3 2103213001233221 ((-58.57361 -34.59252, -58.56812 -34.59252, -58… 22105 39486
#>  4 2103213001231110 ((-58.54614 -34.52919, -58.54065 -34.52919, -58… 22110 39472
#>  5 2103213001320003 ((-58.52966 -34.53371, -58.52417 -34.53371, -58… 22113 39473
#>  6 2103213001230110 ((-58.59009 -34.52919, -58.58459 -34.52919, -58… 22102 39472
#>  7 2103213001212321 ((-58.59558 -34.52014, -58.59009 -34.52014, -58… 22101 39470
#>  8 2103213001232302 ((-58.60107 -34.588, -58.59558 -34.588, -58.595… 22100 39485
#>  9 2103213001322012 ((-58.52417 -34.56991, -58.51868 -34.56991, -58… 22114 39481
#> 10 2103213001230320 ((-58.60107 -34.55634, -58.59558 -34.55634, -58… 22100 39478
#> # ℹ 386 more rows
#> 
#> $num_cols
#> [1] 18
#> 
#> $num_rows
#> [1] 22
#> 
# }
```
