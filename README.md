experimental-design
================

Michael Jahn,
2020-11-20

Tools and figures to aide experimental design, such as power analysis

## Contents

- R notebook for power analysis (see `R/power-analysis.Rmd` for details)

## Power analysis

Power analysis is the estimation of the statistical "power" of a designed experiment. Power means that our experiment is designed in such a way that the occurence of type I errors (false positives) and type II errors (false negatives) is minimized. There are four different parameters that determine the power of the experimental design, whereas each of those can be calculated by supplying the other three.

- **sample size** (number of replicates)
- **effect size** (simplified: the expected difference in means, divided by expected standard deviation)
- **significance level alpha** (probability that the null hypothesis was falsely rejected, type I error)
- **statistical power** (probability that alternative hypothesis was correctly rejected, 1 - type II error)

Typically accepted **default values** for some of these parameters are:

- significance level alpha = 0.05, 0.01
- power = 0.8 (that means, the probability of a type II error is allowed to be 4x or 8x higher than type I error, which is considered more "dangerous")
- expected effect size is usually the input from the researcher. It is estimated from previous experiments (d = (mean1 - mean2)/sd).
- sample size is usually the desired parameter

Power analysis can be performed for different types of statistical tests, for example **t-test** (simple comparison of two sample means), ANOVA (regression analysis for conditions with several different variables, e.g. different measurement time points). Here, the R package `pwr` is used.

#### Example

Power analysis was used to determine the number of samples required to tell if two means (with a known SD) are significantly different.

![](R/power-analysis_files/figure-gfm/unnamed-chunk-4-1.png)