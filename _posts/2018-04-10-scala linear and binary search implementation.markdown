---
layout: post
title:  "Scala: Linear and Binary Search Implementation"
date:   2018/04/10
categories: Scala
permalink: 2018/04/10/scala-linear-and-binary-search-implementation/
author: Pramesh
---


Welcome to my first article on Scala. In this post let’s discuss the implementation of linear and binary search in scala. These are some of the popular searching algorithms. Lets see how to implement them in scala.

# LINEAR SEARCH
Linear search is searching technique that searches for any item serially from the first element until the item is found in any collection. It scans the element one-by-one until the item that is searched matches the item currently scanned. More details here.

**Complexity**

**Worst case**: O(n) => if the item to search is present at last index

**Best case**: O(1) => if the item to search is present at first index

<script src="https://gist.github.com/prameshgautam/95490733bd58fa7ddf1cde063fade35f.js"></script>

In above code, the search key is compared with the head of list and if they match true is returned otherwise the process continues for the tail of the list recursively until the key is found or the list is empty.

Whenever you run this code, it will print true if the  value is found and false otherwise.

# BINARY SEARCH
Binary search is a searching technique that divides the given list into two halves and recursively searches in each half by comparing with the given search key. One condition is that the given list must be sorted to apply this algorithm. This algorithm is faster than the linear search since the complete list should not be scanned to find the required item. In each iteration the list is divided which gives the complexity to be O(log n). More details here.

**Complexity**

**Worst case**: O(log n)

**Best case**: O(1)

<script src="https://gist.github.com/prameshgautam/5bc6156bf03723b43ad9cc5812196fbd.js"></script>

Whenever you run this code, it will print true if the  value is found and false otherwise. This code is for the elements that are sorted in ascending order. If you are to implement for the one in descending order, just swap the comparison logic.

I hope this article will be of use. If there are any queries/suggestions please comment them. I’ll see you in the next one. Cheers 🙂

{% include disqus.html %}

