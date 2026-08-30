# Read all the .csv files in a folder and format the data.

This function reads all the `.csv` files in a particular folder. These
files consistently contain identical columns, with variations only in
location, day, and time. As a result, we can uniformly apply specific
formatting to columns across these files.

## Usage

``` r
read_fb_mobility_files(path_to_csvs, colnames, coltypes, keep_format = NULL)
```

## Arguments

- path_to_csvs:

  Path to the folder where the `.csv` files are stored

- colnames:

  Columns to include in the results (as character). For more information
  go to
  [`readr::read_csv()`](https://readr.tidyverse.org/reference/read_delim.html)

- coltypes:

  Column specifications (as strings). See vignette("readr", package =
  "readr") for more details. documentation.

- keep_format:

  Vector of column names, besides `date_time`, `day` and `quadkey`, that
  you don't want to convert to a number.

## Value

A data.frame with the information of all the files read.

## See also

[`format_fb_data`](https://docs.ropensci.org/quadkeyr/reference/format_fb_data.md)

[`read_csv`](https://readr.tidyverse.org/reference/read_delim.html)

## Examples

``` r

files <- read_fb_mobility_files(
  path_to_csvs = paste0(system.file("extdata",
    package = "quadkeyr"
  ), "/"),
  colnames = c( # The columns not listed here will be omitted
    "lat",
    "lon",
    "quadkey",
    "date_time",
    "n_crisis",
    "percent_change",
    "day",
    "hour"
  ),
  coltypes = list(
    lat = "d",
    lon = "d",
    quadkey = "c",
    date_time = "T",
    n_crisis = "c",
    percent_change = "c",
    day = "D",
    hour = "i"
  )
)
#> New names:
#> • `` -> `...1`
#> New names:
#> • `` -> `...1`
#> New names:
#> • `` -> `...1`

head(files)
#> # A tibble: 6 × 8
#>     lat   lon quadkey     date_time           n_crisis percent_change day       
#>   <dbl> <dbl> <chr>       <dttm>                 <dbl>          <dbl> <date>    
#> 1 -34.6 -58.6 2103213001… 2020-04-15 00:00:00       NA           2.86 2020-04-15
#> 2 -34.5 -58.6 2103213001… 2020-04-15 00:00:00       NA          -2.60 2020-04-15
#> 3 -34.6 -58.6 2103213001… 2020-04-15 00:00:00       NA           1.46 2020-04-15
#> 4 -34.5 -58.5 2103213001… 2020-04-15 00:00:00       NA           2.61 2020-04-15
#> 5 -34.5 -58.5 2103213001… 2020-04-15 00:00:00       NA           3.24 2020-04-15
#> 6 -34.5 -58.6 2103213001… 2020-04-15 00:00:00       NA           1.17 2020-04-15
#> # ℹ 1 more variable: hour <dbl>
```
