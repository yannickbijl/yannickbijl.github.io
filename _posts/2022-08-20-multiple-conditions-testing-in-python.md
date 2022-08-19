---
layout: post
date: 2022-08-20 00:00:00 +0100
tags: Python
categories: Programming
title: 'Multiple Conditions Testing in Python'
---

Simple conditions are easily taken care of with if-else statements. In cases that multiple conditions need to be satisfied the statements are extended using an **AND** operator. This can lead to complex, long, and messy statements as seen in an example below.
```python
a = 100
b = 10
c = [1, 2, 3, 4, 5]

if a >= 90 and b <= 50 and len(c) == 5:
    print("all true")
else:
    print("all false")
```

In Python these statements can be made clearer with the `all` keyword. Simply put your conditions in a list and call them in the `if` branch with the keyword `all`. This way it is immediately clear that all conditions are satisfied. And with proper formatting it is easier to read and modify the different conditions.
```python
a = 100
b = 10
c = [1, 2, 3, 4, 5]

conditions = [a >= 90,
              b <= 50,
              len(c) == 5]

if all(conditions):
    print("all true")
else:
    print("all false")
```

Where just a single condition out of multiple needs to be satisfied we use an **OR** operator. Similarly with **AND** this can lead to difficult to read statements, especially later on when you have to revisit your own code.
```python
a = 100
b = 10
c = [1, 2, 3, 4, 5]

if a >= 90 or b <= 50 or len(c) < 5:
    print("at least one true")
else:
    print("all false")
```

In Python these statements can be made clearer with the `any` keyword. This follows again the same logic as above. In this case the conditions are chained with the **OR** operator. Note that with **OR** only a single condition needs to evaluate as true.
```python
a = 100
b = 10
c = [1, 2, 3, 4, 5]

conditions = [a >= 90,
              b <= 50,
              len(c) < 5]

if any(conditions):
    print("at least one true")
else:
    print("all false")
```

The lists can be larger than 3 conditions. The larger the number, the more useful the methods `all` and `any` will be. However, in the case you have 2 conditions (or 3 really simple ones) just use an `if` statement in combination with `and`/`or`. Readability matters in the end, and this will depend on the number and complexity of the conditions.
