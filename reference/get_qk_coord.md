# Get lat/long coordinates from the QuadKey

Reads the QuadKey as a string and extracts the lat/long coordinates of
the upper-left corner of the QuadKey.

## Usage

``` r
get_qk_coord(data)
```

## Arguments

- data:

  A dataframe with a quadkey column.

## Value

A `sf` POINT data.frame containing the tiles XY coordinates (`tileX`,
`tileY`), the QuadKeys (`quadkey`), and a `geometry` column.

## See also

[`quadkey_to_tileXY`](https://docs.ropensci.org/quadkeyr/reference/quadkey_to_tileXY.md)

[`tileXY_to_pixelXY`](https://docs.ropensci.org/quadkeyr/reference/tileXY_to_pixelXY.md)

[`pixelXY_to_latlong`](https://docs.ropensci.org/quadkeyr/reference/pixelXY_to_latlong.md)

## Examples

``` r

grid <- create_qk_grid(
  xmin = -59,
  xmax = -40,
  ymin = -38,
  ymax = -20,
  zoom = 6
)

# quadkey column in grid$data converted to geographic coordinates
grid_coords <- get_qk_coord(data = grid$data)

plot(grid_coords)
```
