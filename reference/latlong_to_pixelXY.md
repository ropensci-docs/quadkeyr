# Convert lat/long coordinates to pixel XY coordinates

Converts a point from latitude/longitude WGS-84 coordinates (in degrees)
into pixel XY coordinates at a specified zoom level. For further
information, refer to the Microsoft Bing Maps Tile System documentation.

## Usage

``` r
latlong_to_pixelXY(lat, lon, zoom)
```

## Arguments

- lat:

  Latitude of the point, in degrees.

- lon:

  Longitude of the point, in degrees.

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

A list returning pixel X and pixel Y coordinates.

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

## Examples

``` r

latlong_to_pixelXY(
  lat = -35,
  lon = -50,
  zoom = 6
)
#> $pixelX
#> [1] 5916
#> 
#> $pixelY
#> [1] 9894
#> 
```
