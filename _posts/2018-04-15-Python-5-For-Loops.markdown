---
layout: post
title: "Python 5: For Loops"
date: 2018-04-15
categories: Python
permalink: /2018/04/15/python-5-for-loops/
author: Pramesh
---

Welcome to my new post on Python. In this post, for loops will be covered.

## Introduction
Looping means to repeat. We use this technique in programming to repeat tasks. We define the condition for repetition or 
the number of iterations to repeat and according to that condition, tasks will get repeated.

In Python, there are two kinds of looping statements. For loop and while loop. In this post for loop will be discussed. 
While loop will be discussed in next post.

## For Loop
For loop is one of the mostly used looping techniques in many programming languages. 
In for loops, we define the number of iterations to loop. We can also define inner loops also known as nested loops.

### Syntax
Syntax of for loop is:

```Python3
for var_name in sequence:
    #do something
```
Here var_name is the variable that holds the current value. The current value is extracted by traversing the sequence.

```Python3
for i in [1,2,3,4]:
    print(i)
```

This code will print from 1 to 4. In each iteration i holds the value it extracts from the **list[1,2,3,4].**

## What does it mean by sequence?
Sequence or iterable(as called in languages) is a data type that can be traversed from beginning to end by incrementing the position. In above example, we’ve used list for traversing. Other data structures like tuple and dictionary can also be used for traversal. range function can also be used. Just remember that must be a data structure that can be traversed.

## Nested Loops
Nested loop means using a loop statement inside another loop statement. We can use for loop inside loop statement and that is called a loop statement.

```Python3
for i in [1, 2, 3, 4]:
    for j in range(i):
        print("i = {0}; j = {1}".format(i, j))
```
Output of above code will be:
```Python3
i = 1; j = 0
i = 2; j = 0
i = 2; j = 1
i = 3; j = 0
i = 3; j = 1
i = 3; j = 2
i = 4; j = 0
i = 4; j = 1
i = 4; j = 2
i = 4; j = 3
```

As you can see, every iteration of inner loop runs for every iteration of outer loop. i.e:

* while i is 1, j runs from 0 to 0
* while i is 2, j runs from 0 to 1
* while i is 3, j runs from 0 to 2
* while i is 4, j runs from 0 to 3

For `range` function, last index is exclusive. You can increasing nesting to any level. 
Using deep level of nesting will increase the number of iterations. So keep that in mind.

## Looping in dictionary
In previous examples, looping was done in list. Similar is the case for tuples as well. Looping in a dictionary is a 
bit different. Its because, dictionary consists of key, values and we can choose to loop using both key value or only 
of them. Post on dictionaries is available here if you want to learn about dictionaries.

```Python3 
country_cap = {"Nepal": "Kathmandu", "India": "Delhi", "China": "Beijing", "USA": "Washigton"}
 
#looping in both key and value
for coun, cap in country_cap.items():
    print("country = {0}; capital = {1}".format(coun, cap))
 
#looping onlt in keys
for coun in country_cap.keys():
    print("country = {0}".format(coun))
 
#looping in values
for cap in country_cap.values():
    print("capital = {0}".format(cap))
```

In above code, function `items()`, `keys()` and `values()` return the iterable sequence. `items()` returns sequence of 
pairs of key and value, `keys()` return sequence of keys and `values()` returns sequence of values. 
Looping is then done in the similar way as discussed earlier.

## Loop Control Statements
We can control the running iterations of loop. For that Python provides two keywords: `break` and `continue`.

## break
* Break terminates the currently running loop and resumes execution from the  statement immediately after the loop
* It can be used in both for and while loop
* In case of nested loops, it stops the execution of the innermost loop

```Python3
for item in [1, 2, 3]:
    for letter in 'hello':
        if letter == 'l':
            break
        print("inner loop letter = {0}".format(letter))
    print("outer loop item = {0}".format(item))
```

On running above code, it can be seen that the outer loop runs three times according to the items of list but the inner loop run only two times for each outer loop. That is because l is the item in which loop is stopped. i.e: loop runs for h and e. After h and e, the loop is terminated.

## continue
* It skips the currently running statement of the loop but resumes the remaining statements of the same loop
* While comparing with break: `break` will stop the current loop while `continue` will skip the selected statement of current loop and continue with others.

```Python3
for item in [1, 2, 3, 4, 5]:
    if item == 3:
        continue
    print(item)
```
On running the above code, it can be seen that 3 is not printed due to continue. All other numbers except 3 are printed. 
The iteration in which item is 3 is skipped and remaining iterations are executed.

I hope this post was useful to you. I’ll update if I find anything missing. Please leave comments if you have any 
queries/suggestion. I’ll see you in the next one. Cheers

