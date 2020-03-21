---
layout: post
title: "Python 2: List and Dictionary"
date: 2017-12-07
categories: Python
permalink: /2017/12/07/python-2-list-and-dictionary/
author: Pramesh
---

Welcome to 2nd post on Python. Please visit first one on [variables and tuples][variables] before starting this one. In this post, I’ll be discussing lists and dictionaries. Just like tuples, lists  and dictionaries are also data structures in Python but with different purpose and definition.

1. List
2. Dictionary

## List
List is a mutable data structure that stores data like a tuple does. 
The different between tuple and list is that tuple is immutable and list is mutable. 
Tuple is written in round brackets while list is written in square brackets. 
List is an **editable sequence** of data. As it is mutable, elements can be added/deleted to list. 
Like tuple, it supports multiple data types in a single list and storing elements in multidimensional way.

**example:**

```Python3
names = ["Ram", "Harry", "Steve"]
print(names)         #prints ['Ram', 'Harry', 'Steve']
names.append("John")
print(names)         #prints ['Ram', 'Harry', 'Steve', 'John']
```

Accessing elements is same like in tuple. Indexing starts at 0 from left and at -1 from right.

```Python3
print(names[0])  #prints Ram
print(names[-1]) #prints John i.e after running append
```

Operations like append and extend are used to edit the existing the list. 
Since list is mutable the original instance of list gets changed with such operations. 
List is best used in Python as dynamic substitute of array.

### Append and Extend
**Append** places the element at the last index of the list while **extend** extends the list with the element passed to it and the element should be a 
sequence.

**example:**
```Python3
names = ["Ram", "Harry", "Steve"]
new_names = ["John", "Liana"]
print(names)
names.append(new_names)          #places list new_names as the last element
print(names)
names = ["Ram", "Harry", "Steve"]
names.extend(new_names)          #places the elements of new_names at last of list as individual elements
print(names)
```
Here, **append** simply appended the entire list as the last element of the list. 
It didn’t care about the contents of the list and placed it as the last element. 
While **extend** recognized new_names as list and extended the original list with the elements of **new_names** list.

List supports many other operations to insert elements, delete them and change list. 
Some of them are **pop, reverse, sort, remove, index, insert, len, max and min**. Check out these methods. 
It’ll make a good exercise to know more about lists.

## Dictionary
Dictionary is a data structure that stores data in form of keys and values. It can be thought of like Maps in other languages.

**example:**

```Python3
country_capital = {"Nepal": "Kathmandu", "India": "Delhi", "China": "Beijing"}
```

Here **country_capital** is a dictionary with Nepal, India and China as keys and Kathmandu, Delhi and Beijing as values. 
Just like in Map, keys should be unique and values can be duplicated. 
Numbers, strings and tuples can be made keys whereas values can be numbers, strings, tuples and list and dictionaries as well.

Like list, dictionary is also a mutable data structure which allows us to manipulate the elements in dictionaries. Following points can be used to explain lists:

* Similar to Map in Java
* Contains key-value pair
* Each key is separated from its value by a colon ( : )
* Each items are separated from each other by comma ( , )
* And the items are enclosed within the curly braces like this { }
* Keys are always unique but values may be duplicate
* Keys are immutable like strings
* Dictionaries can be updated since they are mutable

```Python3
_dictionary1 = {"01":”Room 01”, “02”: “Room 2”, “03”: “Room 03”, “977”: “Nepal”}
```

You can use square brackets to access the values corresponding the key

```Python3
_dictionary["977"] #outputs Nepal
```

While updating a dictionary, if a key already exists then the value gets updated otherwise it is stored as a new item.

```Python3
_dictionary[”ktm”] = “Kathmandu” #New item
_dictionary[‘”977”] = “NP”       #Value gets  updated for given key
del _dictionary[‘key’]           #deletes entry with given key
_dictionary.clear()              #clears all the entry in dictionary
del _dictionary                  #deletes the entire dictionary
```

Since dictionary is mutable, it can be extended just like list.

**example:**

```Python3
country_capital = {"Nepal": "Kathmandu", "India": "Delhi", "China": "Beijing"}
country_capital.update({"France": "Paris"})
print(country_capital) #{'France': 'Paris', 'India': 'Delhi', 'China': 'Beijing', 'Nepal': 'Kathmandu'}
```

France and Paris are inserted as key and value in original dictionary in above example. 
There are various other operations available to access/modify dictionary. 
That would be a good exercise. Some methods are **len, str, copy, has, items, keys, setdefault, update and values.**

This much for this post. There are other things about lists and dictionaries that will be covered in future posts. Please check for updates.

I hope this post was fruitful. If you find anything confusing, need to ask anything or if you have any suggestions, please leave a comment. 
I’ll be happy to respond.

See you in the next one. Cheers 

[variables]:/2017/12/03/python-1-variables-and-tuples/