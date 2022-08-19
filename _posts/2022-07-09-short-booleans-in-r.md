---
layout: post
date: 2022-07-09 01:00:00 +0100
tags: R
categories: Programming
title: 'Short Booleans in R'
---

Booleans are the logic operators representing `true` and `false` in programming languages. It could also be seen as a `0` or `1`. In R the keywords `TRUE` and `FALSE` are used. Please note that these are fully capitalized, otherwise R will not recognize the booleans. 
```r
if (TRUE == TRUE) {}
if (FALSE == FALSE) {}
```

In R you also have the option to use a shortened version of the booleans. These are a capitalized `T` and `F`, as seen below. 
```r
if (T == T) {}
if (F == F) {}
```

You can also mix between the standard and short notation of booleans in our statements.
```r
if (TRUE == T) {}
if (F == FALSE) {}
```

I advise to choose between the standard or short notation and consistently apply it in your own projects. Use the standard notation in team projects where not everyone is familiar with the R programming language.
