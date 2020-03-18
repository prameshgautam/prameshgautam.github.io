---
layout: post
title:  "Integrating Play Framework and ReactJs"
date:   2018-05-25
categories: Play Framework
permalink: /2018/05/25/integrating-play-framework-and-reactjs/
author: Pramesh
---


Hi guys,

Welcome to my first post on Play Framework and React. I was trying to set up a project using Play Framework for backend and React for the frontend. After days of research and trying various options from various blogs, I settled on an approach which I liked and would like to share with you. For this post, I hope you’re familiar with Scala/Play Framework and ReactJS.

[Play Framework][Play] is a web framework that can be used with Scala and Java and [React][React] is a Javascript framework for building user interfaces. I’ll be using Scala for this post. You can learn more about Scala and React in their official documentation.

You can find the code on [GitHub][code]. I’ll be providing an abstract explanation in this post. Please check the code to see the implementation part.

## Overview
The approach I’ve used uses JSON API to communicate between backend and frontend.  I’ve created an sbt project for the backend. This will create a basic play-framework project with a controller, a route, and a template. This becomes the backend of our project excluding the template. We won’t be using this template and will react for the frontend. For the frontend, I’ve created an NPM project in ui folder with package.json and webpack.config.js. Once front and back servers start, we’ll fetch the JSON APIs provided by the back server and use them to display on the front server.

## Creating Sbt Project
This is the backend of this project. Use the following command to create a project skeleton.

`sbt new playframework/play-scala-seed.g8`

This will create a Controller and view. Next, we’ll add some JSON APIs that will be returned by the controller and will be used by frontend to communicate with the project. For this demonstration, I’ve created two models: Student and Subject. They’ll be parsed with the help of JSON library provided by Play Framework and will be served on the browser from the routes defined in routes file.

{%highlight scala%}
GET        /students     controllers.StudentController.studentsIndex
GET        /subjects     controllers.StudentController.subjectsIndex
{%endhighlight%}

Once the models have been set up and they are implemented to return JSON, start the server with the command sbt run and visit <http://localhost:9000/students> or <http://localhost:9000/subjects>. They’ll return the JSON format for our models.

## Creating React Project
It’ll be an NPM project. Create a folder named **ui** and do **npm init** to initialize it to NPM project. **package.json** and **webpack.config.js** are configured. Please see [GitHub][code]. In NPM project do npm run build to start the front server. build script has been set up in package.json as

{% highlight javascript %}
“scripts”: {
“test”: “echo \”Error: no test specified\” && exit 1″,
“build”: “webpack-dev-server”
}
{% endhighlight %}

It will run the webpack-dev-server and start the react project on <http://localhost:8080>. For the front end code that fetches the JSON API and displays the data on the browser, please visit the code.

## How do they Communicate?
So far, we’ve created the backend part of the project with Play Framework that returns the JSON format for students and subjects and in the front part, we’ve created the react project that parses the JSON data to display to the user. Please see [GitHub][code] for implementation part. With all these setups, we need one more thing to change on the back server. We need to add configuration it to allow something called Cross-Origin Resource Sharing(CORS). **CORS** has been explained [here][cors]. It allows the requests from other domain to extract the data. Since we’re trying to fetch data in <http://localhost:8000> from <http://localhost:8080>, we need to change config the support this. For that, add these lines to your backend project’s application.conf file.


{% highlight scala %}
play.filters.enabled += "play.filters.cors.CORSFilter"
play.filters.cors {
allowedOrigins = [“http://localhost:8080”%5D
allowedHttpMethods = [“GET”, “POST”]
allowedHttpHeaders = [“Accept”]
preflightMaxAge = 3 days
}
{% endhighlight %}

This config allows our frontend server <http://localhost:8080> to fetch the data from the backend server.

With this much code, you’ll be able to display the data in the browser. React will handle all the front end stuff from data fetching and parsing while Play Framework gladly serves the data in the form of JSON. I hope the approach I’ve used is clear to you. However, it’s my first try at integrating Play Framework and ReactJS. There’re various things that can be improved, eg: adding designs, reverse proxy and the front code can be made a bit better I hope.

Please comment if you’ve any queries/feedback. I’ll be happy to respond. I’ll see you in the next one. Cheers 🙂


[Play]: https://www.playframework.com/
[React]: https://reactjs.org/
[code]: https://github.com/pmgautam/play-react-integration
[cors]: https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS

