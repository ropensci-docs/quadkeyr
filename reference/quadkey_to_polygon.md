# Convert a QuadKey into a square polygon

This functions creates a `sf` POLYGON data.frame from a QuadKey string.

## Usage

``` r
quadkey_to_polygon(quadkey)
```

## Arguments

- quadkey:

  The QuadKey as a string

## Value

A `sf` POLYGON data.frame with a `quadkey` and `geometry` column.

## See also

[`quadkey_df_to_polygon`](https://docs.ropensci.org/quadkeyr/reference/quadkey_df_to_polygon.md)

## Examples

``` r

# Quadkey as string
quadkey_to_polygon(quadkey = "213")
#> Simple feature collection with 1 feature and 1 field
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -45 ymin: -66.51326 xmax: 0 ymax: -40.9799
#> Geodetic CRS:  WGS 84
#>   quadkey                       geometry
#> 1     213 POLYGON ((-45 -66.51326, 0 ...

# QuadKeys as column in a data.frame
# get data file
path <- paste0(
  system.file("extdata", package = "quadkeyr"),
  "/cityA_2020_04_15_0000.csv"
)
data <- read.csv(path)
data <- format_fb_data(data)

quadkey_df_to_polygon(data = data)
#> Simple feature collection with 150 features and 9 fields
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -58.60107 ymin: -34.60156 xmax: -58.5022 ymax: -34.50203
#> Geodetic CRS:  WGS 84
#> First 10 features:
#>     X       lat       lon          quadkey  date_time n_crisis percent_change
#> 1   1 -34.58574 -58.55438 2103213001233302 2020-04-15       NA      2.8639400
#> 2   2 -34.51335 -58.57635 2103213001213202 2020-04-15       NA     -2.6009911
#> 3   3 -34.59026 -58.57086 2103213001233221 2020-04-15       NA      1.4601414
#> 4   4 -34.52692 -58.54340 2103213001231110 2020-04-15       NA      2.6076928
#> 5   5 -34.53145 -58.52692 2103213001320003 2020-04-15       NA      3.2428621
#> 6   6 -34.52692 -58.58734 2103213001230110 2020-04-15       NA      1.1728565
#> 7   7 -34.51787 -58.59283 2103213001212321 2020-04-15 13.07492     -0.3100404
#> 8   8 -34.58574 -58.59833 2103213001232302 2020-04-15       NA     11.4323758
#> 9   9 -34.56764 -58.52142 2103213001322012 2020-04-15       NA    -18.2960744
#> 10 10 -34.55407 -58.59833 2103213001230320 2020-04-15       NA    -15.7189196
#>           day hour                       geometry
#> 1  2020-04-15   NA POLYGON ((-58.55713 -34.588...
#> 2  2020-04-15   NA POLYGON ((-58.5791 -34.5156...
#> 3  2020-04-15   NA POLYGON ((-58.57361 -34.592...
#> 4  2020-04-15   NA POLYGON ((-58.54614 -34.529...
#> 5  2020-04-15   NA POLYGON ((-58.52966 -34.533...
#> 6  2020-04-15   NA POLYGON ((-58.59009 -34.529...
#> 7  2020-04-15   NA POLYGON ((-58.59558 -34.520...
#> 8  2020-04-15   NA POLYGON ((-58.60107 -34.588...
#> 9  2020-04-15   NA POLYGON ((-58.52417 -34.569...
#> 10 2020-04-15   NA POLYGON ((-58.60107 -34.556...
```
