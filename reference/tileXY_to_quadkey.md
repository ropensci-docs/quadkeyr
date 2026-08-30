# Convert tile XY coordinates into a QuadKey.

Converts tile XY coordinates into a QuadKey at a specified zoom level.
For further information, refer to the Microsoft Bing Maps Tile System
documentation.

## Usage

``` r
tileXY_to_quadkey(tileX, tileY, zoom)
```

## Arguments

- tileX:

  Tile X coordinate.

- tileY:

  Tile Y coordinate.

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

The QuadKey as a string.

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

tileXY_to_quadkey(
  tileX = 23,
  tileY = 38,
  zoom = 6
)
#> [1] "210331"
```
