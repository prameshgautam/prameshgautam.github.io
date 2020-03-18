---
layout: post
title:  "Cascading 1: Intro + Creating a Flow"
date:   2016-10-23
categories: Play Framework
permalink: /2016/10/23/cascading-1-intro-creating-a-flow/
comments:true
author: Pramesh
---


Hey folks,

Welcome to Cascading Tutorial. This is the first one. In this tutorial we are going to look at a simple example which will be a kind of intro to Cascading. We will define some terms and see an example of Cascading Flow.

If you want to know about Cascading in detail, then please go to this [link][cascading_link]. Basically, Cascading is a Java based data manipulation API. It is quite powerful and you can perform a ton of tasks in it. In this tutorial we will learn how to build a simple Cascading flow. Like I said, it is a kind of intro to Cascading. In Cascading, data is manipulated in the form of a flow. You can think of it being analogous to water flow. Data needs to be read from a source and can be written to files or databases.

Cascading can also be called as an abstraction over Hadoop MapReduce. As it is complex to code in MapReduce, we can use Cascading for data operations. It will then be converted to MapReduce jobs when running over Hadoop.

The sources of data are called [Taps][taps_link]. Data input is taken from source Tap and data is written to sink Tap. Taps are the only source of data in Cascading. In other words, Taps are needed to read data and write it after applying operations data. Again, you can think of source Tap and sink Tap like in water flow.

Once data is brought to Taps, it needs to flow through them. Data flows through a medium called [Pipe][pipe_link]. It is similar to Pipes that carry water in water flow. Data operations can be applied once the data starts flowing through Pipe. We need to bind Pipes to both source and sink Taps. And these Pipes carry data in them. Required operations such as function, filter and buffer are applied when the data is going through Pipe.

Third major thing we need is [Scheme][scheme_link]. Scheme defines the  characteristics of data that is to be read and written. Things like data delimiters, header information and file location are defined from Scheme. Custom Schemes can be created to meet our data requirements. Again, Scheme is needed for both source and sink Tap. We can define what kind of data is to be read from what location and how it should be written  in source and sink taps respectively with their Schemes.

Another important term to understand is [Fields][fields_link]. Fields are the name given to columns of data. They are same as the column name used in SQL. We can use Fields to know the column of data we need to work. We need to define the source Fields and sink Fields in our flow. Fields Layout should match the data layout in files.

Please keep in mind that Tap, Pipe, Scheme and Fields are all Java classes. Once we define these things properly and feed data into these, we can run our code in both local and Hadoop environment.

Lets start with the code. You can find the text file we will use over [here][github_link].

File generated from [mockaroo][mockaroo].

Implementation part: `CascadingIntro.java`

<script src="https://gist.github.com/prameshgautam/950f450307f000be5305cf37041fc2e9.js"></script>

Here is the code description:

* In four class variables we have defined the source and sink delimiters and source and sink file locations. (lines 17-21)
* Then in main function we define the Fields. In this example, since we are not changing the data layout, source and sink Fields will be same. (line 25)
* Then we define source Taps and sink Taps. Like defined above, they determine what kind of data is to be read from what location. SinkMode.REPLACE is used to replace the file if it exists at given location. (lines 28-29)
* TextDelimited is the Scheme used in this example. We need to pass different data information in this Scheme about the data we are using. In this case we have comma(,) as delimiter and since we have header, we have set hasHeader to true.
* Then we define the Pipe to use. Data flows through this Pipe. Debug function is used to display the data flowing through Pipe.
* In lines 35 and onward, we have defined the flow, added source and sinks and completed it.



If we run this code then, same data is written to folder **cascading_intro_file_sink.csv** with file name like **part-00000**. 

There won’t be header and delimiter will be Pipe(\|) because these are the values we have passed onto the sink Taps’ scheme at line 29. 

In this example nothing much happens. Simply data flows from one location and gets written to another with same data. This is how a Cascading flow runs.

We will have some more tutorials with examples and some operations. Till then.. cheers 🙂

[cascading_link]: http://www.cascading.org/
[taps_link]: http://docs.cascading.org/cascading/1.2/userguide/html/ch03s03.html
[pipe_link]: http://docs.cascading.org/cascading/1.2/javadoc/cascading/pipe/Pipe.html
[scheme_link]: http://docs.cascading.org/cascading/2.0/javadoc/cascading/scheme/Scheme.html
[fields_link]: http://docs.cascading.org/cascading/1.2/javadoc/cascading/tuple/Fields.html
[github_link]: https://www.dropbox.com/s/rnk0c6j4vl05pe8/cascading_intro_file.csv?dl=0
[mockaroo]: [https://www.mockaroo.com/]

