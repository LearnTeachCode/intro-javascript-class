# 5.1: API group practice challenge

[In our previous class](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-4), we learned the very basics of working with APIs over the web: HTTP, requests vs responses, HTTP request methods (like GET vs POST), headers, data formats, and how to view request/response data in Chrome's network tab, and how to access APIs via the command line using the `curl` command!

:books: **Prerequisites:**
  - [Review APIs and using cURL from our previous class here](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-4)
  
Let's kick off today's class by building a tiny project together! We'll be combining APIs with other concepts like the DOM and event listeners.

<hr/>

## Planning our app

:hammer: **First, what are we building?** Let's create a very simple app that displays a random dad joke every time the user clicks a button.

**Feature requirements:**

  - There should be a button that the user can click on.
  - And there should be a paragraph to serve as a placeholder for the joke that will appear later.
  - Every time the user clicks that button, make an API call to request a ranomd joke from the Dad Jokes API.
  - When the joke (the API's *reponse*) has finished downloading, display the joke inside our paragraph!    

As with any project, no matter how big or small, we'll begin by making a plan. This means *no coding* and *no computers* needed at all for these first steps!

<br/>

## Challenge 1:

:hourglass_flowing_sand: Get out your pencils and paper! In ***two minutes or less***, draw a quick sketch of the user interface for this application. Keep it simple. (It is a ridiculously simple game, after all!)

<br/>

## Challenge 2:

Let's make a list of all the ***DOM elements*** (parts of the web page) that will need to be accessed by our JavaScript code. 

  > In other words, which parts of the web page will be *changed*? Which will the user *interact* with?

<br/>

## Challenge 3:

How many ***events*** will we need to use in our program?

  > Remember, an *event* is any action that's *outside of our control* as developers; we don't know when (or if) the event will happen. But our code will need to *react* to these events.


<br/>

## Challenge 4:

:hourglass_flowing_sand: In two minutes or less, sketch a quick flowchart from the ***user's perspective***, outlining how the user would use this app step by step.

<br/>

## Challenge 5:

:hourglass_flowing_sand: Spend a couple minutes sketching *another* flowchart, this time from the ***computer's perspective***. Show what our code needs to do step by step. (This will be more detailed than how the user perceives our app.)

<br/>

## (Group) Challenge 6:

All together now, let's write the first parts of our code! We'll leave **placeholders** for the parts that we don't remember how to accomplish just yet.

:star: **[Click this link to collaborate on our shared Glitch project!](https://glitch.com/edit/#!/join/d41c9162-9467-47ea-839d-80d5e994cfdf)**

<br/>

## Challenge 7:

OK, the first parts of our app are completed, and we've confirmed that our code works so far. Onto the next feature!

**First step:** Review the [**Dad Jokes API documentation**](https://icanhazdadjoke.com/api) and test it one more time via the command line (using the `curl` command) to make sure it still works.

  > With APIs, you can't make any assumptions! If it worked yesterday, it might not still work today. Testing APIs with `curl` is great for debugging, because it's entirely separate from your JavaScript code -- like a little quarantine zone.
  
  :books: **Review:** 

<br/>

## Challenge 8:

**Second step:** How can you specify that you'd like to request a dad joke in ***plain text*** format? In JSON format? In HTML format?

**Hints:**
  1. You'll need to use a new ***flag*** with your cURL command to specify a ***request header***. (In our last class, we've used the `-v` flag. This time you'll need a different letter -- find it in the [Dad Jokes API documentation](https://icanhazdadjoke.com/api)!
  
  2. You need to include a ***key-value pair*** for this request header, and you'll find an example of that in the [documentation](https://icanhazdadjoke.com/api) as well.
  

<br/>

## Challenge 9:

Using the same example code from last week's API practice in [section 4.5](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-5-api-challenges-1.md), open a new tab in your browser and run the following JavaScript code directly in the console:

```javascript
var requestObject = new XMLHttpRequest();
requestObject.addEventListener("load", handleResponse);
requestObject.open("GET", "https://icanhazdadjoke.com/");
requestObject.send();

function handleResponse () {
  console.log(requestObject.responseText);
}
```

Did it work? What did the server send you as its response?

<br/>

## Challenge 10:

Before we can integrate the code above into our project, we need to change it so that the Dad Jokes API will send us its response in ***plain text*** format, not in HTML format!

Remember when we sent a request using `curl`, we could specify a request header to tell their server which data format we want to receive: "text/plain", "application/json", or "text/html". Now let's do the same thing but with JavaScript code!

<br/>

:trophy: **Google search challenge:** See if you can find ***how to set a request header*** using JavaScript code.

  1. What's the name of the built-in JavaScript function that let's us specify a request header?
  2. How many parameters does this function take?
  3. What is the first parameter?
  4. What's the second parameter?
  5. How do these two parameters match up to what we typed when we were using `curl`?

<br/>

## Challenge 11:

Great work! Now that we've discovered the missing piece to our API puzzle, let's integrate this new code into our project!

:star: **[Return back here to our shared Glitch project!](https://glitch.com/edit/#!/join/d41c9162-9467-47ea-839d-80d5e994cfdf)**

**Our next steps:**

  1. First, let's just copy-paste our working code anywhere in our JavaScript file, then open the live app, and check the console to see if the code still works.
  
  2. Next, instead of showing the random joke in the console, let's show it to the user! The joke should be displayed in our placeholder paragraph.
  
  3. Finally, let's just *move* this section of our code so that it *only* runs *after* the user clicks the button.

And that's it!

<br/>

## Bonus challenge set 1:

:star: First, remix our Glitch project so you can work on your own personal copy!

  1. Make one tiny change to the code so that the API call requests the data in JSON format instead of plain text.
  
  2. What shows up on the page? Why does it look that way?
  
  3. Fix it so that the actual data appears on the page, using of one of JavaScript's built-in JSON functions.
  
  4. Make one more small change so that only the joke's ID is displayed on the page (none of the other info).
  
  5. Create another paragraph on the page, and then display the joke's ID inside *one* paragraph, and the joke itself inside *another* paragraph!
  
  <br/>

## Bonus challenge set 2:

  1. (If you haven't already, be sure that you've remixed our Glitch project to work on your own personal copy.)
  
  2. Create a Firebase app and link it to your project.
  
  3. Add some code so that after each random dad joke is downloaded, **insert** *the joke and its ID* into Firebase! (So every time the user clicks the button, your Firebase database will have a longer and longer list of jokes where each entry in the database will follow this format: `R7UfaahVfFd: "What do you call a fly without wings? A walk."`)
  
  4. Somewhere at the very bottom of your file (outside of any other functions), set up a Firebase event listener to **display** the entire list of all previous jokes onto the web page!

<br/>
<hr/>

:trophy: **Great work!** We built our first application that makes use of a third-party web API!

:point_right: **Next up:** [in section 5.2, we'll work with NASA's API to build another small app together and learn about query parameters, rate limits and API keys](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-5/5-2-nasa-api.md)!
