# Convert pixel XY coordinatess into lat/long coordinates.

Converts a pixel from pixel XY coordinates at a specified zoom level
into latitude/longitude WGS-84 coordinates (in degrees). For further
information, refer to the Microsoft Bing Maps Tile System documentation.

## Usage

``` r
pixelXY_to_latlong(pixelX, pixelY, zoom)
```

## Arguments

- pixelX:

  X coordinate of the point, in pixels.

- pixelY:

  Y coordinates of the point, in pixels.

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

A list with the longitude and latitude.

## Details

Converting latitude/longitude coordinates into a QuadKey and then back
to latitude/longitude won't yield identical values, unless the initial
latitude/longitude coordinates correspond to the upper-left QuadKey's
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

pixelXY_to_latlong(
  pixelX = 768,
  pixelY = 1280,
  zoom = 3
)
#> $lat
#> [1] -40.9799
#> 
#> $lon
#> [1] -45
#> 
```
