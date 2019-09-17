p8105\_hw1\_sm4594
================
Sophia Miller
9/15/2019

# Problem 1.

Create a data frame comprised of:

  - a random sample of size 8 from a standard Normal distribution
  - a logical vector indicating whether elements of the sample are
    greater than 0
  - a character vector of length 8
  - a factor vector of length 8, with 3 different factor
    “levels”

<!-- end list -->

``` r
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.2.1     ✔ purrr   0.3.2
    ## ✔ tibble  2.1.3     ✔ dplyr   0.8.3
    ## ✔ tidyr   0.8.3     ✔ stringr 1.4.0
    ## ✔ readr   1.3.1     ✔ forcats 0.4.0

    ## ── Conflicts ──────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
problem1_df = tibble(
  norm_samp = rnorm(8),
  norm_samp_pos = norm_samp > 0,
  vec_char = character(8),
  vec_factor = factor(3)
)
```

Take the mean of each variable in the data
    frame:

``` r
mean(pull(problem1_df, norm_samp))
```

    ## [1] -0.3409777

``` r
mean(pull(problem1_df, norm_samp_pos))
```

    ## [1] 0.375

``` r
mean(pull(problem1_df, vec_char))
```

    ## Warning in mean.default(pull(problem1_df, vec_char)): argument is not
    ## numeric or logical: returning NA

    ## [1] NA

``` r
mean(pull(problem1_df, vec_factor))
```

    ## Warning in mean.default(pull(problem1_df, vec_factor)): argument is not
    ## numeric or logical: returning NA

    ## [1] NA

We are able to take the mean of the random sample as well as the logical
vector, but we are unable to take the mean of the character and factor
vectors.

``` r
as.numeric(pull(problem1_df, norm_samp_pos)) 

as.numeric(pull(problem1_df, vec_char))

as.numeric(pull(problem1_df, vec_factor))
```
