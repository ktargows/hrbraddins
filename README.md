
[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/0.1.0/active.svg)](http://www.repostatus.org/#active) [![codecov](https://codecov.io/gh/hrbrmstr/hrbraddins/branch/master/graph/badge.svg)](https://codecov.io/gh/hrbrmstr/hrbraddins) [![Travis-CI Build Status](https://travis-ci.org/hrbrmstr/hrbraddins.svg?branch=master)](https://travis-ci.org/hrbrmstr/hrbraddins)

`hrbraddins` : Additional Addins for RStudio

The following functions are implemented:

-   `bare_combine`: Turn a selection of comma-separated bare strings into a - `base::combine`: statement
-   `bare_rename`: Turn a selection of comma-separated bare strings into a `dplyr::rename` statement
-   `join_rows`: Join `cr`/`lf`-separated selected rows of text into a single space-separated row

### Bare Rename

The RStudio Addins menu selection "Bare Rename" will take a text selection and make it into `dplyr::rename()` statement For example:

    a,b c,d,e f

or

    a, b c, d, e f

will be converted to:

    dplyr::rename(a, `b c`, d, `e f`)

**NOTE**: not all backtick-edge cases are handled (yet).

### Bare Combine

Similarly, the RStudio Addins menu selection "Bare Combine" will take a text selection and make it into a `c()` statement. For example:

    a,b c,d,e f

or

    a, b c, d, e f

will be converted to:

    c("a", "b c", "d", "e f")

**NOTE**: not all double-quote edge cases are handled (yet).

### Join Rows

Finally, unless I'm missing something, RStudio doesn't have a "join rows" option, so you can use the RStudio Addins menu selection "Join Rows" to do just that. So:

    a
    b
    c
    d

becomes:

    a b c d

The best way to find out if I'm wrong about that is by doing this tho since the internet will gladly tell me if I'm wrong.

### Installation

``` r
devtools::install_github("hrbrmstr/hrbraddins")
```
