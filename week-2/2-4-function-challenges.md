# Section 2.4: Intro to functions with parameters and arguments

Functions are one of the most fundamental concepts in programming, but full of nuances that can be challenging to wrap your head around! Let's take a first look at the *very basics* of how functions work and why they're useful. (We will return to the topic of functions in more detail later on in our class. One step at a time!)

<hr/>

## Overview of functions:

📺 **Video: Review of Function Basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

<br/>

### What are functions?

You can think of functions a few different ways:

  1. **Functions are the *verbs* of programming**; they perform actions! Even more importantly, functions are ***reusable*** actions. For example, if you have a function `eat()`, you can use it to eat lots of things -- `eat("cupcakes")` and `eat("cookies")` and maybe even some vegetables once in a while.
  
  2. **A function is also like a *factory***; it takes raw materials as ***inputs***, combines them in some way, and then produces some final product as its ***output***. (This is a bit oversimplified of course, as metaphors usually are, but that's the basic idea.)
  
  3. You can also think of **functions as *miniature computer programs*** in and of themselves! They can have their own variables and their own space in the computer's memory. In fact, functions work best when they're *self-contained*, so that way they're very easy to reuse in many different projects.

<br/>

## Challenge 1:

Before we talk about functions in more detail, let's dive right into the code and experiment!

**First, make a prediction:** what do you think will happen when you run the code below, and why? Discuss your ideas *before* running the code.

```javascript
function shoutAtConsole (phrase) {
   console.log(phrase + "!!!!!!!!!!!!!!!!1!1!!!1!11!1!eleven");
}

shoutAtConsole("Run");
```

After discussing it, then run the example code -- you can copy-paste the entire thing directly into your browser console, or in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit).

<br/>

## Challenge 2:

Again, *before running the code*, make a prediction and discuss:

  1. What do you think this code will do, and why?
  2. How is this code different from the previous example?

```javascript
function makePageRed () {
   document.body.style.background = "red";
}

makePageRed();
```

Then try out the code to see if you were right! You'll need to run it inside Glitch or copy-paste it into your browser console. (Python Tutor doesn't provide a web page for your JavaScript code to interact with, so it won't work there.)

<br/>

## Challenge 3:

You know what to do! First make a prediction and discuss:

  1. What do you think this code will do, and why?
  2. How is this code different from the previous example?

```javascript
function makePageBlue () {
   document.body.style.background = "blue";
}
```

Then run the code above -- again, you'll need to either copy-paste it into your console or run it inside of Glitch.

<br/>

## Challenge 4:

How about this code? Discuss what you think will happen *first*, and then run the code *afterwards*.

```javascript
makePagePurple();
```

<br/>

## Challenge 5:

And how about this code? Discuss it before you try it:

```javascript
function shoutAtConsole (phrase) {
   console.log(phrase + "!!!!!!!!!!!!!!!!1!1!!!1!11!1!eleven");
}

shoutAtConsole("Run");
shoutAtConsole("Oh no");
shoutAtConsole("Zombies");
shoutAtConsole("Seriously, there are zombies here. Run");
```

How is this code different from the example in challenge #1?

<br/>

## Challenge 6:

I know you can't get enough of functions, so here's another one! Discuss first: what do you think will happen when you run this code?

```javascript
function sevenLanguageGreeting (name) {
   console.log("Bonjour, " + name);
   console.log("今日は, " + name);
   console.log("Hujambo, " + name);
   console.log("Hyvää päivää, " + name);
   console.log("здравствуйте, " + name);
   console.log("Ciao, " + name);
   console.log("السَّلَامُ عَلَيْكُمْ‬, " + name);   
}

sevenLanguageGreeting("Boaty McBoatface");
```

And then test it in your console or in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit).

  > **Just for fun:** If you haven't heard of Boaty McBoatface, look it up online. There's a hilarious real-life story involving science, contests, and internet culture.

<br/>

## Group challenge: let's break stuff!

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/e63388c0-f352-4d69-91aa-bce96a6959dd) so we can all write code together at the same time. :)

Given the example code provided in the `script.js` file, let's find several ways to break it! How many different kinds of error messages can we cook up?

**Group discussion:**

  1. Which line(s) of code are *defining* the function, and which line(s) are *calling* the function?
  
  2. What's the difference between defining vs calling a function?
  
  3. How would you break up a *function definition* into **four disctinct parts**?
  
  4. Which parts of a function definition are *required* to be there, and which parts are optional?
  
  5. And for *calling* a function, which part are required and which are optional?


<br/>

## Defining versus calling functions:

When it comes to working with *your own* custom functions, you'll always be using them in ***two stages:***

  1. **Defining your function** - This is like creating an entry in a dictionary for a new word that you just invented; the definition specifies what the word means! In our case, a *function definition* specifies what that function will do.
  
  2. **Calling your function** - This second step is like using a new word in a sentence after you've looked it up in the dictionary. When you *call* your function, the computer looks it up in memory (like looking up a word in the dictionary), and then it runs the code inside of the function (like using a new word in a sentence).

<br/>

:star: **You only need to define a function once, which then allows you to run it multiple times.** It's a lot like initializing a variable with the `let` keyword -- only do it once! -- and then you can use that variable as many times as you want to afterwards, *without* using `let`.

<br/>

## Function vocabulary note:

There are several different words people use when talking about functions, and they all mean pretty much the same thing!

**Other words for "calling" a function:**
  - ***Run*** a function  
  - ***Execute*** a function
  - ***Use*** a function
  - ***Invoke*** a function

**Other words for "defining" a function:**  
  - ***Declare*** a function
  - ***Create*** a function
  - ***Initialize*** a function

