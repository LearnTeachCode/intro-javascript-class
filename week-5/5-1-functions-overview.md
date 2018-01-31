## 5.1: Overview of functions, variable scope, and the return statement

Functions are one of the most fundamental concepts in programming, but full of nuances that can be challenging to wrap your head around! Let's take a look at some examples though. This guide will also serve as a reference for solving our [function practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-2-function-challenges.md).

**Table of Contents:**
  - 5.1.1: ...
  - 5.1.2: .....

<hr/>


## Overview of functions

📺 **Video: Review of Function Basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

### What are functions?

Functions are like the verbs of programming, because they perform actions within a program. Functions are like miniature programs that can be *reused* multiple times.

### Why are functions useful?

Because they keep your code modular and **DRY** (Don't Repeat Yourself, an important principle for programming and tech in general)!

Keeping your code modular helps you organize everything better. Messy code is like a messy desk with papers scattered all over it -- that makes it harder to find things! Messiness also makes it harder to debug your code if anything breaks. So, wrapping up your code in different functions is a bit like organizing your desk and putting things into boxes and separate piles.

### Separation of concerns

["Separation of concerns"](https://en.wikipedia.org/wiki/Separation_of_concerns) refers to the philosophy that each part of your program should do just *one* thing.

One example of separation of concerns is the difference between HTML and CSS! As illustrated by the website [CSS Zen Garden](http://www.csszengarden.com/), separating your website's content/structure (HTML) from its presentation (CSS) saves a lot of time when you need to change the way your website looks.

Just imagine changing the font color on thousands of HTML pages -- yikes! With CSS, you only need to change *one line of code* that controls the font color of *all* the pages on your entire website. Using functions in your JavaScript code helps avoid repetitive code and saves you time in a similar way.


## Defining versus running functions

When it comes to working with *your own* custom functions, you'll be using them in ***two stages:***

  1. **Defining your function** - This is like creating an entry in a dictionary for a word you just invented; this explains what it means. In our case, it specifies what the function will do.
  
  2. **Running your function** - This second step is like using a new word in a sentence after you've looked it up in the dictionary. Running your function involves looking it up in the computer's memory and then executing the lines of code inside the function.

:star: **You only need to define a function once, which then allows you to run it multiple times.** It's a lot like initializing a variable with the `let` keyword -- only do it once! -- and then you can use that variable as many times as you want to afterwards, *without* using `let`.

Hopefully that's a helpful metaphor for understanding the difference between **defining** and **running** functions!

:books: **Important vocabulary note:** There are a few synonyms you'll see that all mean the same thing!

**Other words for running a function:**
  - ***Run*** a function
  - ***Call*** a function
  - ***Execute*** a function
  - ***Use*** a function
  - ***Invoke*** a function

**Other words for defining a function:**
  - ***Define*** a function
  - ***Declare*** a function
  - ***Create*** a function
  - ***Initialize*** a function

Tech jargon is maybe the least fun part of becoming a skilled software developer, but it's a necessary evil. =P Next, let's finally look at some code!


## How to define a function

There are **four parts** to every function definition:

  1. The `function` keyword
  2. The name of the function (follow same naming rules as variables)
  3. Parentheses containing optional inputs (called parameters)
  4. Curly brackets containing the code that it will run (called the function body)

### Example function definitions

The function defined below takes **one input**, then adds exclamation points after it (assuming the input is a string), and finally displays the result in the console:

```javascript
function shout (phrase) {
   console.log(phrase + '!!!');
}
```

This other function has **no inputs** :

```javascript
function sayHello () {
   console.log('Hello!');
}
```

And finally, this function has **three inputs**:

```javascript
function addThreeNumbers (numOne, numTwo, numThree) {
   console.log(numOne + numTwo + numThree);
}
```

:star: **Important note:** There's *more than one way* to define functions in JavaScript! We're just using this one way for now, and it's totally fine if you always define functions this way. (Mostly a matter of personal preference.)


## Running functions

We've already been using (or running, calling, or executing) functions since day 1 of our class! These should look familiar:

```javascript
// Display a message in the console:
console.log("Hi!");

// Translate an HTML element into a JavaScript object and save it to a variable:
let submitElem = document.getElementById("submit");

// Set up an event listener to tell the web browser to run a function when the user clicks this element on the page:
submitElem.addEventListener("click", myFunctionToRun);

// And again, here's us defining our own function to run when that element from above is clicked:
function myFunctionToRun () {
  console.log("The submitElem was just clicked!");
}
```

Looking at the code above, what do `console.log()`, `document.getElementById()`, and `submitElem.addEventListener()` all have in common? Yup, they're all followed by a pair of parentheses! Which brings us to a very important rule to remember about functions:

:star: **To run a function, you type the name of the function followed by parentheses `()`**, with any *inputs* for the function listed inside the parentheses.

### The meaning of parentheses `()` for functions

The pair of parentheses that come after the name of a function is sometimes called the **invocation operator**, because it's what signals to the computer that it's time to run the code inside that function *at that exact moment in time*.

**What's the difference between `myFunction` and `myFunction()`?**

Copy-paste the code below and run it directly inside your browser console to see the difference:

```javascript
// First we define the function:
function myFunction () {
  console.log("Hello from myFunction!");
}

// Here's what happens when you run myFunction():
myFunction();

// And here's what happens if you just type myFunction into the console:
myFunction;
```

So here's the difference:

  - **myFunction()** runs the code inside the function -- remember, the parentheses `()` are what tell the computer "hey, time to run this code right now!"
  
  - **myFunction** *without* the parentheses is just the ***name*** of the function itself, telling the computer to go find that function wherever it's saved in the computer's memory. (Like looking up the definition of a word in a dictionary.)
  
So when we use `addEventListener()` and pass it the name of a function as the second input, we *don't* use parentheses next to our custom function's name; we don't want the function to run at that exact moment! Instead, we want the computer simply to know *which* function to run ***later*** -- for example, when the user clicks a button.

**The code below will NOT work as expected:**
```javascript
// *** NOTICE: here we accidentally use parentheses after myTestFunction in the line below: ***
document.addEventListener("click", myTestFunction());

function myTestFunction () {
  console.log("The page was just clicked!");
}
```

Test it out by copy-pasting it into your web browser and then clicking several times anywhere on the web page. You'll see that the message `"The page was just clicked!"` only appears once -- *immediately* -- and nothing happens when you click the page.

That's because `myTestFunction()` runs *immediately* when the computer sees that pair of parentheses after the name of our function, *not* when the click event happens.

**The code below WILL work as expected:**

```javascript
// *** NOTICE: no parentheses after myTestFunction in the line below: ***
document.addEventListener("click", myTestFunction);

function myTestFunction () {
  console.log("The page was just clicked!");
}
```

Test it out again by copy-pasting it into your web browser, and then clicking some more anywhere on the web page.

Now it works, because the computer is now only telling the event listener *where* to find the function in memory instead of *using* it right away -- basically saying "hey, go find the entry in your dictionary for the function named myTestFunction so you can run it later!" 


## Arguments versus parameters

...


## The return statement

...


## Variable scope

.... Code snippets to maybe use, from before ....

Local variable (this won’t work):
function pointlessFun (x) {
   var localX = 5;
}
console.log(localX);

Adding a global variable:
var globalX = 999;
function pointlessFun (x) {
   var localX = 5;
}
console.log(globalX);

All functions can access global variables:
var globalX = 999;
function pointlessFun (x) {
   var localX = 5;
   console.log(globalX);
}

Which value will appear in the console?:
var nameTest = 999;
function pointlessFun (x) {
   var nameTest = 5;
}
console.log(nameTest);


Importance of the var keyword:
var nameTest = 999;
function pointlessFun (x) {
    nameTest = 5;
    console.log(nameTest);
}
console.log(nameTest);



let nameTest = 999;

function pointlessFun (x) {
    nameTest = 5;
    console.log("Inside pointlessFun, value is: " + nameTest);
}

console.log("BEFORE running pointlessFun, value is: " + nameTest);
console.log("*** Now about to RUN pointlessFunction! ***");
pointlessFun();
console.log("AFTER pointlessFunction finished, value is: " + nameTest);
