# Convert latitude/longitude coordinates into QuadKeys

Converts a point from latitude/longitude WGS-84 coordinates (in degrees)
into a Quadkey at a specified zoom level. For further information, refer
to the Microsoft Bing Maps Tile System documentation.

## Usage

``` r
latlong_to_quadkey(lat, lon, zoom)
```

## Arguments

- lat:

  Latitude of the point, in degrees.

- lon:

  Longitude of the point, in degrees.

- zoom:

  Zoom or level of detail, from 1 (lowest detail) to 23 (highest
  detail).

## Value

A dataframe with latitude (lat), longitude (lon), zoom level (zoom) and
the QuadKey as a string (quadkey).

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

latlong_to_quadkey(
  lat = 35.63051,
  lon = 139.69116,
  zoom = 20
)
#> Simple feature collection with 1 feature and 1 field
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 139.6912 ymin: 35.63051 xmax: 139.6912 ymax: 35.63051
#> Geodetic CRS:  WGS 84
#>                quadkey                  geometry
#> 1 13300211230321211111 POINT (139.6912 35.63051)
latlong_to_quadkey(
  lat = c(-4, -25.33, -25.66),
  lon = c(-53, -60.33, -70.66),
  zoom = 4
)
#> Simple feature collection with 3 features and 1 field
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: -70.66 ymin: -25.66 xmax: -53 ymax: -4
#> Geodetic CRS:  WGS 84
#>   quadkey              geometry
#> 1    2101        POINT (-53 -4)
#> 2    2103 POINT (-60.33 -25.33)
#> 3    2102 POINT (-70.66 -25.66)
```
