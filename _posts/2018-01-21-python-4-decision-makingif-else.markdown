---
layout: post
title: "Python 4: Decision Making(if…else)"
date: 2018-01-21
categories: Python
permalink: /2018/01/21/python-4-decision-makingif-else/
author: Pramesh
---

Welcome to 4th Python post. In this post, I’ll be discussing decision making.

# Introduction
As simple as it sounds, decision making is the technique of making decisions based on some conditions. 
Suppose you’re developing an application for college admission and only want to admit students whose age is greater 
than 18, then, in this case, you check if age is greater than 18 or not and execute the admission process only if age 
is greater than 18. This is a simple example of decision making. We’ll see some more.

## Boolean expressions
Before understanding decision making, please make sure you know about boolean values  True and False and operators and, or, not.

Review:

* True and True = True
* False and True = False
* True or False = True
* not True = False
* not False = True

Note:

* and will evaluate True only if both the conditions are true
* or will evaluate True if one of the conditions is true
* not will negate the condition
* All values except 0 and None are considered True in Python and 0 and None are considered False

## if…else
if…else is the decision-making structure along with following structures

* if…elif….else
* nested if

**Python doesn’t support switch statements**

## Syntax
### if statements

```Python3
if expression:
    if_suite
```

if_suite is executed only if the **expression** evaluates to **True**. 
Please mind the colon at the end of **if** and **else** lines. 
It denotes that the inner block starts from that code. 
Indentation denotes the inside code. i.e the code that is written in after some spaces is the inner code for the outside if or else block

### if…else statements

```Python3
if expression1:
    if_suite
elif expression2:
    elif_suite
else:
    else_suite
```

if the `expression1` is `True` then `if_suite` is executed. If it is `False` then it searches for the corresponding `elif` block 
and evaluates `expression2` from the first `elif` it finds. If `expression2` is `True`, then `elif_suite` is executed. 
If `expression2` is `False` then it will again search for another `elif` block. As it won’t find another `elif` block in the 
example above, `else_suite` is executed. Else block is the default block if none of the conditions are `True`.

## Nested statements

```Python3
if expression1:
    statement(s)
    if expression2:
        statement(s)
    elif expression3:
        statement(s)
    else:
        statement(s)
else:
    statement(s)
```

In case of nested if, evaluation strategy is same as above, but it will go on evaluating the inner if statements and 
only go to the outside block if none of the inner blocks can be executed.

**Example:**

```Python3
age = int(input("Enter age"))
if age >= 18:
    if 18 <= age <= 30:
        print("between 18 and 30")
    elif 30 < age <span
        print("between 30 and 50")
    else:
        print("greater than 50")
elif 10 <= age < 18:
    print("between 10 and 18")
else:
    print("below 10")
```

As an exercise, please try to trace the above if…elif example. Please leave comments if you have any queries/suggestions. 
I'll be writing about loops in next post. See you in the next one. Cheers
