
# `R`/MOSS: Semiparametric Efficient Survival Analysis

[![Travis-CI Build
Status](https://travis-ci.org/wilsoncai1992/MOSS.svg?branch=master)](https://travis-ci.org/wilsoncai1992/MOSS)
[![Appveyor Build
Status](https://ci.appveyor.com/api/projects/status/hagh8vidrdeacr7f?svg=true)](https://ci.appveyor.com/project/wilsoncai1992/MOSS)
[![codecov](https://codecov.io/gh/wilsoncai1992/MOSS/branch/master/graph/badge.svg)](https://codecov.io/gh/wilsoncai1992/MOSS)
[![Project Status: Active – The project has reached a stable, usable
state and is being actively
developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![License: GPL
v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://www.gnu.org/licenses/gpl-2.0)
[![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/MOSS)](http://cran.rstudio.com/web/packages/MOSS/index.html)
[![](http://cranlogs.r-pkg.org/badges/MOSS)](http://cran.rstudio.com/web/packages/MOSS/index.html)
[![](http://cranlogs.r-pkg.org/badges/grand-total/MOSS)](http://cran.rstudio.com/web/packages/MOSS/index.html)

MOSS performs ensemble machine learning and Targeted Maximum Likelihood
(TMLE) to estimate the counter-factual marginal survival functions,
while non-parametrically adjusting for measured confounding. TMLE
approach is employed to create a doubly robust and semi-parametrically
efficient estimator. Simultaneous confidence bands of the entire curve
is also available for inference. User can specify what kind of static
intervention on treatment (exposure).

The following comparable methods are also included in the package for
you to easily compare methods: - Inverse censoring probability weighted
(IPCW) - Locally efficient one-step estimator (estimating equation
methods)

``` r
install.packages('MOSS')
devtools::install_github('wilsoncai1992/MOSS')
```

## Documentation

  - To see all available package documentation:

<!-- end list -->

``` r
?MOSS
help(package = 'MOSS')
```

## Brief overview

### Data structure

The data input of all methods in the package should be an `R`
`data.frame` in the following survival long data format:

``` r
#   ID W A T.tilde delta
# 1  1 0 0      95     1
# 2  2 1 1       1     0
# 3  3 0 0     215     1
# 4  4 1 1      15     1
# 5  5 0 0      73     1
# 6  6 0 0      15     1
```

### Steps of analysis

1.  perform SuperLearner fit of the conditional survival function of
    failure event, conditional survival function of censoring event,
    propensity scores (`initial_sl_fit`)
2.  perform TMLE adjustment of the conditional survival fit
    (`MOSS_hazard`)
3.  simultaneous confidence band (`compute_simultaneous_ci`)

## Citation

To cite `MOSS` in publications, please use:

> Cai W, van der Laan MJ (2019+). *One-step TMLE for time-to-event
> outcomes.* Working paper.

## Funding

## Copyright

This software is distributed under the GPL-2 license.

## Community Guidelines

Feedback, bug reports (and fixes\!), and feature requests are welcome;
file issues or seek support
[here](https://github.com/wilsoncai1992/MOSS/issues).
