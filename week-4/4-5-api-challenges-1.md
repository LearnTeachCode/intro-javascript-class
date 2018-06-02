# 4.5: API practice challenges (Part 1)

In the [previous section](https://github.com/LearningNerd/intro-apis-workshop/blob/master/curl-intro.md), we used **cURL** to request a website straight from the command line, and saw that it does basically the same thing as going to a website in our web browser -- except it shows the response body as ***code***, rather than rendering it visually the way we're used to looking at websites.

Next, let's practice making requests an API to see how the process works!

<hr/>

## Challenge 1:

Somebody made a [**Dad Jokes API**](https://icanhazdadjoke.com/api) just for laughs. It's not a very *useful* API, but it's a nice simple example of how APIs work -- plus, some of the jokes are actually sort of funny! :laughing:

<br/>

**Your challenge:** Look through the Dad Jokes API documentation at https://icanhazdadjoke.com/api and then figure out how to use cURL to get a random dad joke.

<br/>

  > When learning how to work with any API, *most* of your time will be spent just reading their documentation! If you work in software development, you'll often spend more time *reading* than you do writing code.

<br/>

## Challenge 2:

As we learned about in previous classes, there are several different **data formats** used in the software world: [**XML**](https://en.wikipedia.org/wiki/XML) used to be the common standard, but in recent years [**JSON**](https://en.wikipedia.org/wiki/JSON) has become more popular.

  > You can think of these data formats like different file types (`.doc` for Microsoft Word files, `.jpg` or `.png` for images, `.html` for web pages, etc.)

<br/>

**Your challenge:** Get another random dad joke, but this time get the joke in **JSON format** instead of plain text. Look at their documentation to find out how to do this!

:bulb: ***Hint:** You'll need to use a new flag with your cURL command to request which data type you want. (So far we've tried the `-v` flag. Time to try a new one, which you'll see in the Dad Jokes API documentation.*

<br/>

## Challenge 3: 

As a quick preview of the most bare-bones way to make API requests within your JavaScript code, try copy-pasting the example code below and run it directly in your browser console:

```javascript
var requestObject = new XMLHttpRequest();
requestObject.addEventListener("load", handleResponse);
requestObject.open("GET", "https://icanhazdadjoke.com/");
requestObject.send();

function handleResponse () {
  console.log(requestObject.responseText);
}
```

**Discuss:**

  1. What appeared in the console, and where did it come from?
  2. Which HTTP request method did we use in that JavaScript code?
  3. In which data format did you receive the response?
  
<br/>

## Bonus challenge 1:

Use your web browser to access the same URL as before to get a random dad joke, and look in Chrome's network panel to inspect the request named `icanhazdadjoke.com`.

  > **Remember:** you need to open the developer tools and go to the Network panel, and then **refresh the web page** to record the request/response data.

<br/>

**Your challenge:**

  - Comparing the response shown in the web browser to the response shown in cURL for the exact same URL, ***what's different*** between cURL and the browser?
  
  - Can you identify the ***response headers***, both in Chrome's network tab and in cURL? Are there any big differences between them? 
  
  - Why is it that the web browser recieves HTML as a response, but the command line (using cURL) receives a small bit of plain text? How does the Dad Jokes server know whether you're using a web browser or not?

<br/>


## Bonus challenge 2:

First: make sure you've solved the previous challenge and identified the part of the response header that tells the Dad Jokes server about what type of the client you're sending the request from.

<br/>

**Your next challenge:** Trick the Dad Jokes server into thinking that your that command line is actually the Mozilla Firefox web browser! To do this, you can use the value `Mozilla/5.0` -- you'll need to send it in your request header user cURL!

<br/>

...so, what happened? Did you fool them? ;)

<br/>
<hr/>

:point_right: **Next up:** [for homework, in section 4.6 you'll follow some suggested steps to start integrating a Firebase database into your personal project](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-6-project-homework-firebase.md)!
