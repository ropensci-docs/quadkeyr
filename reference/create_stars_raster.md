# Create a `stars` raster

The use of a template enables the creation of an accurate raster, even
in the presence of NAs.

## Usage

``` r
create_stars_raster(template, nx, ny, data, var)
```

## Arguments

- template:

  A `sf` POLYGON data.frame to use as template. Check
  [`stars::st_as_stars()`](https://r-spatial.github.io/stars/reference/st_as_stars.html)
  documentation for more details.

- nx:

  Integer; number of cells in x direction.

- ny:

  Integer; number of cells in y direction.

- data:

  A `sf` POLYGON data.frame with the variable we want to represent in
  the raster.

- var:

  The column name of the variable to plot.

## Value

A `stars` object.

## See also

[`st_as_stars`](https://r-spatial.github.io/stars/reference/st_as_stars.html),
[`st_rasterize`](https://r-spatial.github.io/stars/reference/st_rasterize.html)

## Examples

``` r
# \donttest{
# Basic workflow
# Read the data
path <- paste0(
  system.file("extdata", package = "quadkeyr"),
  "/cityA_2020_04_15_0000.csv"
)
data <- read.csv(path)
data <- format_fb_data(data)

complete_polygon_grid <- add_regular_polygon_grid(data = data)

stars_object <- create_stars_raster(
  data = complete_polygon_grid$data,
  template = complete_polygon_grid$data,
  var = "percent_change",
  nx = complete_polygon_grid$num_cols,
  ny = complete_polygon_grid$num_rows
)
stars_object
#> stars object with 2 dimensions and 1 attribute
#> attribute(s):
#>                      Min.  1st Qu.   Median      Mean  3rd Qu.     Max. NAs
#> percent_change  -23.94377 -2.50754 1.109488 0.6168087 3.838209 28.42059 246
#> dimension(s):
#>   from to offset     delta refsys point x/y
#> x    1 18  -58.6  0.005493 WGS 84 FALSE [x]
#> y    1 22  -34.5 -0.004524 WGS 84 FALSE [y]

# Other workflow
grid <- create_qk_grid(
  xmin = -59,
  xmax = -57,
  ymin = -35,
  ymax = -34,
  zoom = 12
)

grid_coords <- get_qk_coord(data = grid$data)

polygrid <- grid_to_polygon(grid_coords)

data("data_provided")
data_raster <- polygrid |>
  dplyr::inner_join(data_provided,
    by = c("quadkey")
  )

raster <- create_stars_raster(
  template = data_raster,
  nx = grid$num_cols,
  ny = grid$num_rows,
  data = data_raster,
  var = "variable"
)
# }
```