Tech jargon is maybe the least fun part of becoming a skilled software developer, but it's a necessary evil. =P

<br/>

## Challenge 7:

The code below should display the message `"I stopped the evil supervillain from dividing by zero!"` in the console. Why isn't it working? Fix it, and hurry! The fate of the universe depends on you!!!

```javascript
// Defining our function
function stopUniverseFromImploding () {
 console.log("I stopped the supervillain from dividing by zero!");
}

// Running our function
stopUniverseFromImploding;
```

<br/>

## Challenge 8:

What's wrong with the code below? Your challenge is to fix it!

```javascript
function (userName) {
  console.log("Welcome, " + userName);
}
```

<br/>

## Challenge 9:

Once you've solved the bug for challenge #8 above, next **call** the function **three times** with **three different names** as inputs. If it worked, you should then see three diffierent messages welcoming each new user!

  > **Functions are like reusable templates:** you can write the code once, and use it multiple times. And with inputs, now your functions can accomplish one common task in *many different scenarios!*

<br/>

## Challenge 10:

**Define** a function that will change the background of the web page to *any color you want!* Feel free to copy from challenge #2 or 3 and modify the code as needed.

Then **call** your new function, and test it on one of your favorite websites by running your code in the browser console while you're on that web page. 

<br/>

## Challenge 11:

First, define a function that takes ***one input***, subtracts 10 from it, and then logs the result to the console. Name it whatever you want -- but best to use a descriptive name, and stick to camel case style formatting.

  > [**Camel case formatting**](https://en.wikipedia.org/wiki/Camel_case) refers to the convention of naming variables and functions with wordsLikeThis, with noHyphensOrUnderscores, where every word *except* the first word is capitalized. Famous examples of camelCase names in popular culture include "iPhone" and "eBay".

Next, test your function by **calling it three times** with three different numbers as inputs! Be sure to check the console to see if it worked; you should see three different results.

<br/>

## Vocabulary note: Arguments versus parameters

When casually speaking about functions, we use the word ***inputs*** to refer to the values that go into the function (also phrased as "the values that are passed into the function"). But there are two other more *technical* and *specific* terms that you'll hear: ***arguments*** and ***parameters***.

  - A **parameter** is a *placeholder* used to represent an input inside a ***function definition***. The parameters represent values that have not been defined yet.
  
  - An **argument** is an *actual value*, a piece of data, that is passed into a function ***when you run the function***. Arguments *replace* the parameters (placeholders) in the function definition.

<br/>

So remember: parameters are part of the *first stage* when you *define* a function, and arguments are part of the *second stage* when you *run* a function.

***Example:***

```javascript
// 3 PARAMETERS, placeholders that will be replaced with the actual values later:
function displayThreeWords (word1, word2, word3) {
	console.log(word1 + ' and ' + word2 + ' and ' + word3);
}

// 3 ARGUMENTS, specific values that will REPLACE the parameters (the placeholders):
displayThreeWords('pineapple', 'motorboat', 'toothbrush');
```

<br/>

:star: **Here's a handy way to remember it:**

  - The ***parameter*** is the ***parking space*** (a placeholder, an empty space).
  - The ***argument*** is the ***automobile*** (that parks in the empty space).

<br/>

## Challenge 12:

Define a function that takes **two parameters**, adds them together, and `console.log()`s the sum. Then test your function by **calling** it three times, using **two arguments** each time you call the function.

<br/>

## Challenge 13:

This time, run the code first! Take a look at the output. Then identify why it gave that output, and add the piece that's missing:

```javascript
function createMadLib1 (famousName, verbing, nouns, adjective) {
	console.log("The ancient art of " + verbing + " was popularized by " + famousName + " in 1150 BC. It is a very " + adjective + " form of creative expression, especially when combined with " + nouns + ".");
}

createMadLib1('Larry King', 'ice skating', 'military secrets');
```

<br/>


## Challenge 14:

OK, now discuss what you think will happen, ***before*** you run this code. Do you think there will be an error? If so, what do you think the error message will say? Why?

```javascript
function smooshWords (word1, word2) {
	console.log(word1 + word2);
}

smooshWords("break", "fast", "pizza");
```

Then test it to find out!

<br/>

## Challenge 15:

Again, make a prediction and discuss it first. Then test the code afterards:

```javascript
function saySomething () {
	console.log("Something");
}

doSomething("hi", "hello", "are you listening?", "stop play Overwatch and pay attention!");
```

Then test it to find out!

<br/>

## Why are functions useful?

Because when use effectively, functions keep your code modular and **DRY**: ***Don't Repeat Yourself***, one of the most important principles of software development!

Just like it's harder to find things if you have a messy office with papers scattered all over the place, it's harder to find the cause of a bug if your *code* is scattered all over the place! Functions help us keep our code organized into separate, reusable actions. That makes bugs easier to find, and easier to avoid in the first place.

<br/>

## Recap: How to define and call functions

**Defining functions:** There are ***four parts*** to every function definition:

  1. The `function` keyword
  2. The name of the function (follow same naming rules as variables)
  3. Parentheses containing any optional *parameters* (placeholder variables that will later contain some data)
  4. Curly brackets containing the code that the function will run (called the *function body*)

**Calling functions** (also called *running*, *executing*, or *invoking* functions):

  1. The name of the function
  2. Parentheses containing any optional *arguments* (the actual data that will replace the parameters)

<br/>
<hr/>

:trophy: ***Wonderful work!*** You're on your way to being a functional programming wizard!

:point_right: **[Next up: ...!](#)**
