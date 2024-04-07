
<!-- README.md is generated from README.Rmd. Please edit that file -->

# predicttornado

<!-- badges: start -->
<!-- badges: end -->

The goal of predicttornado is to give access to functions that help with
the data analysis of predicting the number of fatalities using length
and width of tornadoes based on tornado data.

## Installation

You can install the development version of predicttornado like so:

``` r
# install.packages("devtools")
devtools::install_github("DSCI-310-2024/predicttornado")
```

## Example

``` r
tornado_df <- data.frame(
  om = c(156, 189, 26), 
  yr = c(1950, 1951, 1952), 
  mo = c(10, 11, 12), 
  dy = c(1, 9, 20), 
  date = as.Date(c("2021-03-26", "2022-03-26", "2024-03-01")),
  time = as.POSIXct(c("12:00:00", "13:00:00", "21:00:00"), format = "%H:%M:%S"),
  tz = c("America/Chicago", "America/Chicago", "America/Chicago"),
  datetime_utc = as.POSIXct(c("2021-03-26 12:00:00", "2022-03-26 13:00:00", "2024-03-01 21:00:00")),
  st = c("OK", "NC", "TX"),
  stf = c(0, 0, 0), 
  mag = c(0, 0, NA), 
  inj = c(23, 233, 405), 
  fat = c(45, 190, 201), 
  loss = c(23, 40, 56), 
  slat = c(0, 0, 0), 
  slon = c(0, 0, 0), 
  elat = c(0, 0, 0), 
  elon = c(0, -50, -60), 
  len = c(201, 340, 100), 
  wid = c(34, 57, 71), 
  ns = c(0, 0, NA), 
  sn = c(0, 0, 0), 
  f1 = c(0, 0, 0), 
  f2 = c(0, 0, 0), 
  f3 = c(0, 0, NA), 
  f4 = c(0, 0, 0), 
  fc = c(FALSE, FALSE, TRUE)
)
```

This is a basic example which shows you how to load the package and use
one of its functions, `process_data`, which processes and cleans your
data before using it for data analysis.

``` r
#library(predicttornado)

#process_data(tornado_df)
```

This package can also be used to create visualizations like scatterplots
using `create_scatterplot`, boxplots using `boxplot_viz` and accuracy
plots using `accuracy_plot`.

``` r
#create_scatterplot(tornado_df, width, fatalities) + 
#labs(x = "Width of tornadoes (yards)", y = "Fatalities", 
#title = "Figure 2: Scatterplot of width (yards) of tornado and fatalities")
```

``` r
#boxplot_viz(tornado_df, fatalities)
```

``` r
#accuracy_plot(tornado_df, fatalities) + 
#labs(x = "Actual Number of Fatalities", y = "Predicted Number of Fatalities")
```

You can easily create a linear regression model and fit it to your data
with the function `fit_linear_model`:

``` r
#fit_linear_model(fatalities ~ width + length, tornado_df)
```
