## 2.3: Practice challenges: Intro to functions

Functions are one of the most fundamental concepts in programming, but full of nuances that can be challenging to wrap your head around! Let's take a first look at the *very basics* of how functions work and why they're useful. (We will return to the topic of functions in more detail later on in our class. One step at a time!)

<hr/>

## Overview of functions:

📺 **Video: Review of Function Basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

<br/>

### What are functions?

Functions are like the ***verbs*** of programming, because they perform actions within a program. You can think of functions as their own miniature computer programs that can be *reused* multiple times.

<br/>

### Why are functions useful?

Because they keep your code modular and **DRY** (Don't Repeat Yourself, an important principle for programming and tech in general)!

Keeping your code modular helps you organize everything better. Messy code is like a messy desk with papers scattered all over it -- that makes it harder to find things! Messiness also makes it harder to debug your code if anything breaks. So, wrapping up your code in different functions is a bit like organizing your desk and putting things into boxes and separate piles.

<br/>

### Defining versus calling functions:

When it comes to working with *your own* custom functions, you'll always be using them in ***two stages:***

  1. **Defining your function** - This is like creating an entry in a dictionary for a new word that you just invented; the definition specifies what the word means! In our case, a *function definition* specifies what that function will do.
  
  2. **Calling your function** - This second step is like using a new word in a sentence after you've looked it up in the dictionary. When you *call* your function, the computer looks it up in memory (like looking up a word in the dictionary), and then it runs the code inside of the function (like using a new word in a sentence).

<br/>

:star: **You only need to define a function once, which then allows you to run it multiple times.** It's a lot like initializing a variable with the `let` keyword -- only do it once! -- and then you can use that variable as many times as you want to afterwards, *without* using `let`.

<br/>

### Function vocabulary note:

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

## Challenge 1:

First, take a look at the code below and run it in your browser console or in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit) to test it out.

**Discuss:**

  1. Which lines of code are *defining* the function versus *calling* the function?
  2. What would you identify as the ***four parts*** of the function definition?

```javascript
function sayHello () {
   console.log('Hello!');
}

sayHello();
```

  > **Important note:** There's *more than one way* to define functions in JavaScript! We're just using this one way for now, and it's totally fine if you always define functions this way. (Mostly a matter of personal preference.)

<br/>

## Challenge 2:

Take the code for the example function given above, and **break it** five different ways! 

<br/>

## Challenge 3:

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

## Challenge 4:

Define a function that will display in the console *all the text inside the entire body element of the web page*! Name it whatever you want -- but it's best to use a descriptive name, and remember stick to camel case  style (`camelCaseStyleForVariableNames).

Then write the code that will ***call*** (in other words, *run* or *execute*) your new function, and test it on one of your favorite websites by running your code in the browser console while you're on that web page! 

<br/>

## Bonus challenge 1:

**Identify** the three built-in JavaScript functions that we've already been using in our class so far, and then **discuss:** what might the four parts of their function definitions look like?

<br/>

## Bonus challenge 2:

What's wrong with the code below? Let's fix it!

```javascript
function (num) {
  console.log(num * 2);
}
```

<br/>

## Bonus challenge 3:

The code below should display the number `42` in the console, but it doesn't work! How would you fix it? (We haven't learned about this stuff in class yet; this is a preview for later!)

```javascript
getHalf () {
 return num / 2;
}
let newNum = getHalf(84);
console.log(newNum);
```

<br/>

<hr/>

:trophy: ***Great job!*** You're on your way to being a functional programming wizard! Next, we'll put all the pieces together to create our finished Hangman game (but with one important bug to solve!), and then we'll start working on identifying and fixing that cliffhanger bug.
