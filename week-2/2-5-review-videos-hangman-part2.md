# 2.5: Review and finishing version 0 of the Hangman game

In [the first set of review videos for building our Hangman game (section 1.5)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md), we learned about flowcharts, linking JS files to HTML files, variables, the DOM, and conditional statements! In this second part of our review, we'll finish building version 0 of our game -- but with a cliffhanger bug! (Your homework is to take a stab at finding the bug, [following section 2.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-4-debugging-challenge.md))

:books: If you haven't already, remember to bookmark [this link to all our class materials](https://github.com/LearnTeachCode/intro-javascript-class/tree/march-2018)!

❓ **Remember to ask questions on our Slack channel** and discuss your ideas with us there! (See our [quick intro to Slack](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#111-intro-to-slack) if you need a refresher.)

**Table of Contents:** 
  - [2.5.1: Intro to events and event listeners](#251-intro-to-events-and-event-listeners)
  - [2.5.2: Operators: Increment, decrement, and concatenate](#252-operators-increment-decrement-and-concatenate)  
  - [2.5.3: Putting it all together: Hangman and the cliffhanger bug](#253-putting-it-all-together-hangman-and-the-cliffhanger-bug)

<hr/>

## 2.5.1: Intro to events and event listeners

Events and event listeners allow you to respond to user input (among many other types of events), telling a section of your code to *wait* and only execute when triggered by an event. 

:tv: **Video: Intro to events and event listeners (19 min): https://youtu.be/UbwCNBCUrhQ**

Web browsers provide a built-in JavaScript function named `addEventListener`, which is available on any JavaScript object that represents a DOM element (see [section 1.5.4 for a video review of the DOM](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md#154-the-dom-interacting-with-html-and-css-using-javascript)).

**Example code for responding to a click on a button:**

```javascript
let submitButtonElem = document.getElementById("submit");

submitButtonElem.addEventListener("click", logClick);

function logClick () {
  console.log("User clicked the button!");
}
```

Every time you use an event listener, there are **three main questions** you'll need to answer:

  - **Where is the event happening?** On the `submitButtonElem` (the object representing a button on the web page)
  - **Which event are we listening for?** The `"click"` event (see the [list of all built-in events on MDN](https://developer.mozilla.org/en-US/docs/Web/Events))
  - **What should happen when the event occurs?** Run the `logClick` function

**Bonus resources:**
  - [Event listeners reference page on MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
  - [List of all built-in web browser events on MDN](https://developer.mozilla.org/en-US/docs/Web/Events)

<br/>

## 2.5.2: Operators: Increment, decrement, and concatenate

Below is a video review of arithmetic operators, concatenation (combining strings), and how to count up or down using a variable in JavaScript, which we'll need in order track the number of guesses remaining in our Hangman game!

:tv: **Video: Operators: Increment, decrement, and concatenate (9 min): https://youtu.be/0kwAn7YuTwQ**

**Extra resources:**
  - [MDN reference page on arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)
  - [Increment and decrement reference page on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment_())
  - [String operators and concatenation reference on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#String_operators)

<br/>

## 1.2.8: Putting it all together: Hangman and the cliffhanger bug

Now that we've taken a look at all the programming concepts that make our Hangman game possible, let's finally combine everything and build the game! (But there will be one tricky bug in the game, for you to the bug as homework in [section 2.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-4-debugging-challenge.md).)

:tv: **Video: Putting it all together: Hangman and the cliffhanger bug (13 min): https://youtu.be/OmTq8hkFov0**

Phew! Isn't it amazing how such a simple (and unfinished) game still requires so many moving parts? But it does get easier with practice -- pretty soon you'll be making games like this in just an hour or two!

<br/>

<hr/>

:point_right: **Don't forget to do the homework!** Try solving our cliffhanger bug [following the instructions in section 2.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-4-debugging-challenge.md). (And remember, the goal *is not* to actually find the solution; the goal is just to practice *being strategic* in your debugging process and make it habit!)
