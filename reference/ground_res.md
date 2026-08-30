# Ground resolution at a specified latitude and zoom level

Determines the ground resolution (in meters per pixel) at a specified
latitude and zoom level. For further information, refer to the Microsoft
Bing Maps Tile System documentation.

## Usage

``` r
ground_res(latitude, zoom)
```

## Arguments

- latitude:

  Latitude (in degrees) at which to measure the ground resolution.

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

the ground resolution (meters / pixel)

## References

<https://learn.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system>

## Examples

``` r

ground_res(
  latitude = 0,
  zoom = 6
)
#> [1] 2445.985
```
