# Apply a 7 day lag to the variable `n_crisis`

Applying a week lag to the data will create raster images showing the
mobility a week before the date of interest. This function works only
for QuadKeys reported without NAs for `n_crisis` and `percent_change`
variables .

## Usage

``` r
apply_weekly_lag(data)
```

## Arguments

- data:

  A data.frame with the columns `quadkey`, `day`, `hour` and `n_crisis`.

## Value

A data.frame with the extra columns `n_crisis_lag_7` and
`percent_change_7`.

- `n_crisis_lag_7`, is the same variable defined as `n_crisis` in the
  Facebook mobility data.frame with a 7 day lag applied.

- `percent_change_7` is the difference between the `n_crisis` value
  between weeks expressed as percentage.

## Examples

``` r

files <- read_fb_mobility_files(
  path_to_csvs = paste0(system.file("extdata",
    package = "quadkeyr"
  ), "/"),
  colnames = c(
    "lat",
    "lon",
    "quadkey",
    "date_time",
    "n_crisis",
    "percent_change"
  ),
  coltypes = list(
    lat = "d",
    lon = "d",
    quadkey = "c",
    date_time = "T",
    n_crisis = "c",
    percent_change = "c"
  )
)
#> New names:
#> • `` -> `...1`
#> New names:
#> • `` -> `...1`
#> New names:
#> • `` -> `...1`

apply_weekly_lag(data = files)
#> QuadKeys with 100% NAs for n_crisis: 305 (67.78% of total)
#> # A tibble: 435 × 10
#> # Groups:   quadkey [145]
#>      lat   lon quadkey    date_time           n_crisis percent_change day       
#>    <dbl> <dbl> <chr>      <dttm>                 <dbl>          <dbl> <date>    
#>  1 -34.5 -58.6 210321300… 2020-04-15 00:00:00    179.           3.75  2020-04-15
#>  2 -34.5 -58.6 210321300… 2020-04-15 08:00:00     NA            6.40  2020-04-15
#>  3 -34.5 -58.6 210321300… 2020-04-15 16:00:00    110.          -0.245 2020-04-15
#>  4 -34.5 -58.6 210321300… 2020-04-15 00:00:00     NA           -0.354 2020-04-15
#>  5 -34.5 -58.6 210321300… 2020-04-15 08:00:00    108.          -0.130 2020-04-15
#>  6 -34.5 -58.6 210321300… 2020-04-15 16:00:00     NA            3.62  2020-04-15
#>  7 -34.5 -58.6 210321300… 2020-04-15 00:00:00    601.         -12.4   2020-04-15
#>  8 -34.5 -58.6 210321300… 2020-04-15 08:00:00     55.7         -3.71  2020-04-15
#>  9 -34.5 -58.6 210321300… 2020-04-15 16:00:00     NA            1.89  2020-04-15
#> 10 -34.5 -58.6 210321300… 2020-04-15 00:00:00     13.1         -0.310 2020-04-15
#> # ℹ 425 more rows
#> # ℹ 3 more variables: hour <dbl>, n_crisis_lag_7 <dbl>, percent_change_7 <dbl>
```
