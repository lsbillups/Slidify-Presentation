---
title       : MPG Predictor 
subtitle    : An easy-to-use shiny app
author      : lsbillups
job         : Coursera Data Product Project
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]     # {mathjax, quiz, bootstrap}
mode        : selfcontained   # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

1. The shiny app `MPG_Predictor` provides an easy way for users to obtain an estimate of Miles-per-gallon (MPG) of their vehicles.

2. The app is solely based on a multivariate regression model built on `mtcars` dataset in `datasets` Package.

3. The app only takes three input variables: weight, quarter mile time and type of transmission.

4. Not only the app generates a prediction on MPG, it also provides a 95% prediction interval.

--- .class #id1

## Multivariate Regression Model


```r
head(mtcars,3)
```

```
##                mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4     21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag 21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710    22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
```

```r
fit<-lm(mpg ~ wt+qsec+am,data = mtcars)
summary(fit)$coefficients
```

```
##              Estimate Std. Error   t value     Pr(>|t|)
## (Intercept)  9.617781  6.9595930  1.381946 1.779152e-01
## wt          -3.916504  0.7112016 -5.506882 6.952711e-06
## qsec         1.225886  0.2886696  4.246676 2.161737e-04
## am           2.935837  1.4109045  2.080819 4.671551e-02
```

--- .class #id2 

## Simple algorithm yet nice result


```r
summary(fit)$r.squared
```

```
## [1] 0.8496636
```

With Rsquare almost 85%, most of the variation is explained by the model. Furthermore, a simple algorithm dramatically cut down the reaction time for the app.

Unlike other prediction app, MPG_Predictor includes 95% prediction interval as well, which provides user another perspective to justify the estimate.

With clear instruction, the app is for everyone.

[Try it today!](https://lsbillups.shinyapps.io/MPG_predictor)

--- .class #id3

##  Acknowledge

Thank you for the Coursera Data Science Specialization. Without this sequence, I couldn't even imagine build an app like this in R. Even though this app is just a baby project, hopefully it will become my starting point as a statyistical analyst.

For more details about this app, please refer to 
[My Github account](https://github.com/lsbillups/Coursera-Data-Product)
and
[Coursera Developing Data Products Course](https://class.coursera.org/devdataprod-015)




