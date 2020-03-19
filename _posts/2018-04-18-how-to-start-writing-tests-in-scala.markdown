---
layout: post
title:  How to start writing tests in Scala?
date:   2018-04-18
categories: Scala
permalink: 2018/04/18/how-to-start-writing-tests-in-scala/
author: Pramesh
---


Welcome to another post in Scala. In this post, I’ll be discussing writing unit tests in Scala. Some form of unit testing is available in almost all major programming languages these days.

# WHAT ARE UNIT TESTS AND WHY ARE THEY IMPORTANT?

Before going to technical part, let’s discuss what actually unit tests are and why they are so much 
important to be a requirement in almost every software development.
That is because they assure you that your code won’t break(not 100% though).
A certain level of assurance is provided by proper unit testing.

Unit tests are some kind of code that helps in testing the source code we write.
As its name implies, unit testing is done to test the units of code. Instead of running the application
end to end,
unit testing is used to test only parts of the code. They are called units.
A unit can be a method, a simple statement or a module. Whenever we create new functionalities or change 
existing ones, we need to do unit testing to be sure that the thing we’ve developed is fine. 
For that, we identify the parts that are needed to be tested and write code for that. 
For detailed information, [Wikipedia][wikipedia] is always there to help :).

Unit testing is not an end to end testing. It is in fact testing of units by identifying them to make 
sure they as an individual unit are working as expected. Integration and other forms of testing are 
needed and cannot be replaced by unit testing.

# HOW TO WRITE UNIT TESTS IN SCALA
For implementation part, I’ll be using a project I’ve created specifically for the purpose of this 
tutorial. You can clone it from [GitHub][project]. It is an sbt project. 
If you want to learn more about [sbt][sbt] you can see the official docs [here][sbt_docs]. 
I will explain the parts that are needed for this tutorial. Let’s start.

We’re using scala/sbt project for this
sbt dependencies are named in build.sbt file(just like in pom.xml in case of maven)
sbt automatically downloads those dependencies
I’ll be using linear and binary search which I’ve written for this blog to demonstrate testing. 
Visit Scala: Linear and Binary Search Implementation to learn about their particular implementation.

Installing Scalatest
To add scalatest library to your project, add this line to your build.sbt file

`libraryDependencies += "org.scalatest" %% "scalatest" % "3.0.5" % "test"`

This will download scalatest and add to your project’s dependencies. 
Other libraries like JUnit can also be used. However, we’ll be using scalatest for this post.

# Writing Test
Writing tests in scala is fairly easy. 
The only thing to do is to define a test method with some name and write test code inside it.
<script src="https://gist.github.com/prameshgautam/94db621ae7ae1de56400ad5f6ea8788e.js"></script>

In the above code, two tests are defined and they are differentiated by their names.
One is named `linear search` test and other is named `binary search test`. 
You can run these tests from IDE or from SBT with `run` tests command. 
To run specific tests `testOnly test_location` command can be used.

Try the code mentioned below. 
It will run the code you write in before and after block before and after each test defined. 
These methods are used for setting up required things before running tests and for clean up tasks after the 
test is completed.
<script src="https://gist.github.com/prameshgautam/cc0e7d643ad399cc8872aa0e9b54df12.js"></script>

# Behaviour Driven Development
Scalatest also supports writing test in BDD style and defining specifications as tests.
<script src="https://gist.github.com/prameshgautam/952f7910cc23540bd11ba5bf4975c18e.js"></script>

methods like should, must are made available via `FlatSpec` class. 
Run this code and see the output for yourself. There’s a lot to like about scalatest.

I hope this post was helpful to you to get started with writing scalatest. 
After this, you can explore advanced topics and official documentation would be a good start for that.

Please leave comments for any queries/suggestions. 
Please like and share if you feel this will be helpful to someone somewhere. I’ll see you in the next one.

Cheers :)

[Wikipedia]: https://en.wikipedia.org/wiki/Unit_testing
[project]: https://github.com/pmgautam/scala-test.git
[sbt]: https://www.scala-sbt.org/
[sbt_docs]: https://www.scala-sbt.org/learn.html

