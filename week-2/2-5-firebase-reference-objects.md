# 2.5: Intro to Firebase challenges: Database reference objects

To recap, there are **four key concepts for accessing data from Firebase:**

  1. [**From section 2.4:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md) Determining the **path** to your data's location in the database
  2. Creating a **reference object** in your JavaScript code, which represents a database location (a chunk of data)
  3. Setting up Firebase **event listeners** to retrieve the data from your database (which also updates in real time!)
  4. Using the **data snapshot** object to extract the **value** of the data

When we were [learning about paths in section 2.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md), we already saw an example of the second concept, Firebase's ***database reference objects***. Now let's take a closer look!

<hr/>

## Challenge 1:

First, let's review something familiar! Imagine we have the following code in our HTML file:

```html
<button id="win">Click here to win a bazillion dollars!</button>
```

**Discuss:**

  1. What's the ***full name*** of the built-in JavaScript function that we've been using to access HTML elements within our JavaScript code?
  
  2. How many inputs does the function require, and which **data type(s)** are used for the input(s)?
  
  3. What does the input represent, in plain English? (What does it mean? Where does it come from?)
  
  4. And what's the **data type** of the value ***returned*** by this function (its **output**)?

  5. What does the output represent, in plain English? (What is it used for? Why do we need it?)

**Then write a line of code to access the button in the example above.** Feel familiar?

<br/>

## Challenge 2:

**Take another look at the JavaScript code for our Glitch project from the previous section: https://glitch.com/edit/#!/firebase-practice-1**

**Discuss:**

  1. Which line of code do you think is creating a ***database reference object***?
  
  2. What's the ***full name*** of that Firebase function?
  
  3. How many inputs does the function require, and which **data type(s)** are used for the input(s)?

  4. What does the input represent, in plain English? (What does it mean? Where does it come from?)
  
  5. What do you think is the **data type** of the value ***returned*** by this function (its **output**)?
  
  6. What does the output represent, in plain English? (What is it used for? Why do we need it?)

<br/>

## Comparing DOM element objects to database reference objects

As we're starting to see, the process of creating ***database reference objects*** is pretty similar to how we've been creating DOM element objects since the first day of our class!

Let's look at **line 18** and **line 23** from [our previous example Glitch project](https://glitch.com/edit/#!/firebase-practice-1) and compare them side-by-side:

```javascript
// Create a JS object to represent the paragraph element 
// on our web page that has the id "testmessage"
let testMessageElem = document.getElementById("testmessage");

// Create a database reference object for the database location
// with the path of "helloworld"
let helloWorldRef = firebase.database().ref("helloworld");
```

### Side-by-side comparison:

|  | DOM element objects | Firebase database reference objects |
| --- | --- | --- |
| Names of the functions | `document.getElementById()` | `firebase.database().ref()` |
| Number of inputs | one | one |
| Data type of input | string | string |
| What the input represents | The `id` attribute of an HTML element on the web page | The **path** to a location in the database |
| Data type of output (returned value) | object | object |
| What the output represents | An element of the web page | A chunk of data in the database |

<br/>

**To summarize the similarities:**

  - `document.getElementById()` locates **a section of our *web page***, allowing us to access or modify **a certain *HTML element*** using JavaScript.
  
  - `firebase.database().ref()` locates **a section of our *database***, allowing us to access or modify **a certain *chunk of data*** using JavaScript.

<br/>

:star: **In both cases, the *input* helps us find what we're looking for, and the *output* is an object that gives us the information and the functions required to actually *interact* with it.**

<br/>

  > **Bonus questions:** What else do these two scenarios have in common? And what's ***different*** between them?

<br/>

## Challenge 3:

**Remix this Glitch project: https://glitch.com/edit/#!/firebase-practice-2**

That project is linked to the same working Firebase database we've been tinkering with so far, except now let's practice writing more of the code ourselves!

