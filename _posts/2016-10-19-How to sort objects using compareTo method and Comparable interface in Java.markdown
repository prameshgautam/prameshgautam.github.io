---
layout: post
title:  "How to sort objects using compareTo method and Comparable interface in Java"
date:   2016-10-19
categories: Java
permalink: /2016/10/19/how-to-sort-objects-using-compareto-method-and-comparable-interface-in-java/
author: Pramesh
comments:true
---


Hello guys,

welcome to another post. In this post we are going to see how to sort our custom objects by using Comparable interface in Java. We will create a Person class and sort

its objects on the basis of age of Person we create.Code explained below

<script src="https://gist.github.com/prameshgautam/b219a1c37b4e545589e9fb9f0d120942.js"></script>

Here is the code explanation:

* First create **Person** class with name, age and gender attributes.
* Then implement **Comparable** interface with Person as parameter so that we can use Person to compare in compareTo method.
* We override **compareTo** method and compare age of the Person passed as parameter and current Person object. On that basis Person objects are sorted.
* The sorting process is performed as:
At first another Person object is passed as parameter to **compareTo** method. We have compared age of person to sort in ascending order. It we reverse the compare signs, the output will be in descending order. **less than 0**, **0** and **greater than 0** values should be returned by compareTo method which indicates less than, equal and greater than respectively. We can simply write return **this.age – o.age;** to compare on age basis. While **Collections.sort(personList)** gets executed, the Person object on the list will be sorted which can be checked by printing the value of **personList**.

If we run this program, the output will be:

`[{name: John, gender: Male, age: 20}, {name: Stacy, gender: Male, age: 21}, {name: Harry, gender: Male, age: 25}]`

Please leave comments for any suggestions, questions or random stuff. See you in next one.

Cheers 



