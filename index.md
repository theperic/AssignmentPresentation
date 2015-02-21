---
title       : Height Predition App
subtitle    : 
author      : Eric Larsen
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Using the Application

This is a basic application to predict a person's height based on the average of their parents height and their gender.  It uses a simple linear model based on te Galton data set in R.

1. Use the Slider to select your father's height.
2. Use the Slider to select your mother's height.
3. Select your gender.

--- .class #id 

## Technical information

The calculation in the app is quite simple.  I fit a linear model to the Galton data set:

lm(galton$child ~ galton$parent)

I averaged the input heights of the father and mother, then applied the slope and y intercept from the linear model.

I assumed that men are 5% taller than women, so if the gender selected was female, I reduced the estimate by 5%.

---

## Environment Information
This application and document were built with:

```r
print(sessionInfo(), locale = FALSE)
```

```
## R version 3.1.2 (2014-10-31)
## Platform: x86_64-w64-mingw32/x64 (64-bit)
## 
## attached base packages:
## [1] splines   grid      stats     graphics  grDevices utils     datasets 
## [8] methods   base     
## 
## other attached packages:
## [1] UsingR_2.0-4    Hmisc_3.14-6    Formula_1.2-0   survival_2.37-7
## [5] lattice_0.20-29 HistData_0.7-5  MASS_7.3-37    
## 
## loaded via a namespace (and not attached):
##  [1] acepack_1.3-3.3     cluster_2.0.1       digest_0.6.8       
##  [4] evaluate_0.5.5      foreign_0.8-62      formatR_1.0        
##  [7] knitr_1.9           latticeExtra_0.6-26 markdown_0.7.4     
## [10] nnet_7.3-8          RColorBrewer_1.1-2  rpart_4.1-8        
## [13] slidify_0.4.5       stringr_0.6.2       tools_3.1.2        
## [16] whisker_0.3-2       yaml_2.1.13
```
