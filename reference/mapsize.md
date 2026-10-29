# Map size in pixels

Determines the map width and height (in pixels) at a specified zoom
level. For further information, refer to the Microsoft Bing Maps Tile
System documentation.

## Usage

``` r
mapsize(zoom)
```

## Arguments

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

The map width and height in pixels.

## References

<https://learn.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system>

## Examples

``` r

mapsize(zoom = 6)
#> [1] 16384
```
