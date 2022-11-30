---
layout: post
date: 2022-07-23 00:00:00 +0100
tags: Python
categories: Software-Development Programming
title: 'In-place Variable Swapping in Python'
---

In many algorithms, such as bubble sort, there is a need to swap values. In most cases this happens in the same array or list object. Others require the swapping of variables. A simple solution is through the use of a temporary variable that safeguards the original value.
```python
a = 1
b = 0 

temp_a = a # 1

a = b # 0
b = temp_a # 1
```

In Python it is easier to swap variables. There is no need to use a temporary variable. You can simply swap them by reordering them as in the following example. This simple reassignment works also for more than two variables.
```python
a = 1
b = 0

a, b = b, a # 0, 1
```

In all cases the order is what matters with the reassignment. This same logic can be used for the assignment of values. Or the reordering of multiple variables. This works regardless of the number of variables. Naturally it is also possible to mix variable and values
```python
a, b, c, d = 0, 1, 2, 3

a, b, c, d = d, c, b, a # 3, 2, 1, 0

a, b, c, d = d, c, 5, a # 3, 2, 5, 0
```
