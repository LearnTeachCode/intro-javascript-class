# Section 5.1: Intro to APIs: Our first look at HTTP

You've certainly heard the term ***API*** thrown around a lot -- not just among techies, but also in the news and sometimes even in casual conversation! So what's this all about? ***API*** stands for ***Application Programming Interface***.

We'll be learning more about how APIs work and how to use them in our next few classes. Our very first step will be to look at the underlying protocol (set of rules) that allows our programs to send and receive information over the internet.

<hr/>

<br/>

## What does it mean to access an API over the web?

:star: ***Accessing an API over the internet is essentially just visiting a website!***

There are only a couple differences:

  - Instead of typing a URL into your web browser to access a website, you'd usually access an API from *within your code* (like inside your JavaScript file) or via the *command line* directly.
  
  - Compared to visiting a website as a *user*, accessing an API as a *developer* does require you to read some documentation beforehand to learn each API's unique rules and conventions.
  
  - Developers need to decide on and sent *much more* information than just which URL to access, as you'll see very soon!

<br/>

## HTTP and the request-response model

:star: **HTTP** stands for [***HyperText Transfer Protocol***](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol), and it's the set of rules that allow computers to communicate with each other over the internet -- it's the backbone of the World Wide Web!

<br/>

  > **Fun fact:** HTTP was initially created by [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee), inventor of the World Wide Web, in 1989 at CERN.

  > **Bonus fun fact:** CERN is the home of the [Large Hadron Collider](https://home.cern/topics/large-hadron-collider), the largest single machine in the world, which smashes atoms and even smaller particles together at crazy high speeds in the name of science!

<br/>

Since HTTP is already so widely adopted (used by practically every computer in the world!), it's very convenient for programmers to build on top of it! That's why so many APIs are based on HTTP.

<br/>

**HTTP follows what we call the *request-response* model of communication:**

  1. Any time your computer (the ***client***) visits a website, it makes a ***request*** via HTTP, which the web browser sends over the internet to a ***server***.
  
  2. Then the server (which is just another computer) receives that request and runs some code to decide what it should send back to the client.
  
  3. Finally, it sends a ***response*** back to the client.

<br/>

The ***request-response model*** is just like communicating via snail mail or telegram:

![HTTP request response model](https://raw.githubusercontent.com/LearnTeachCode/learnteachcode.github.io/master/socketio-workshop/slides/images/request-response.gif)

Very simple, isn't it? It's an old-fashioned idea, but it works because our computers and internet connections are fast enough that browsing the web feels *nothing* like communicating via telegram. :)

<br/>

## Challenge 1:

**Discuss:**

  1. What information do you think is part of your computer's ***request*** when you log into Facebook (or another social network)?
  
  2. What do you think is included in the ***response*** that the server sends back to your computer?
  
  3. In our projects that we've all been creating in Glitch, how many HTTP requests and responses do you think need to happen for a user to access our web apps?

<br/>

## Four most common HTTP request methods (or HTTP verbs)

| HTTP request method (or "verb") | The action it corresponds to |
| --- | --- |
| GET | Request some data (ex: to view any web page, or to search for something on Google) |
| POST | Submit data to the server, usually to create something new (ex: create a new project on Glitch or GitHub) |
| PUT | Replace existing data with new data (ex: update your relationship status on Facebook) |
| DELETE | Remove a piece of data entirely (ex: delete an embarrassing video that you had uploaded to YouTube) |

The **GET** and **POST** request methods are the most common by far.

<br/>

Most of the time when you're browsing the web, your web browser is just sending a bunch of **GET** requests. When you submit a form (especially with any private information like a password, bank account info, etc), that's usually sent as a POST request.

<br/>

:books: **Extra resources:**
  - See GitHub's API documentation on how they use the HTTP verbs (they use some special ones in addition to the main four): https://developer.github.com/v3/#http-verbs 
  
  - You can also explore the HTTP verbs in more depth here: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods

<br/>

## Challenge 2:

**Discuss:**

  1. When you go to a website like https://example.com by typing that URL into your web browser, which type of HTTP request method is your web browser sending to that website's server?
  
  2. If you publish a new post on Facebook, which HTTP request method do you think is sent to Facebook's servers?

  3. When your web browser sends that request to Facebook, what pieces of information do you think need to be sent (aside from Facebook's URL)?

<br/>


<hr/>

:point_right: **Next up:** [in section 5.2, we'll learn the basics of Chrome's network tab to see what happens behind the scenes every time you visit a website (which is basically the same as making an API call)](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-5/5-2-network-tab.md)!
