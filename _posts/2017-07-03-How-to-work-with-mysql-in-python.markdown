---
layout: post
title: How to work with MySQL and Python using PyMySQL?
date: 2017-07-03
categories: Python
permalink: /2017/07/03/how-to-work-with-mysql-in-python
author: Pramesh
---

Welcome to my first Python post. In this post, we’ll see how to work with MySQL database in Python. This tutorial assumes your familiarity with Python. So let’s get started. In this post, we’ll create a program that will insert data from user to database, show data in the terminal, delete data or update data. Python list and control structures(loop, if….else) are also used in this program.

1. Introduction
2. Installation of PyMySql
3. Working with Database(Create, Insert, Update, Delete)

# 1.Introduction
MySQL is a relational database and Python is a programming language. We’ll be working with these two technologies. We’ll store our data in MySQL database and perform operations in it from Python. We’ll be using a Python module named PyMySql for this tutorial. There are various modules available for database connection but we’re choosing it over others as it is written in pure Python.

# 2.Installation of PyMySQL
Run this command to install pymysql.

`pip3 install pymysql`

# 3.Working with Database
We’ll work with four type of database operations(`create`, `insert`, `update`, `delete`) that are a part of  CRUD operations (create, read, update, delete).

## Prerequisites
Please have these things setup on your system before trying this tutorial.

Create database named test in localhost server.
Set username = root and password = root.
Create table named test_table in test database.

## Code
You can get the complete code at my github page from [here][1]. Required parts are only explained in this post.

## Create Connection
In your code, import PyMySQL module and create the connection variable.
`conn = pymysql.connect(host=HOSTNAME, user=USER, password=PW, db=DB)`
Set these variables according to your environment. This will create the connection object. Our other tasks are dependent on this object and we’ll perform our tasks accordingly.

## Insert
In code, have a look at `insert_records()` function. It is designed to take input until the user wants, save them in a list and insert records one by one.

<script src="https://gist.github.com/prameshgautam/f849f1f0e468f7cba61ce86c712b1af2.js"></script>

Input is being taken as per users’ desire and they are stored as queries in `insert_queries` list. `prepare_insert_query()` function creates all those queries. Loop is being applied in that list and cursor object executes those queries. `conn.commit()` will commit the results and if any exception is thrown then rollback is applied via `conn.rollback()`.

## Fetch Data

<script src="https://gist.github.com/prameshgautam/a046a2ed49cafd33fb0ea5bccbc87081.js"></script>

select query is passed to `see_records()` function. `fetchall()` method from cursor object lists the output which is iterable. In that iterator, loop is applied and the records are displayed.

## Update and Delete
Similar is the case for update and delete part as well. Required queries are passed to cursor object’s execute method and the query is executed. In the cases where data is to be modified, `commit()` and `rollback()` methods have been used. They help to prevent the atomicity of database.

Python connection with MySQL is fairly simple. You just create the connection, fetch cursor object and run the queries. It is up to you to tune the program as per your needs. Please leave comments if you need clarification in part. Do share it if you think it is useful.

## References
1. [PyMySQL](https://pymysql.readthedocs.io/en/latest/)

See you in the next one 🙂

[1]: https://github.com/prameshgautam/ramzavil_python/blob/master/dbConnect.py

{% include disqus.html %}

