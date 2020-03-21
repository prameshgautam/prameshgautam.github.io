---
layout: post
title: "Python 3: Slicing Explained"
date: 2017-12-26
categories: Python
permalink: /2017/12/26/python-3-slicing-efficient-method-to-access-elements/
author: Pramesh
---

Welcome to 3rd post on Python. In this post, I’ll discuss slicing. Just as the name suggests, slicing is to slice data 
into parts and get the required part from that data. As you learn more and more Python, you’ll come across slicing in 
different data structures in different applications. So let’s get started.

## Indexing
The most common indexing used in Python is **0-indexing**(i.e: position of the element at leftmost position is 0 
and increases by 1 as we move to right side). We can also access elements with **-1 index**(i.e: index of the element 
at the rightmost position is -1 and decrements by 1 as we move to left).

```Python3
sentence = "This is a slicing example"
print(sentence[0])  #prints T
print(sentence[1])  #prints h
print(sentence[24]) #prints last e
print(sentence[-1]) #prints e
print(sentence[-2]) #prints l
print(sentence[-25])#prints T
```

In the above example, **sentence[0]** prints **T**, as we have used **0-index** and **sentence[-1]** 
prints e which is the last element and this is due to **-1 index.**

**Remember: 0-index starts at leftmost position and increments by 1 as we move to the right side and -1 
index starts at rightmost position and decrements by 1 as we move to left side.**

## Accessing elements
Now as we know two forms of indexing used in Python, we can start accessing elements from any 
collection(string, list, tuple, dictionary). Syntax for slicing goes like this:

```Python3
variable[start_position:end_position:step]
```

* start_position: position to start accessing element. This position is **inclusive**, hence is included while accessing element.
* end_position: position to stop accessing element. This is an **exclusive**, hence is not included while accessing element.
* step: steps to increment the position while traversing through the collection. Step can be either negative or positive. Negative will access elements through left and positive will access elements through right.

```Python3
countries = ["Nepal", "India", "USA", "China", "UK", "Canada", "Japan"]
print(countries[0])         #prints Nepal
print(countries[1:4])       #prints ['India', 'USA', 'China']
print(countries[0:6:2])     #prints ['Nepal', 'USA', 'UK']<span id="mce_SELREST_start" style="overflow:hidden;line-height:0;"></span>
print(countries[-5:-1:2])   #['USA', 'UK']
print(countries[4:0:-1])    #prints ['UK', 'China', 'USA', 'India']
```

In case of **countries[0:6:2]**, elements from 0 till 6 index are printed with **step** of **2**. Index **6** is **exclusive** and **0** is **inclusive** in this case. If we don’t give the value for step, then it is 1 by default(eg: **countries[1:4]**)

**countries[4:0:-1]** is the example of **negative** step. It starts to print at **index 4** and moves till **0**. Step is being **decreased** by **1** in this case. Element at **index 4** is **inclusive** and element at **index 0** is **exclusive**.

## Trick: Reverse with slicing
```Python3
word="Hello"
rev = word[::-1]
print(rev)   #prints olleH
```

Since there are no start and end positions, all elements are printed. Due to step being -1, string is reversed.

## Slice function
Slicing can also be used in the form of a function.  slice function takes the following syntax

`slice(start_position, end_position, step)`

```Python3
numbers = [1, 2, 3, 4, 5, 6, 7]
s = slice(1, 4, 2)
print(numbers[s])
```
Here we’ve used slice function and assigned it to variable s. This is pretty easy to understand.

I would like to end the post here. I hope this post was helpful. Please leave comments for any queries and suggestions. 
I’ll see you in the next one. Cheers 