## 2.2.3: Practice challenges: Intro to objects

Objects are basically just bags of variables! They help us keep our code organized -- like when you tidy up your desk by separating things into different drawers and boxes, instead of leaving everything scattered randomly all over the place. :)

:tv: **Video: Intro to objects (13 min): https://youtu.be/Bza2U5mLxIQ**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. (Planning to remake it a bit later!)

In these practice challenges, we'll learn how to identify, create, read from, and modify JavaScript objects. Let's get coding!

<hr/>

## Challenge 1:

There are a few different ways to create an object in JavaScript. For now, we'll be using ***object literal notation***, which looks like this:

```javascript
// Creating an empty object (an object with nothing inside it)
let myEmptyObject = { };

// Creating an object that contains two other variables, a number and a string:
let playingCard = { number: 3, suite: "Hearts" }

// This is how we usually format objects to make them easier to read:
let player = {
  skillLevel: 9,
  name: "Leeroy Jenkins"
};
```

**Your challenge:** For the last section of code that creates the `player` object, identify **five** different ways to ***break*** the code! Be sure to test it in the browser console or in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit).

  - For each bug you created, why did it break?
  - Which pieces of the code or syntax need to stay the same, and which pieces can be changed?

<br/>

## Challenge 2:

Imagine we're building a new social network site to compete with Facebook. (Hey, we can try!) As with any big project, we'll start small and just use some fake data. In the code below, we have a bunch of separate variables for some fake data related to one imaginary user:

```javascript
var myName = "Sally Awesomepants";
var myProfession = "full-stack JavaScript developer";
var myAge = 32;
var myFavColor = "purple";
var myFavFood = "pizza";
var myFavAnimal = "penguin";
var myFavNumber = 3;
```

This code isn't so bad on its own, but imagine if we had a database of *thousands* of users just like this one. That would be *impossible* to keep organized with a bunch of separate variables!

**Your challenge:** Organize that data into *one new object* representing our imaginary user.

<br/>


## Some new vocabulary:

When a variable is inside an object, we call it a ***property*** or a ***key***. All information stored inside an object comes in pairs, which we call ***key-value pairs***.

Each key is followed by a colon (`:`) and then its value. Multiple key-value pairs are separated with commas (`,`) which is a pattern you'll see a lot in programming languages -- just like how we write lists of words in English!

<br/>


## Challenge 3:

Every year, we all have birthdays and Facebook notifies all our friends that we're getting old! (Just kidding; you're only as old as you *feel!*)

To add that feature to our social network, we definitely need to figure out two important things: 1) how to ***access*** (in other words, how to *read*) one piece of our data, and 2) how to ***change*** the value of that one piece of data.

**Your challenge:**
  
  1. Using the object you just created, write one more line of code display Sally's current age in the browser's console.
  
  2. Next, write another line of code to *change* Sally's age, pretending it's her birthday!
  
  3. Display Sally's new age in the browser's console.
  
  4. Finally, write one line of code to make the console display the *entire object* that represents Sally.

  > **Hint:** Remember how in previous classes, we were able to access and also *change* the text that appears on a web page (or part of a page)? The syntax will look *exactly* like that! Reference our JavaScript cheat sheet.

<br/>


## A new trick for using the console:

Remember how we could use the `console.log()` function with a DOM element to confirm that we selected the correct part of the page? The console will display the HTML code of that element, and if you hover your mouse over that code in the console, it will highlight that section of the web page:

```javascript
// Try this in your console right now!
console.log( document.body );

// You can also do something like this (if the page has an element with the id of "cool")
console.log( document.getElementById("cool") );

// A second way to write that in two separate steps:
let coolElement = document.getElementById("cool");
console.log( coolElement );
```
<br/>

:pencil: **Every element of a web page is represented as a JavaScript object.** That's why we call them DOM elements, because DOM stands for Document **Object** Model!

So every DOM element is an object containing its own ***key-value pairs*** -- for example, almost every DOM element has a key (also called a property) named `textContent`.

There are *many* other key-value pairs hidden away inside each DOM element. But when we use `console.log()` like we did in the example code above, the console only shows us the *HTML representation* of that element, not the *JavaScript representation* with all of its key-value pairs.

<br/>

:star: **So here's the trick to see any DOM element's key-value pairs:** use the built-in function `console.dir()` instead!

  > **Sidebar:** The "dir" stands for "directory", which is another word for "catalogue" or "listing". So `console.dir()` shows a directory of a DOM element's key-value pairs, not unlike how a phone book lists names/phone number pairs!
  
<br/>

Try it out with the code below:

```javascript
// Try this in your console right now!
console.dir( document.body );

// You can also do something like this (if the page has an element with the id of "cool")
console.dir( document.getElementById("cool") );
```
<br/>

**Bonus:** Look at the key-value pairs of the *entire document object* itself!

  > And yes, the `document` object is the *Document* in the *Document Object Model* acronym. It's the *root* of the entire tree or hierarchy, the mothership of the whole website!

<br/>


## Challenge 4:

Let's imagine our social network site is mostly finished, and users are beta-testing the site. Many users have requested that we let them display their *relationship status* as well, so that way all their friends can see when their status changes from `"In a Relationship"` to `"It's Complicated"`!

**Your challenge:** Add a new *property* (also called a *key*) to the object representing our user named Sally, so that way we can keep track of her relationship status. Be sure to use the console to test if it worked!

  > **Hint:** The way you write this looks exactly the same as *changing* the value of a property.

<br/>


## Challenge 5:

Create an object that contains *another object* -- for example, a `house` object that contains some information about the house, including a `kitchen` object that contains information about that house's kitchen.

  > **Hint:** Remember that you can assign *any value* (of any data type) to a variable, and objects are a data type! You can use this trick to create the *inner* object first, assign it to a variable, and then use that variable name as the *value* in one of the *parent* object's key-value pairs.

Once you've created this *nested data structure*, how would you access a single piece of information about the kitchen and display that value in the console?

  > **Hint:** We've accessed an object inside another object before, when we changed all the text inside the body of a web page.

<br/>


## Bonus challenge 1:

This one's a Google challenge! Look up how to ***remove*** a property from an object. Test out any code you find to see if it actually works, and then try removing the property that we had previously added to track Sally's relationship status.

<br/>

## Bonus challenge 2:

What happens if you try to assign *an entire object* to be displayed on a web page? Then try to come up with a couple ideas for how to display all of an object's data on a web page.

  > **Hint:** Look up the **JSON** functions that are built into JavaScript! (We haven't talked about JSON, but it stands for JavaScript Object Notation. It's a standardized way to format information using the same exact "object literal" notation that we've been using to create JavaScript objects! (But that's a topic for later.)

<br/>

<hr/>

:trophy: ***Great job!*** You can now use objects to store and access collections of data, an essential tool for every software application you'll ever create! Next up, we'll look at a very special kind of object: arrays!
