# 3.2: Review: Event listeners

:weight_lifting_man: Let's warm up those coding muscles with a quick review of how we've been using event listeners so far!

Remember that event listeners allow you to respond to all sorts of events (for example, the user clicking something on the web page). When you set up an event listener, you're basically telling a section of your code to *wait* until an event happens!

:tv: **Video: Intro to events and event listeners (19 min): https://youtu.be/UbwCNBCUrhQ**

Web browsers provide a built-in JavaScript function named `addEventListener`, which is available on any JavaScript object that represents an element of the web page (also called DOM elements).

:books: **Review materials:**

  - Video review of function basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU
  - [Beginner class section 2.3: intro to functions](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-3-function-intro-challenges.md)
  - [Beginner class section 4.2: functions with inputs](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-4/4-2-function-input-challenges.md)
  - [Beginner class section 4.3: scope, function outputs, and the `return` statement](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-4/4-3-scope-and-function-output-challenges.md)
  

<br/>

<hr/>

## Overview of events and event listeners

Every time you use an event listener, there are **three main questions** you'll need to answer:

  1. **Where is the event happening?** (Which part of the web page?)
  2. **Which event are we listening for?** (See the [list of all built-in events on MDN](https://developer.mozilla.org/en-US/docs/Web/Events) for examples!)
  3. **What should happen when the event occurs?** (Remember, these actions must be wrapped inside a function!)

<br/>

## Challenge 1:

Take a look at the example below, and then answer those three questions to describe this code:

```javascript
let submitButtonElem = document.getElementById("submit");

submitButtonElem.addEventListener("click", logClick);

function logClick() {
  console.log("User clicked the button!");
}
```

**Discuss:**

  1. Where is the event happening? (Which part of the web page?)
  2. Which event are we listening for?
  3. What should happen when the event occurs?

<br/>

## Challenge 2:

Here's another bit of code! Again, take a look and answer those three questions to describe what this does:

```javascript
document.addEventListener("keypress", logEvent);

function logEvent() {
  console.log("An event just happened!");
}
```

**Discuss:**

  1. Where is the event happening? (Which part of the web page?)
  2. Which event are we listening for?
  3. What should happen when the event occurs?

**Bonus:** Test out the code above and see what it does! Look up the event on a reference website -- I think MDN (Mozilla Developer Network) is the best reference site for this.

<br/>

## Getting more information about the event

The code below is *very similar* to our previous examples, but notice one importance difference: the function that's triggered by the event now has an **input**! 

```javascript
document.body.addEventListener("click", logMouseEvent);

function logMouseEvent(event) {
  console.log(event);
}
```

Try running this code directly in your browser console on *any* web page. (Be sure to also click somewhere on the page to trigger the event!) Then take a look at what appears in the console -- a MouseEvent object!

![console-expand-object](https://user-images.githubusercontent.com/1555022/26953972-67a12a30-4c62-11e7-8bb0-bb786e433bd1.gif)

If you expand the object inside your browser's console, you can see it contains a long list of information about the event that just occurred.

**Important note:** Remember that inside a function definition, the *parameter* is just a *placeholder* for whatever data will be there in the future. It doesn't matter what we name that parameter!

```javascript
// We can name the parameter "event":
function logMouseEvent(event) {
  console.log(event);
}

// ....or "bananas" or anything else! It's just a placeholder:
function logMouseEvent(bananas) {
  console.log(bananas);
}

// A common convention you may seen in other people's code is to name it "e":
function logMouseEvent(e) {
  console.log(e);
}
```

:books: For a review of functions, take a look at the suggested links at the very top of this page.

<br/>

## Challenge 3:

Take the code below (which is the same example from challenge #2), and modify it slightly so that instead of displaying `"An event just happened!"` in the console, it should instead display ***the event object*** inside the console!

```javascript
document.addEventListener("keypress", logEvent);

function logEvent() {
  console.log("An event just happened!");
}
```

What kind of object does this event provide to your function? (Be sure to test your code! You can run it directly in the browser console on *any* web page.)

<br/>

## Challenge 4:

Using your browser's console, take a look at the *key-value pairs* inside that event object and identify *which key* was pressed by the user!

What's the name of the *key* or *property* that contains the answer?

<br/>

## Challenge 5:

Remember how to access a property of an object? Here's a quick refresher:

```javascript
let myParrot = {
  name: "Polly",
  color: "red"
};

// This is how you display the entire object:
console.log(myParrot);

// This is how you display the "color" property of the myParrot object:
console.log(myParrot.color);
```

**Your challenge:** Make *one tiny change* to your code from the previous challenge so that instead of displaying the *entire* event object in the console, your function will only display *which key was pressed* in the console.

<br/>

## Group coding challenge:

Let's do one more practice problem together! **Open this Glitch project and then *click the link at the top of the page* to code with us: https://reviewgroup1.glitch.me/**

**Our goal:** whenever the user types a new character into the text input box, the paragraph at the bottom will display which key they pressed!

<br/>

<hr/>

:point_right: **Next up:** [in section 3.2, we'll start using Firebase's `.on()` event listener function to display data from a database](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-2-firebase-event-listener.md)!
