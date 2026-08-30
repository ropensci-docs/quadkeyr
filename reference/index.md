# Package index

## From a QuadKey to a Simple Features data.frame and other conversions

Functions to convert a QuadKey to a `sf` POINT data.frame or `sf`
POLYGON data.frame. Additionally, all the R functions described in the
official documentation to convert QuadKeys to and from tiles, pixels and
geographic coordinates are available.

- [`quadkey_to_polygon()`](https://docs.ropensci.org/quadkeyr/reference/quadkey_to_polygon.md)
  : Convert a QuadKey into a square polygon
- [`quadkey_to_latlong()`](https://docs.ropensci.org/quadkeyr/reference/quadkey_to_latlong.md)
  : Convert a string of Quadkey numbers to lat/long coordinates
- [`quadkey_to_tileXY()`](https://docs.ropensci.org/quadkeyr/reference/quadkey_to_tileXY.md)
  : Convert a QuadKey into tile XY coordinates.
- [`tileXY_to_pixelXY()`](https://docs.ropensci.org/quadkeyr/reference/tileXY_to_pixelXY.md)
  : Convert tile XY coordinates into pixel XY coordinates
- [`pixelXY_to_latlong()`](https://docs.ropensci.org/quadkeyr/reference/pixelXY_to_latlong.md)
  : Convert pixel XY coordinatess into lat/long coordinates.
- [`latlong_to_quadkey()`](https://docs.ropensci.org/quadkeyr/reference/latlong_to_quadkey.md)
  : Convert latitude/longitude coordinates into QuadKeys
- [`latlong_to_pixelXY()`](https://docs.ropensci.org/quadkeyr/reference/latlong_to_pixelXY.md)
  : Convert lat/long coordinates to pixel XY coordinates
- [`pixelXY_to_tileXY()`](https://docs.ropensci.org/quadkeyr/reference/pixelXY_to_tileXY.md)
  : Convert pixel XY coordinates into tile XY coordinates
- [`tileXY_to_quadkey()`](https://docs.ropensci.org/quadkeyr/reference/tileXY_to_quadkey.md)
  : Convert tile XY coordinates into a QuadKey.
- [`mapsize()`](https://docs.ropensci.org/quadkeyr/reference/mapsize.md)
  : Map size in pixels
- [`mapscale()`](https://docs.ropensci.org/quadkeyr/reference/mapscale.md)
  : Map scale (1 : N)
- [`ground_res()`](https://docs.ropensci.org/quadkeyr/reference/ground_res.md)
  : Ground resolution at a specified latitude and zoom level

## Generating a Raster Image from Quadkey-Identified Data

Complete a grid of QuadKeys within a specified area and zoom level, and
create a `stars` raster. You can also directly convert QuadKeys in a
data.frame column into an `sf` POLYGON data.frame.

- [`add_regular_polygon_grid()`](https://docs.ropensci.org/quadkeyr/reference/add_regular_polygon_grid.md)
  :

  Add the rows needed to complete a regular QuadKey polygon grid derived
  from the bounding box of the `quadkey` column of a data.frame.

- [`create_stars_raster()`](https://docs.ropensci.org/quadkeyr/reference/create_stars_raster.md)
  :

  Create a `stars` raster

- [`quadkey_df_to_polygon()`](https://docs.ropensci.org/quadkeyr/reference/quadkey_df_to_polygon.md)
  :

  Convert data.frame with `quadkey` column to a `sf` POLYGON data.frame

- [`create_qk_grid()`](https://docs.ropensci.org/quadkeyr/reference/create_qk_grid.md)
  : Create grid of QuadKeys for a particular zoom or level of detail.

- [`get_qk_coord()`](https://docs.ropensci.org/quadkeyr/reference/get_qk_coord.md)
  : Get lat/long coordinates from the QuadKey

- [`regular_qk_grid()`](https://docs.ropensci.org/quadkeyr/reference/regular_qk_grid.md)
  :

  Convert a incomplete QuadKey `sf` POINT data.frame into a regular
  grid.

- [`grid_to_polygon()`](https://docs.ropensci.org/quadkeyr/reference/grid_to_polygon.md)
  : Convert a grid of QuadKeys to square polygons

## Converting Facebook Mobility QuadKey-identified Datasets into Raster Files

Convert Facebook mobility data `.csv` files into `.tif` files by day and
hour reported.

- [`read_fb_mobility_files()`](https://docs.ropensci.org/quadkeyr/reference/read_fb_mobility_files.md)
  : Read all the .csv files in a folder and format the data.

- [`format_fb_data()`](https://docs.ropensci.org/quadkeyr/reference/format_fb_data.md)
  : Format the Facebook mobility data

- [`missing_combinations()`](https://docs.ropensci.org/quadkeyr/reference/missing_combinations.md)
  : Detect dates and hours missing in filenames

- [`get_regular_polygon_grid()`](https://docs.ropensci.org/quadkeyr/reference/get_regular_polygon_grid.md)
  :

  Get regular QuadKey polygon grid derived from the bounding box of the
  `quadkey` column of a data.frame.

- [`polygon_to_raster()`](https://docs.ropensci.org/quadkeyr/reference/polygon_to_raster.md)
  : Create and save raster images for different dates and times

- [`apply_weekly_lag()`](https://docs.ropensci.org/quadkeyr/reference/apply_weekly_lag.md)
  :

  Apply a 7 day lag to the variable `n_crisis`

## QuadKey Visualization App

Introduce a QuadKey visualization application enabling users to validate
function outcomes.

- [`qkmap_app()`](https://docs.ropensci.org/quadkeyr/reference/qkmap_app.md)
  : Launch the Shiny App
