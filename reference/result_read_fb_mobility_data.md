# Dataset with (fake) Facebook mobility data

A data.frame similar to a the potential output of
`read_fb_mobility_files`.

## Usage

``` r
result_read_fb_mobility_data
```

## Format

### `result_read_fb_mobility_data`

A data frame with 134,492 rows and 9 columns:

- lat:

  Latitude of the QuadKey centroid

- lon:

  Longitude of the QuadKey centroid

- quadkey:

  QuadKey as a string

- country:

  Country name

- date_time:

  Date in format %Y-%m-%d %H%M

- n_crisis:

  Variable

- percent_change:

  Variable

- day:

  Day in format %Y-%m-%d

- hour:

  Hour of the day as a number between 1 and 24