***Your challenge:*** Based on [the penguin database from section 2.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md#the-structure-of-firebase-databases), **write the missing JavaScript code to display the *name* of the penguin with ID number `7344`**.

**Hints:**

  - You'll need to look in the HTML file to get the `id` of the HTML element where we want the penguin's name to appear.
  - You need to write code on line **16**, **25**, **35**, and **50**.
  - Feel free to ignore the rest of the code for now, just read the comments!

<br/>

## Challenge 4:

Which of the following *ten* versions of the code below would actually work?

  > Yeah, I'm serious! Don't worry, your eyes won't bleed *too* much. :smiling_imp:

```javascript
// Version 1:
let lizBirthdayRef = firebaseDatabase("/people/liz/birthday");

// Version 2:
let lizBirthdayRef = firebase.Ref("/people/liz/birthday");

// Version 3:
let lizBirthdayRef = firebase().Database("/people/liz/birthday");

// Version 4:
let lizBirthdayRef = firebase.ref("/people/liz/birthday");

// Version 5:
let lizBirthdayRef = firebase.database().Ref("/people/liz/birthday");

// Version 6:
let lizBirthdayRef = firebaseDatabase.ref("/people/liz/birthday");

// Version 7:
let lizBirthdayRef = firebase().database().Ref("/people/liz/birthday");

// Version 8:
let lizBirthdayRef = firebase.database().ref("/people/liz/birthday");

// Version 9:
let lizBirthdayRef = firebase.database.ref("/people/liz/birthday");

// Version 10:
let lizBirthdayRef = firebaseDatabase().Ref("/people/liz/birthday");
```

Now you know why it's important to take frequent breaks to rest your eyes (and stretch your legs), *especially* when you're debugging! :laughing:

<br/>

## Bonus info: A note on namespacing

Let's take a closer look at this Firebase function that we've just learned how to use, and relate it back to a bigger topic. First, a review:

  - Remember how the `document` object represents the entire web page, containing the details of *every single thing* on the page?
  - Or how the `console` object is just a container for lots of things related to the console, including our favorite function `console.log()`?
  - Another example: all the built-in math functions in JavaScript live inside the `Math` object, like `Math.random()`, `Math.round()`, and many others!

<br/>

Similarly, the `firebase` object is just a container for all the built-in Firebase functions. And the `firebase.database()` function gives us access to an object representing the *currently active Firebase database*. And that object in turn has many functions of its own, one of which is `ref()`, which is the one we've been using this whole time!

So the ***full name*** of the function we've been using is `firebase.database().ref()`!

<br/>

:star: **There's a fancy word for this technique of *organizing* data (or code) by logically grouping things under different names: we call it *[namespacing](https://en.wikipedia.org/wiki/Namespace)!***

This helps us keep our code neat and tidy, and it also helps prevent [***name collisions***](https://en.wikipedia.org/wiki/Name_collision) -- when two different things have the same name, and you get them mixed up! Very bad!

<br/>

**For example:** What's the difference between `round()` and `Math.round()`? The first is *your own* custom function named `round()`, and the second is the *built-in* JavaScript function that is **namespaced** within the `Math` object.

Without that namespacing, if you created a function of your own named `round()`, it would overwrite JavaScript's built-in function for rounding numbers! That would be super confusing! So the creators of JavaScript grouped all the built-in math functions into an object named `Math` to keep them organized and tucked away for safe keeping.

<br/>

> **Bonus challenge:** What would happen if you overwrote the `Math` object itself? Hmm... Try it out and see what happens!

<br/>

**Moral of the story:** Namespacing is basically just the technique of putting things into separate folders (or other containers like JavaScript objects), so that way you won't get them all mixed up!

<br/>
<hr/>

:trophy: **Congratulations!** You're 50% finished with the concepts needed to display data from a Firebase database!

:point_right: **Next up:** [in section 2.6, we'll take a break from Firebase and dip our toes into the command line](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-2/2-5-firebase-reference-objects.md) -- now that you're familiar with paths, you pretty much already know how to navigate around a file system the *old-school* way!
