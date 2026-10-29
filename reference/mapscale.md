# Map scale (1 : N)

Determines the map scale at a specified latitude, zoom level, and screen
resolution. For further information, refer to the Microsoft Bing Maps
Tile System documentation.

## Usage

``` r
mapscale(latitude, zoom, screen_dpi)
```

## Arguments

- latitude:

  Latitude (in degrees) at which to measure the map scale.

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

- screen_dpi:

  Resolution of the screen, in dots per inch.

## Value

The map scale, expressed as the denominator N of the ratio 1 : N.

## References

<https://learn.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system>

## Examples

``` r

mapscale(
  latitude = 0,
  zoom = 6,
  screen_dpi = 96
)
#> [1] 9244667

```
