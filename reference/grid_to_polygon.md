# Convert a grid of QuadKeys to square polygons

The main argument of this function, the grid of geographic coordinates
(lat/long WG84) represents the upper-left corner of the QuadKey. To
transform these coordinates into square polygons, the function
supplements the grid by adding a row and column of tiles. These points
introduce QuadKeys located at the border of the area using the internal
function `complete_grid_for_polygons()`. The function builds the
polygons using all the points of the grid. Note that it's possible to
associate each QuadKey with its square polygon.

## Usage

``` r
grid_to_polygon(data)
```

## Arguments

- data:

  A `sf` POINT data.frame with a `quadkey` and `geometry` column.

## Value

A sf POLYGON data.frame with a quadkey column.

## Examples

``` r
grid <- create_qk_grid(
  xmin = -59,
  xmax = -57,
  ymin = -35,
  ymax = -34,
  zoom = 11
)

grid_coords <- get_qk_coord(data = grid$data)

polygrid <- grid_to_polygon(grid_coords)
polygrid
#> Simple feature collection with 96 features and 3 fields
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -59.0625 ymin: -35.03 xmax: -56.95312 ymax: -33.87042
#> Geodetic CRS:  WGS 84
#> # A tibble: 96 × 4
#> # Rowwise: 
#>    tileX tileY quadkey                                                  geometry
#>  * <dbl> <dbl> <chr>                                               <POLYGON [°]>
#>  1   699  1229 21032113213 ((-57.12891 -34.01624, -56.95312 -34.01624, -56.9531…
#>  2   698  1229 21032113212 ((-57.30469 -34.01624, -57.12891 -34.01624, -57.1289…
#>  3   697  1229 21032113203 ((-57.48047 -34.01624, -57.30469 -34.01624, -57.3046…
#>  4   696  1229 21032113202 ((-57.65625 -34.01624, -57.48047 -34.01624, -57.4804…
#>  5   695  1229 21032112313 ((-57.83203 -34.01624, -57.65625 -34.01624, -57.6562…
#>  6   694  1229 21032112312 ((-58.00781 -34.01624, -57.83203 -34.01624, -57.8320…
#>  7   693  1229 21032112303 ((-58.18359 -34.01624, -58.00781 -34.01624, -58.0078…
#>  8   692  1229 21032112302 ((-58.35938 -34.01624, -58.18359 -34.01624, -58.1835…
#>  9   691  1229 21032112213 ((-58.53516 -34.01624, -58.35938 -34.01624, -58.3593…
#> 10   690  1229 21032112212 ((-58.71094 -34.01624, -58.53516 -34.01624, -58.5351…
#> # ℹ 86 more rows
```
