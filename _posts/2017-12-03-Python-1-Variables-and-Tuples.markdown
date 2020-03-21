---
layout: post
title: "Python 1: Variables and Tuples"
date: 2017-12-03
categories: Python
permalink: /2017/12/03/python-1-variables-and-tuples/
author: Pramesh
---

Welcome to first Python post. I am planning to prepare a series tutorial on Python. I will post new articles time to time 
from basics. In this post, I’ll be covering on variables and tuples. I’ll be covering these topics in this post:
1. Variable
    * Variable Types
    * Rules for Naming a Variable
2. Tuple

# Variable
Variable is a name that is used to store any value we want to use. In any programming language, 
values do not matter in most of the cases if they cannot be used or accessed. 
For example: if you are writing a function to calculate the square of a number then you need to use the value the user inputs. 
To use that value, we need to have it stored by name and that name is called a variable. Try this in Python.

```Python3
number = 5
```

Here 5 is the **value** and **number** is the **variable** in which we want to store the value. 
In the machine we are using, variable number will be storing value 5 and it will reserve memory. 
After entering this line in some IDE or Python shell, we can access the value of number.

## Variable Type
Variables have different data types. For eg: int, str etc. Unlike some other Programming languages, in Python, we do not 
need to specify the type of variable during its creation. Python will automatically detect the type of the variable and 
this feature of Python is called **dynamic typing**. In the above example, try the following code.

```Python3
type(number)
```
output: `<class ‘int’>`

Here we can see, Python automatically detected the type of variable number to be int. Same is the case for other types of variables.

## Rules for naming a variable
* Python variables should start with _ or alphabet
    * example:- _first_name, _last_name, dob, gender, etc
* Python allows you to assign single value to several variables simultaneously
    * example:- _sum = _total = _average = 97
* You can assign a variable with different data types like integer, float, string, etc. without mentioning the data type
    * example:-

```Python3
_first_name = 'Ram' #Assigning string
_last_name = "Sth"  #Assigning string
_age = 25           #Assigning integer
_salary = 9000.00   #Assigning float
```

# Tuple
Tuple is a data structure available in Python. It is used to store data like in arrays with indexes. 
Tuple is an **immutable** data structure, so **cannot be updated once created**. Tuple is written by enclosing data in ().

In below example, names is a variable of type tuple that stores 3 values. 
Tuple values can be accessed by using **0** index(i.e. index of first element is 0). To access data from end position, 
indexing starts **from -1 and progresses to -2, -3** and so on.

```Python3
names = ("Ram", "Harry", "Steve")
print(names[0])  #prints Ram
print(names[1])  #prints Harry
print(names[2])  #prints Steve
print(names[-1]) #prints Steve
print(names[-2]) #prints Harry
print(names[-3]) #prints Ram
```

Tuples are used as **substitute of Arrays** in Python. But Tuples can store data of **different types**.

```Python3
names = ("Ram", "Harry", "Steve", 9)
```

This is valid definition in Python.

We can use Tuples in a multidimensional way as well. One application would be matrix implementation.

```Python3
matA = ((1, 2, 3),(4, 5, 6),(7, 8, 9)) #A 3X3 matrix definition   
print(matA[0][2]) #prints 3
print(matA[1][2]) #prints 6
print(matA[2][2]) #prints 9
```

Similar is the case for tuple of any higher dimension. Python provides various methods to operate on tuple. Some of them are **max** and **min**. These are worth taking a look at and will be helpful while working with tuples.

This much for this post. I hope this post is useful in getting started with Variables and Tuples. If you have any queries or need more explanation, please leave a comment. I’ll be happy to help.

See you in the next one. Cheers

