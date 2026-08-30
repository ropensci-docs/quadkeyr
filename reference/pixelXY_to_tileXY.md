# Convert pixel XY coordinates into tile XY coordinates

Converts pixel XY coordinates into tile XY coordinates of the tile
containing the specified pixel. For further information, refer to the
Microsoft Bing Maps Tile System documentation.

## Usage

``` r
pixelXY_to_tileXY(pixelX, pixelY)
```

## Arguments

- pixelX:

  Pixel X coordinate.

- pixelY:

  Pixel Y coordinate.

## Value

A list returning the tile X and tile Y coordinates.

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

pixelXY_to_tileXY(
  pixelX = 5916,
  pixelY = 9894
)
#> $tileX
#> [1] 23
#> 
#> $tileY
#> [1] 38
#> 
```
