# Section 3.6: Intro to objects

Objects are basically just bags of variables! They help us keep our code organized -- like when you tidy up your desk by separating things into different drawers and boxes, instead of leaving everything scattered randomly all over the place. :)

<br/>

:tv: **Video: Intro to objects (13 min): https://youtu.be/Bza2U5mLxIQ**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. (Planning to remake it a bit later!)

<br/>

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

<br/>

**Your challenge:** Create an object that represents ***you***, and including the following information:

  - Your name
  - Your hometown
  - What you ate for dinner last night

<br/>

Be sure to test it in the browser console or in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit).


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

:star: When a variable is inside an object, we call it a ***property*** or a ***key***. All information stored inside an object comes in pairs, which we call ***key-value pairs***.

<br/>

Each key is followed by a colon (`:`) and then its value. Multiple key-value pairs are separated with commas (`,`) which is a pattern you'll see a lot in programming languages -- just like how we write lists of words in English!

<br/>


## Challenge 3:

Every year, we all have birthdays and Facebook notifies all our friends that we're getting old! (Just kidding; you're only as old as you *feel!*)

To add that feature to our social network, we definitely need to figure out two important things:

  1. How to ***access*** one piece of our data
  2. How to ***change*** the value of that one piece of data.

<br/>

Based on what we've learned in previous classes, how do you think we can access and change data that's inside an object?

<br/>

**Your challenge:**

  1. Display *the entire* object in the console (use the object that you had just created to represent `Sally`)
  
  1. Write one more line of code to display Sally's current age in the browser's console.
  
  1. Next, write another line of code to *change* Sally's age, pretending it's her birthday!
  
  1. After changing her age, Display Sally's new age in the browser's console.
  
<br/>

  > **Hint:** Remember how in previous classes, we were able to access and also *change* the text that appears on a web page (or part of a page)? The syntax will look *exactly* like that! Reference our JavaScript cheat sheet.

<br/>

## Challenge 4:

Let's imagine our social network site is mostly finished, and users are beta-testing the site. Many users have requested that we let them display their *relationship status* as well, so that way all their friends can see when their status changes from `"In a Relationship"` to `"It's Complicated"`!

<br/>

**Your challenge:** Add a new *property* (also called a *key*) to the object representing our user named Sally, so that way we can keep track of her relationship status. Be sure to use the console to test if it worked!

<br/>

  > **Hint:** The syntax for *adding* a new property to an object looks exactly the same as *changing* the value of a property.

<br/>


## Bonus challenge 1:

Create an object that contains *another object*:

  1. Create a `kitchen` object that contains the following data:

     - The size of the kitchen in square feet
     - The type of stove (electric? gas?)
     - An emptry `refrigerator` object

  2. Inside that `refrigerator` object (this is the *nested object), give it the following key-value pairs:

     - The width of the fridge in number of feet
     - The height of the fridge
     - The brand of the fridge (Frigidaire? KitchenAid? Samsung?)


<br/>

  > **Hint:** Remember that you can assign ***any data type*** to a variable, and objects are a data type! 

<br/>

## Bonus challenge 2:

Display the brand of the fridge in the browser console. 

<br/>

  > **Hint:** We've accessed an object inside another object before, when we changed all the text inside the body of a web page.

<br/>


## Bonus challenge 3:

This one's a Google challenge! Imagine Sally no longer wants the world to know whether she's single or married or "it's complicated". We'll have to remove that data from her account!

<br/>

**Your challenge:** look up how to ***remove*** a property from an object. Then remove the property that we had previously added to track Sally's relationship status.

<br/>

## Bonus challenge 4:

What happens if you try to display *an entire object* on a web page? Try it with `document.body.textContent = nameOfYourObjectHere;` and see for yourself.

Weird, right?

Then think if there's a way to take *all* of the data inside an object and do something with it so that you actually *can* display all of its data onto a web page.

<br/>

  > **Hint:** Look up the **JSON** functions that are built into JavaScript! <br/><br/>We haven't talked about JSON, but it stands for JavaScript Object Notation. It's a standardized way to format information using the same exact "object literal" notation that we've been using to create JavaScript objects! (But that's a topic for later.)

<br/>

<hr/>

:trophy: ***Great job!*** You can now use objects to store and access collections of data, an essential tool for every software application you'll ever create!

:point_right: **Next up:** [....](#)
 
