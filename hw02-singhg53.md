hw02-singhg53
================
Gurjot Singh
20/09/2018

# Homework Assignment \#2

By: Gurjot Singh (singhg53)

Hello\! Today we will be exploring a the dataset known as `gapminder`.

## Smell test the data

For those who have not yet downloaded the dataset you can do so by
installing the package by the function:

`install.packages("gapminder")`

Now since you have downloaded the dataset lets load it using the
`library` function:

``` r
library(gapminder)
```

Let’s also install and load the tidyverse
    package:

`install.packages("tidyverse")`

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ───────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

The cool thing about the tidyverse package is that includes different
functions that could be used like `ggplot2` and `dplyr`

**Question: Is `gapminder` a data.frame, a matrix, a vector, a list?**

First let’s check what type of dataset is `gapminder` using the `typeof`
function:

``` r
typeof(gapminder)
```

    ## [1] "list"

`gapminder` is found to be a list.

This shows us that the dataset is a list. But it is important to test if
a dataset is a dataframe because a dataframe are lists as well.

``` r
is.data.frame(gapminder)
```

    ## [1] TRUE

Since this is true we can establish that the dataset is indeed a data
frame.

A cool way to check if the dataset is a martix or an array is using the
functions below.

``` r
is.matrix(gapminder)
```

    ## [1] FALSE

``` r
is.array(gapminder)
```

    ## [1] FALSE

Both of them come out false, as expected.

The class of the dataset can be found by using the `class` function

``` r
class(gapminder)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

This is another way we could find that `gapminder` is a data frame.

The number of columns can be found using the `ncol` function:

``` r
ncol(gapminder)
```

    ## [1] 6

This shows us that there are six columns in the dataset.

Let’s check how many rows are in the data set using the `nrow` function:

``` r
nrow(gapminder)
```

    ## [1] 1704

We can conclude there are 1704 rows in this dataset.

We can use the `dim` function to tell us the size or the exent of the
data

``` r
dim(gapminder)
```

    ## [1] 1704    6

The structure of the dataset can also tell us about the extent or size
of the data and it could tell us what data type is each
    variable

``` r
str(gapminder)
```

    ## Classes 'tbl_df', 'tbl' and 'data.frame':    1704 obs. of  6 variables:
    ##  $ country  : Factor w/ 142 levels "Afghanistan",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##  $ continent: Factor w/ 5 levels "Africa","Americas",..: 3 3 3 3 3 3 3 3 3 3 ...
    ##  $ year     : int  1952 1957 1962 1967 1972 1977 1982 1987 1992 1997 ...
    ##  $ lifeExp  : num  28.8 30.3 32 34 36.1 ...
    ##  $ pop      : int  8425333 9240934 10267083 11537966 13079460 14880372 12881816 13867957 16317921 22227415 ...
    ##  $ gdpPercap: num  779 821 853 836 740 ...

| **Variable** | **Data Type** |
| ------------ | ------------- |
| country      | Factor        |
| contient     | Factor        |
| Year         | Integer       |
| lifeExp      | Number        |
| pop          | Integer       |
| gdpPercap    | Number        |

# Explore Individual Variables

Let’s first explore the continent variable, which is categorical

``` r
summary(gapminder$continent)
```

    ##   Africa Americas     Asia   Europe  Oceania 
    ##      624      300      396      360       24

Now let’s look at a numerical variable such as lifeExp

``` r
summary(gapminder$lifeExp)
```

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   23.60   48.20   60.71   59.47   70.85   82.60

Let’s do another cateogrical variable for fun, such as, continent

``` r
summary(gapminder$continent)
```

    ##   Africa Americas     Asia   Europe  Oceania 
    ##      624      300      396      360       24

Vectorization, recycling

look at the years

``` r
filter(gapminder, country == "Rwanda" & country == "Afghanistan")
```

    ## # A tibble: 0 x 6
    ## # ... with 6 variables: country <fct>, continent <fct>, year <int>,
    ## #   lifeExp <dbl>, pop <int>, gdpPercap <dbl>

``` r
filter(gapminder, country == c("Rwanda"))
```

    ## # A tibble: 12 x 6
    ##    country continent  year lifeExp     pop gdpPercap
    ##    <fct>   <fct>     <int>   <dbl>   <int>     <dbl>
    ##  1 Rwanda  Africa     1952    40   2534927      493.
    ##  2 Rwanda  Africa     1957    41.5 2822082      540.
    ##  3 Rwanda  Africa     1962    43   3051242      597.
    ##  4 Rwanda  Africa     1967    44.1 3451079      511.
    ##  5 Rwanda  Africa     1972    44.6 3992121      591.
    ##  6 Rwanda  Africa     1977    45   4657072      670.
    ##  7 Rwanda  Africa     1982    46.2 5507565      882.
    ##  8 Rwanda  Africa     1987    44.0 6349365      848.
    ##  9 Rwanda  Africa     1992    23.6 7290203      737.
    ## 10 Rwanda  Africa     1997    36.1 7212583      590.
    ## 11 Rwanda  Africa     2002    43.4 7852401      786.
    ## 12 Rwanda  Africa     2007    46.2 8860588      863.
