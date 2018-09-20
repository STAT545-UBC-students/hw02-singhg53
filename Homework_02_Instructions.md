Homework\_02\_Instructions
================
Gurjot Singh
20/09/2018

# Homework 02: Explore Gapminder and use dplyr

## Overview

The goal is to explore a dataset. In particular, to begin to establish a
workflow for data frames or “tibbles”. You will use `dplyr` and
`ggplot2` to do some description and visualization.

Due by 23:59 Tuesday 2018-09-25, but I **highly recommend** you aim to
submit before class. This assignment should go smoothly, but if the
computer gods do not smile upon you, we should be able to straighten
things out in class or office hours.

Your homework should serve as your own personal cheatsheet in the future
for things to do with a new dataset. Give yourself the cheatsheet you
deserve\!

### Evaluation

All rubrics listed on the
[assignments](http://stat545.com/Classroom/assignments/) page are
relevant for this assignment.

Here’s an “overall” view of the scores:

0: Didn’t attempt.

1: There are some mistakes or omissions, such as the number of rows or
variables in the data frame. Or maybe no confirmation of its class or
that of the variables inside. There are no plots or there’s just one
type of plot (and its probably a scatterplot). There’s no use of
`filter()` or `select()`. It’s hard to figure out which file I’m
supposed to be looking at. Maybe the student forgot to commit and push
the figures to GitHub.

2: Hits all the elements. No obvious mistakes. Pleasant to read. No
heroic detective work required. Solid.

3: Some “above and beyond”, creativity, etc. You learned something new
from reviewing their work and you’re eager to incorporate it into your
work now. Use of dplyr goes beyond `filter()` and `select()`. The
ggplot2 figures are quite diverse. The repo is very organized and it’s a
breeze to find the file for this homework specifically.

## Bring rectangular data in

Work with the `gapminder` data we explored in class. *If you really want
to, you can explore a different dataset. Self-assess the suitability of
your dataset by reading [this
issue](https://github.com/STAT545-UBC/Discussion/issues/115), and if you
still aren’t sure if it’s suitable, send Vincenzo an email.*

The Gapminder data is distributed as an R package from
[CRAN](https://cran.r-project.org/web/packages/gapminder/index.html).

Install it if you have not done so already and remember to load it.

    install.packages("gapminder")
    library(gapminder)

Install and load dplyr. Probably via the tidyverse meta-package.

    install.packages("tidyverse")
    library(tidyverse)

## Smell test the data

Explore the `gapminder` object:

  - Is it a data.frame, a matrix, a vector, a list?
  - What is its class?
  - How many variables/columns?
  - How many rows/observations?
  - Can you get these facts about “extent” or “size” in more than one
    way? Can you imagine different functions being useful in different
    contexts?
  - What data type is each variable?

Be sure to justify your answers by calling the appropriate R functions.

## Explore individual variables

Pick **at least** one categorical variable and at least one quantitative
variable to explore.

  - What are possible values (or range, whichever is appropriate) of
    each variable?
  - What values are typical? What’s the spread? What’s the distribution?
    Etc., tailored to the variable at hand.
  - Feel free to use summary stats, tables, figures. We’re NOT expecting
    high production value (yet).

## Explore various plot types

Make a few plots, probably of the same variable you chose to
characterize numerically. You can use the plot types we went over in
class (cm006) to get an idea of what you’d like to make. Try to explore
more than one plot type. **Just as an example** of what I mean:

  - A scatterplot of two quantitative variables.
  - A plot of one quantitative variable. Maybe a histogram or
    densityplot or frequency polygon.
  - A plot of one quantitative variable and one categorical. Maybe
    boxplots for several continents or countries.

You don’t have to use all the data in every plot\! It’s fine to filter
down to one country or small handful of countries.

## Use `filter()`, `select()` and `%>%`

Use `filter()` to create data subsets that you want to plot.

Practice piping together `filter()` and `select()`. Possibly even piping
into `ggplot()`.

## But I want to do more\!

*For people who want to take things further.*

Evaluate this code and describe the result. Presumably the analyst’s
intent was to get the data for Rwanda and Afghanistan. Did they succeed?
Why or why not? If not, what is the correct way to do this?

    filter(gapminder, country == c("Rwanda", "Afghanistan"))

Read [What I do when I get a new data set as told through
tweets](http://simplystatistics.org/2014/06/13/what-i-do-when-i-get-a-new-data-set-as-told-through-tweets/)
from [SimplyStatistics](http://simplystatistics.org) to get some ideas\!

Present numerical tables in a more attractive form, such as using
`knitr::kable()`.

Use more of the dplyr functions for operating on a single table.

Adapt exercises from the chapters in the “Explore” section of [R for
Data Science](http://r4ds.had.co.nz) to the Gapminder dataset.

## Reflection

Once you’re done the above, go back to [UBC
canvas](https://canvas.ubc.ca/), and find the “Homework 02” page. Here,
you should submit a reflection (and, although not required, adding a
link to your homework respository would be helpful for the markers).

Please don’t skip this reflection\! We really care about this.

Reflect on what was hard/easy, problems you solved, helpful tutorials
you read, etc. What things were hard, even though you saw them in class?
What was easy(-ish) even though we haven’t done it in class?

## Special Submission Cases

**Are you worried about submitting early, and then wanting to make
changes that are included in your submission?**

Don’t be. We’ll always grade your GitHub repository as it was at the
last commit prior to the deadline. Therefore, we encourage you to submit
early and often, especially regarding your GitHub repository\!

**Want to submit early, and continue making contributions to your
repository that you *don’t* want to be graded?**

Just [create a
release](https://help.github.com/articles/creating-releases/) of your
homework repo, and include the link to this release in your submission,
being sure to indicate that this is a special early release that you
want graded. Or, even better, just fork the repo.
