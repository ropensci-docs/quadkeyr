# Convert tile XY coordinates into pixel XY coordinates

Converts tile XY coordinates into pixel XY coordinates of the upper-left
pixel of the specified tile. For further information, refer to the
Microsoft Bing Maps Tile System documentation.

## Usage

``` r
tileXY_to_pixelXY(tileX, tileY)
```

## Arguments

- tileX:

  Tile X coordinate.

- tileY:

  Tile Y coordinate.

## Value

A list returning the pixel X and pixel Y coordinates.

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

tileXY_to_pixelXY(
  tileX = 3,
  tileY = 5
)
#> $pixelX
#> [1] 768
#> 
#> $pixelY
#> [1] 1280
#> 
```
