---
layout: post
date: 2022-12-24 00:00:00 +0100
tags: R
categories: Software-Development Programming
title: 'Dumping Print to Files in R using Sink'
---

Writing data to files is an essential step in all data analysis. To  save your mutated data, to make the data available for other, or to simply view the data, all of these are valid reasons. R gives plenty of options to achieve this, such as the `write.table` and `write.csv` functions. However, data needs to be properly formatted to get clean data out of it.

A simple example of this issue is the output from the `summary` function. It gives a great overview of your data in some basic statistics. But it only looks great when printing the results to the screen. When writing to a file it always has some strange undesired artifacts. These kind of issues only occur more often when you have specific packages for rare use-cases.

So writing to a file is not optimal, but with just printing we miss the entire point of saving the data. Luckily there is the `sink` function. This allows for writing everything to a file instead of the screen. An example of using `sink` can be seen below. Note that we call `sink` again to close the process, otherwise everything will continue to be written to the file until an error occurs or you quit R. 

```r
sink("output.txt")
print(some_variable)
sink()
```

As in the example, we specify an output file to write the data towards. I recommend to initially always have it be a simple text file (.txt). With this format the data is always viewable. Once you have checked and are sure that another format can be used, simply change the extension to the format of choice and re-run the program. In this manner `sink` will be a valuable tool for you to use in debugging and even for getting strange data in simple text file, which is always handy to be able to do.
