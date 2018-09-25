hw02-singhg53
================
Gurjot Singh
20/09/2018

# Homework Assignment \#2

#### By: Gurjot Singh (singhg53)

## Smell test the data

Hello\! Today we will be exploring a the dataset known as `gapminder`

For those who have not yet downloaded the dataset you can do so by
installing the package by the function:

`install.packages("gapminder")`

Now since you have downloaded the dataset lets load it using the
`library` function

``` r
library(gapminder)
```

Let’s also install and load the tidyverse
    package

`install.packages("tidyverse")`

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

The cool thing about the tidyverse package is that includes different
functions that could be used like `ggplot2` and `dplyr`

First let’s check if the dataset is a vector:

``` r
is.atomic(gapminder) || is.list(gapminder)
```

    ## [1] TRUE

Now let’s check what type of vector

``` r
typeof(gapminder)
```

    ## [1] "list"

This shows us that the dataset is a list. But it is important to test if
a dataset is a dataframe because a dataframe are lists as well.

``` r
is.data.frame(gapminder)
```

    ## [1] TRUE

This example shows good dimensionality of the dataset it is a vector-\>
list (1-dimension)-\> data frame (2-dimension)

Let’s just double check if the dataset is a matrix or array:

``` r
is.matrix(gapminder)
```

    ## [1] FALSE

``` r
is.array(gapminder)
```

    ## [1] FALSE

The class of the dataset can be found by using the `class` function

``` r
class(gapminder)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

The columns can be found using the `ncol` function

``` r
ncol(gapminder)
```

    ## [1] 6

Let’s check how many rows are in the data set using the `nrow` function

``` r
nrow(gapminder)
```

    ## [1] 1704

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
