# Convert a QuadKey into tile XY coordinates.

For further information, refer to the Microsoft Bing Maps Tile System
documentation.

## Usage

``` r
quadkey_to_tileXY(quadkey)
```

## Arguments

- quadkey:

  A QuadKey as a single string.

## Value

A list returning the tile X, tile Y coordinates and the zoom level.

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

quadkey_to_tileXY(quadkey = "213")
#> $tileX
#> [1] 3
#> 
#> $tileY
#> [1] 5
#> 
#> $zoom
#> [1] 3
#> 
```
