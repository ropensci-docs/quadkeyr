# Convert a string of Quadkey numbers to lat/long coordinates

This function converts Quadkeys to latitude/longitude WGS-84 coordinates
(in degrees). For further information, refer to the Microsoft Bing Maps
Tile System documentation.

## Usage

``` r
quadkey_to_latlong(quadkey_data)
```

## Arguments

- quadkey_data:

  A single QuadKey as a string or a vector with unique QuadKeys.

## Value

A sf POINT data.frame with a `quadkey` column. The latitude/longitude
coordinates represent the upper-left corner of the QuadKey.

## Details

Converting latitude/longitude coordinates into a QuadKey and then back
to latitude/longitude won't yield identical values, unless the initial
latitude/longitude coordinates correspond to the upper-left Quadkey's
pixel and tile XY coordinates at the same zoom level.

Understanding this distinction is crucial for the accurate use of these
functions in coordinate conversions.

For a detailed explanation on how to use this and other similar
`quadkeyr` functions, read the the vignette:
<https://docs.ropensci.org/quadkeyr/articles/quadkey_to_sf_conversion.html>

## References

<https://learn.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system>

## See also

[`quadkey_to_tileXY`](https://docs.ropensci.org/quadkeyr/reference/quadkey_to_tileXY.md)

[`tileXY_to_pixelXY`](https://docs.ropensci.org/quadkeyr/reference/tileXY_to_pixelXY.md)

[`pixelXY_to_latlong`](https://docs.ropensci.org/quadkeyr/reference/pixelXY_to_latlong.md)

## Examples

``` r

quadkey_to_latlong(quadkey_data = "213")
#> Simple feature collection with 1 feature and 1 field
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -45 ymin: -40.9799 xmax: -45 ymax: -40.9799
#> Geodetic CRS:  WGS 84
#>   quadkey             geometry
#> 1     213 POINT (-45 -40.9799)
quadkey_to_latlong(quadkey_data = c("213", "212", "210"))
#> Simple feature collection with 3 features and 1 field
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -90 ymin: -40.9799 xmax: -45 ymax: 0
#> Geodetic CRS:  WGS 84
#>   quadkey             geometry
#> 3     210        POINT (-90 0)
#> 2     212 POINT (-90 -40.9799)
#> 1     213 POINT (-45 -40.9799)
```
