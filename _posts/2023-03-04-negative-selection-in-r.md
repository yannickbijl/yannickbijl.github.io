---
layout: post
date: 2023-03-04 00:00:00 +0100
tags: R
categories: Software-Development Programming
title: 'Negative Selection in R'
---

R is a statistical programming language well suited for data wrangling and analysis. For many data preparation steps we need to remove data columns. In many languages we achieve this by selecting the columns we want to keep, or using a specific functions such `.drop()` from Python's pandas package.

With R we can also achieve this using negative selection. Similar to the `.drop()` method we can specify the values, columns, or rows that we want to remove. In the case of vectors we use the square bracket notation and place a minus sign before the index we want removed. If want multiple indices removed we place the minus sign before the vector with the indices.
```r
var <- c("a", 2, "words", 123.964)

print(var[-3]) # [1] "a"  "2"  "123.964"
print(var[-c(3, 4)]) # [1] "a"  "2"
```

For dataframes indices indicate rows and columns. Thus in a similar fashion as above we can remove the unwanted data. With the bracket notation  Be aware that with negative selection you will remove the entire row and column if both are given, not just a specific value in the dataframe. 
```r
name <- c("Jon", "Bill", "Maria", "Ben", "Tina")
sex <- c("Male", "Male", "Female", "Male", "Female")
age <- c(23, 41, 32, 58, 26)
df <- data.frame(name, sex, age)

print(df[,-1])
#      sex age
# 1   Male  23
# 2   Male  41
# 3 Female  32
# 4   Male  58
# 5 Female  26
```

The same can be achieved through the `dplyr` package, which is part of the tidyverse. This allows us to easily use negative selections with the names of the columns instead of indices. For negative selection to work properly with dplyr the names need to be wrapped in a vector as shown in the example below.
```r
library(dplyr)

name <- c("Jon", "Bill", "Maria", "Ben", "Tina")
sex <- c("Male", "Male", "Female", "Male", "Female")
age <- c(23, 41, 32, 58, 26)
df <- data.frame(name, sex, age)

print(df %>% select(-c(name)))
#      sex age
# 1   Male  23
# 2   Male  41
# 3 Female  32
# 4   Male  58
# 5 Female  26
```

Through negative selection it is possible to reduce the amount of code needed. Simply by using the negative instead of the positive. Negative selection is an easy but powerful tool. It is a great way to make your code more readable, and also save yourself unnecessary typing.
