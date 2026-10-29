# Create grid of QuadKeys for a particular zoom or level of detail.

Generates a grid comprising all the QuadKeys within the area defined by
the maximum and minimum coordinates of latitude and longitude along with
a specified zoom level.

## Usage

``` r
create_qk_grid(xmin, xmax, ymin, ymax, zoom)
```

## Arguments

- xmin:

  Minimum value in the x axis (longitude)

- xmax:

  Maximum value in the y axis (latitude)

- ymin:

  Minimum value in the x axis (longitude)

- ymax:

  Maximum value in the Y axis (latitude)

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

A list returning the QuadKeys as a data.frame (`data`), the number of
rows (`num_rows`) and columns (`num_cols`) of the grid.

## Examples

``` r

grid <- create_qk_grid(
  xmin = -59,
  xmax = -57,
  ymin = -35,
  ymax = -34,
  zoom = 12
)
```
