---
layout: post
date: 2022-10-01 00:00:00 +0100
tags: R
categories: Programming
title: 'Contingency Tables in R'
---

Contingency tables are a great tool in comparison analyses. In the simplest form a contingency table places one set of results against another set of results. In the example below two methods are compared. Each method produces two outcomes $A$ and $B$. Through the contingency table it is easily recognizable that the vast majority of the results between the methods match.
<center>

|           |   |  Method1 ||
|-----------|---|:---:|:---:|
|           |   | A   | B   |
|**Method2**| A | 20  | 1   |
|           | B | 2   | 18  |

</center>

Within R it is incredibly easy to make a contingency table. The built-in function `table` takes two vectors and makes... well, a table of it. The result is actually a contingency table. The first given vector is the columns, while the second given vector is the rows. If a category is not present it is not used in the table. Thus in the code example below the columns will have category $C$, but the rows will not.
```r
method1 <- c("A", "A", "A", "B", "B", "B", "C")
method2 <- c("A", "A", "B", "B", "B", "A", "A")

contingency <- table(method1, method2)
```

The contingency table works for categorical data. A contingency table can be made from two lists with different categories, and the number of categories can be different between the lists. The three requirements for a contingency table are that 1) there are only two lists, 2) the lists are of the same length, and 3) that the lists are ordered in the same manner. In the example below a dataframe with only two columns is given as the input. If there are more columns an error will be given. In the case of a dataframe the names of the columns (`outcome` and `medication`) are also added to the output.
```r
dataframe <- data.frame(outcome = c("Good", "Good", "Bad", "Bad", "Bad"),
                        medication = c("X", "X", "X", "Y", "Y"))

contingency <- table(dataframe$outcome, dataframe$medication)
```

The contingency table is quite simple to implement in R. It can be extended by adding row and column totals, calculating metrics from it, or by generalizing the code into a function. Of course there are also packages that make nice contingency tables, some even make nice graphics of it using mosaicplots.
