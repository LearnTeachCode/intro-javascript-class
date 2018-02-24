# 1.2: Programming concepts review and the Hangman game

❓ **If you have any questions**, please ask on the private Slack channel for our class. (See our [quick intro to Slack](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#111-intro-to-slack) if you need a refresher.)

:clock2: **Time to complete: about 2 hours**, or more if you dive deeper into the topics and do your own research, which I always recommend!

:books: **Prerequisites:**
  -  First review [Section 1.1: Getting started with our first software tools](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-1-initial-tools-intro.md).
  - **Two *new* videos** have been added to section 1.1: [Intro to Chrome's developer tools and the browser console](https://youtu.be/O_sJE_3jKZ4) (4 min), and [Creating websites locally with VS Code](https://youtu.be/E4FmXNatxt0) (5 min).

**Table of Contents:**  
  - [1.2.1: Flowcharting our Hangman game](#121-flowcharting-our-hangman-game)
  - [1.2.2: Linking JavaScript to HTML](#122-linking-javascript-to-html)
  - [1.2.3: Creating and changing variables](#123-creating-and-changing-variables)
  - [1.2.4: The DOM: Interacting with HTML and CSS using JavaScript](#124-the-dom-interacting-with-html-and-css-using-javascript)
  - [1.2.5: Intro to events and event listeners](#125-intro-to-events-and-event-listeners)
  - [1.2.6: Operators: Increment, decrement, and concatenate](#126-operators-increment-decrement-and-concatenate)
  - [1.2.7: Conditional statements and comparison operators](#127-conditional-statements-and-comparison-operators)
  - [1.2.8: Putting it all together: Hangman and the cliffhanger bug](#128-putting-it-all-together-hangman-and-the-cliffhanger-bug)

<hr/>


## 1.2.1: Flowcharting our Hangman game

:star: ***First, be sure to try out the finished Hangman game here:*** https://hangman-v0-final.glitch.me (Just promise not to look at the finished JavaScript code until you've done the homework -- no cheating!)

:tv: **Video: Intro and flowcharts for our Hangman game (9 min): https://youtu.be/28r3b6E__Rs**

**Flowcharting resources:**
  - ["How to Avoid Overcomplicating your Flowchart"](https://cacoo.com/blog/keep-it-simple-how-to-avoid-overcomplicating-your-flowcharts/): A quick overview with advice on effective flowcharting, a look at common flowchart symbols, and example images.
  - ["What is a Flowchart"](https://www.lucidchart.com/pages/what-is-a-flowchart-tutorial): a pretty detailed overview, including the history of flowcharts, common flowchart symbols, and other background info.


## 1.2.2: Linking JavaScript to HTML

How do you get these different languages -- HTML, CSS, and JavaScript -- to talk to each other? This is a quick overview of how to set it up and a couple potential problems to look out for.

:tv: **Video: Linking JavaScript to HTML (10 min): https://youtu.be/zn8JNXOBg7U**
  
**Extra resources:**
  - [HTML `script` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
  - [HTML `defer` attribute](https://www.w3schools.com/tags/att_script_defer.asp)
  - [HTML `head` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)


## 1.2.3: Creating and changing variables

A first look at how to create new variables, change values of existing variables, and how JavaScript reads your code in two separate stages.

:tv: **Video: Creating and changing variables (8 min): https://youtu.be/a0GTqrB2k9c**

**Extra resources:**
  - [The `let` statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
  - [MDN's page about "hoisting"](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)
  - ["Hoisting" on W3Schools](https://www.w3schools.com/js/js_hoisting.asp)


## 1.2.4: The DOM: Interacting with HTML and CSS using JavaScript

:tv: **Video: The DOM: Interacting with HTML and CSS using JavaScript (34 min): https://youtu.be/ZUcTcNyGMlo**

**Extra resources:**
  - [Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
  - [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
  - [Document object](https://developer.mozilla.org/en-US/docs/Web/API/document)
  - [textContent Property](https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent)
  - [HTML attribute reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes)
  - [HTML element style property](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style)
  
## 1.2.5: Intro to events and event listeners

:tv: **Video: Intro to events and event listeners (19 min): https://youtu.be/UbwCNBCUrhQ**

Events and event listeners allow you to respond to user input (among many other types of events), telling a section of your code to *wait* and only execute when triggered by an event. Web browsers provide a built-in JavaScript function named `addEventListener`, which is available on any JavaScript object that represents a DOM element (see section 1.2.4 above for more on the DOM).

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


Optionally, your function can also receive an input from the event listener, which contains information about the event that just occurred! For example, the `event` parameter in the code below will be replaced by a MouseEvent object containing lots of information about your mouse clicks:

```javascript
window.addEventListener("click", logMouseEvent);

function logMouseEvent (event) {
  console.log(event);
}
```

Try running the code above (you can test it directly in your browser console if you like). Click somewhere on the web page, and then look inside the console. You should see a MouseEvent object show up in your console every time you click the page, and you can expand that object to look inside it:
![console-expand-object](https://user-images.githubusercontent.com/1555022/26953972-67a12a30-4c62-11e7-8bb0-bb786e433bd1.gif)


**Extra resources:**
  - [Event listeners](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
  - [List of all built-in events on MDN](https://developer.mozilla.org/en-US/docs/Web/Events)

## 1.2.6: Operators: Increment, decrement, and concatenate

Here's our first look at arithmetic operators and concatenation in JavaScript, which we'll need in order to count down the number of guesses in our game.

:tv: **Video: Operators: Increment, decrement, and concatenate (9 min): https://youtu.be/0kwAn7YuTwQ**

**Extra resources:**
  - [MDN reference page on arithmetic operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)
  - [Increment and decrement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Increment_())
  - [String operators and concatenation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#String_operators)

## 1.2.7: Conditional statements and comparison operators

:tv: **Video: Conditional statements and comparison operators (27 min): https://youtu.be/Sf7ZMqjXWHw**

**Extra resources:**
  - [MDN reference page on `if...else`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
  - [Comparison operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)


## 1.2.8: Putting it all together: Hangman and the cliffhanger bug

:tv: **Video: Putting it all together: Hangman and the cliffhanger bug (13 min): https://youtu.be/OmTq8hkFov0**

<br/> :point_right: **Don't forget to do the homework next!** All class materials, homework, cheat sheets, etc are [in this folder on GitHub organized by week](https://github.com/LearnTeachCode/intro-javascript-class).
