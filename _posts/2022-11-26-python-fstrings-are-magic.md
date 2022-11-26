---
layout: post
date: 2022-11-26 00:00:00 +0100
tags: Python
categories: Programming
title: 'Python f-Strings are Magic'
---

Formatting strings with variables is a common task in programs. Through the years, different methods have become available to achieve this in Python. The easiest, but also least efficient, method is by concatenating the strings and variables. For this to work the variables need to be strings, so it is recommended to convert all variables into strings with the `str()` function.

A second method is the old-style format method. This uses the `%` symbol for the places where a variable should come. The variables are given in order within a tuple (an immutable list). Formatting is done through indicators after the `%`. In this case variables are converted to strings due to the `s`.

The new-style format method is styled in more 'pythonic' manner. Instead of the `%`, curly brackets `{}` are used to denote the placing of the variables. Then `.format()` is called with all the needed variables. Within the brackets one can place integers to denote a specific variable. If both brackets contain the value `1`, then only the variable `price` will be used.

```python
items, price = ["groceries", "clothing", "insurance"], 228.65

str_format1 = "I paid for " + str(items) + " and it costs " + str(price)
str_format2 = "I paid for %s and it costs %s" % (items, price)
str_format3 = "I paid for {} and it costs {}".format(items, price)
```

The newest method is f-strings. Personally, I find this the most readable method. An f-string starts with a `f` or `F` before the quotation marks. Variables are placed within the brackets directly in the string. It is also possible to place actual code within the brackets, such as calculations and function calls. Preferably variables are well defined before using them in strings, but its great there is the option.

```python
items, price = ["groceries", "clothing", "insurance"], 228.65

str_format4 = f"I paid for {items} and it costs {price}"
```

It is also possible to specify specific formatting similar to the old-style format method. After the variable name use a `:` followed by the necessary flags for the formatting. A value can also be directly supplied.

Some common flags are for formatting decimals, using `.<number of digits>f`, or getting the variable name with the associated value with `=` (Note that there is no `:`). Scientific notation can be done using the flag `e`.

It is also possible to center, left align, or right align using `^`, `<`, and `>` respectively followed by the amount of space it needs to be justified with. This can be combined with symbols as seen below. Another common use is formatting datetime objects. 

```python
value = 1234.123456
print(f"Some value {value:.2f}") # Some value 1234.12
print(f"Some value {value:.4f}") # Some value 1234.1234
print(f"Some {value=}") # Some value=1234.123456
print(f"Some value {value:e}") #Some value 1.234123e+03

value = "abcd"
print(f"|{value:^10}|") # |   abcd   |
print(f"|{value:-<10}|") # |abcd------|
print(f"|{value:=>10}|") # |======abcd|

import datetime
time = datetime.datetime.now()
print(f'{time:%Y-%m-%d %H:%M}') # 2022-11-25 15:39
```

Of course, these are only some examples of the formatting that can be done with f-strings. There are many more options available just a quick google search away. At the very least I hope this gives a starting point for using f-strings and seeing the great use-cases with them.
