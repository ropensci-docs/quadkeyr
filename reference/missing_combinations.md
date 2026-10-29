# Detect dates and hours missing in filenames

Facebook mobility data is reported daily at 3 different hours (0, 8,
16). This function reads the data extracted from the current files and
detects if any file for a particular day or hour is missing.

## Usage

``` r
missing_combinations(data, hour_col = "hour", date_col = "day")
```

## Arguments

- data:

  A data.frame with one column for the raster's date and another for the
  hour. If not explicitly specified in the function's arguments, the
  column names are `day` and `hour`.

- hour_col:

  The name of the column with the hour information.

- date_col:

  The name of the column with the date information.

## Value

A data.frame with the missing days and hours, if any.

## Examples

``` r

# Sample dataset
data <- data.frame(
  country = c("US", "MX", "MX"), 
  day = c("2023-01-01", "2023-01-03", "2023-01-05"),
  hour = c(0, 8, 16)
)

missing_combinations(data)
#>           day hour
#> 1  2023-01-01    8
#> 2  2023-01-01   16
#> 3  2023-01-02    0
#> 4  2023-01-02    8
#> 5  2023-01-02   16
#> 6  2023-01-03    0
#> 7  2023-01-03   16
#> 8  2023-01-04    0
#> 9  2023-01-04    8
#> 10 2023-01-04   16
#> 11 2023-01-05    0
#> 12 2023-01-05    8
```
