---
layout: post
date: 2022-06-25 09:00:00 +0100
tags: Python
categories: Programming
title: 'Ellipses instead of Pass keyword'
---

During software development it is common to declare functions and classes to implement later. To prevent crashes we usually use a statement that prevents the function from loading or a statement that does "nothing" and thus lets the program continue. In Python the keyword `pass` is usually used for this purpose. It basically skips the block of code and continues on with the program. Running the below snippet will do nothing.

```python
def some_function():
    pass

some_function()
```

In a sense, the meaning behind the keyword `pass` will depend on the context. Often it will indicate that the actual code still needs to be implemented. However this is not necessarily the case as `pass` can be used functionally. This could cause confusion in larger projects.

A clearer way to denote that code still needs to be implemented in Python is with ellipses. Ellipses are the three little dots (`...`) that indicate the omission of text in conventional writing. This way would be a lot safer if the entire team is familiar with Python and give more functional context to `pass` when used. Personally, I favor the readability of `...` over `pass`. It makes the purpose of the statement clear without disambiguating between function and communication, while doing the exact same thing.

```python
def some_function():
    ...

some_function()
```
