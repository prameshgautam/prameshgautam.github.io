---
layout: post
title:  "Upload files to S3 using ReactJS and Play Framework"
date:   2018-11-27
categories: Play Framework
permalink: /2018/11/27/upload-files-to-s3-using-reactjs-and-play-framework/
author: Pramesh
---


Welcome to my new post. In this article I am going to write about uploading files to s3 using ReactJS as front end and Play framework as back end. Let’s start.

If you want to learn about how to integrate ReactJs and Play framework using REST apis, please visit here. Creating new project in play and react is also explained in that article.

## Introduction:
This article will use ReactJS in front end to select files and send request to back end. Play framework will read that request and upload files to s3. I’ve used digitalocean spaces for this article. But it is same for S3 as well. I’ve run this test using image and front-end is also written for image. There might be some changes for different file type.

Grab code [here][code_url]

## Project folders:
* s3-back: contains scala/play code
* s3-ui: contains reactjs code

### Dependencies needed:

* Set your access credentials in s3Props.conf
*  Guice binding is done in S3Module.scala -> this is used to inject s3Props implementation
* Add this to your build.sbt(adds aws sdk as dependency)
`libraryDependencies += “com.amazonaws” % “aws-java-sdk-s3” % “1.11.451”`

### How to run:

Go to sbt console from **s3-back** folder and excute run command. This starts back server in port 9000
From  s3-ui folder, execute **npm run start**. This starts front server in port 3000.
In back project, **HomeController.scala** contains necessary code and dependencies are injected to that controller. Json response is provided based on status.

 

In front code, **FileUpload.js** contains necessary code and response to display on the basis of file upload.

 

This much for this article. Please see the code and drop a comment for any suggestion/question. See you in the next one.


[code_url]: https://github.com/prameshgautam/s3-upload-play-react