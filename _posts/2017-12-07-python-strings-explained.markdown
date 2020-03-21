---
layout: post
title: "Python: Strings Explained"
date: 2017-12-07
categories: Python
permalink: /2017/12/07/python-strings/
author: Pramesh
---

After writing posts on variables, tuples, lists and dictionaries, I realize I’ve missed Strings. 
I missed one of the core parts of any programming language. So instead of naming it the 3rd post on Python, 
I’m simply naming it Python-Strings. Hope it makes sense.

So let’s start.

# Introduction
String, in a very basic definition, is anything that is to be used literally in a programming language. 
It is a sequence of characters, it is a literal constant. It doesn’t have any meaning except its literal form. 
In Python, it is no different. To denote anything in its literal form, we use strings. 
If we write anything, data of any type, enclosing it in quotes will make a String.

```Python3
name = "Nepal"
name = 'Nepal'
name = """Nepal"""
name = '''Nepal'''
```

Here, **name** is a variable of **str** type. Hence it is a String. 
Variable name is written in different ways, we’ll see different representations in next section.

## Representation
In Python, Strings can be represented in three ways.

* Single quoted string(‘…’)
* Double quoted string(“…”)
* Multi-line or Triple single/double quoted string(“””…””” or ”’…”’)

Python supports writing Strings either inside single quotes or inside double quotes. 
This provides us with an advantage of using the pattern we like most and eliminates the use of escape sequence while writing quotes. 
We can enclose double quotes inside single quotes and single quotes inside double quotes without using an escape sequence.

```Python3
message = "I'll follow rules"
message = 'I\'ll follow rules'
```

Both of these are valid definitions in Python.

Three quotes can be used to write string in multiple lines.

```Python3
message = """
This is a
multi line
string in Python
"""
```

Here a multi-line string is written by enclosing in triple quotes. 
Single quotes can also be used with this structure. 
This way is mostly followed for writing docs in Python files.

## Accessing values in Strings
Just like we did in tuples and lists, we can access elements of String with 0 or -1 indexed structure.

```Python3
name="Nepal"
print(name[0])  #prints N
print(name[1])  #prints e
print(name[2])  #prints p
print(name[-1]) #prints l
print(name[-2]) #prints a
```

Indexing starts from **0**(starting at beginning/left) and **-1**(starting from end/right)
To learn more about slicing checkout this [post][slicing]. For now, just understand 0 and -1 indexing.

```Python3
name="Nepal"
print(name[1:4])  #prints epa
print(name[-4:-1])#prints epa
```

Here **epa** is printed because **name[1:4]** accesses elements from index 1 to index 4(1 is **inclusive** and 4 is **exclusive**) 
i.e elements from 1 to 3 index are printed.
Similar is the case with **name[-4:-1]**. -4 is inclusive and -1 is exclusive in this case which prints **epa** as in the first case.

I’ll end the post here. You can move on to advanced topics on String after having a basic understanding. 
For any queries, suggestions, feedback please feel free to drop a comment.

I’ll see you in the next one. Cheers

[slicing]: /2017/12/26/python-3-slicing-efficient-method-to-access-elements/

