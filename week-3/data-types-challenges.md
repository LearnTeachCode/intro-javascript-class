## Data types review and practice challenges

Let's listen to a photograph by opening the image file in an audio editor! This video is a high-level look at what data types are all about, with a quick review of some basic data types in JavaScript:

:tv: **Video: Intro to data types with glitch art (10 min): https://youtu.be/aSba04iZWEY**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

<br/>

In the review challenges below, we'll tinker with data types and identify a couple of JavaScript's quirks.

<hr/>


## Challenge 1: 

Name the four primitive data types that we've seen so far.

**Google challenge:** What does it mean to say a data type is ***primitive***?

<br/>


## Challenge 2:

You can find out what a value's data type is by using the `typeof` operator. For example:

```javascript
// Check the type of a literal value (not inside any variable):
console.log( typeof "hi there!" );
console.log( typeof 17 );

// Check the type of a VARIABLE containing a value:
let myComputersName = "Codey McCodeFace";
let isYourFridgeRunning = true;
console.log( typeof myComputersName );
console.log( typeof isYourFridgeRunning );
```

**Your challenge:** Find out what the data type is for each of the following:

  1. The `document` (which represents the entire web page)
  2. `document.body` (which represents everything in the `<body>` element of the page)
  3. `document.body.textContent` (all the *text* stored in the document's body)
  4. The browser console itself (which we've been using to log messages this whole time!)
  
**Discuss:** How else can you tell if a variable is an object, *without* using the `typeof` operator?

<br/>


## Challenge 3:

Take a look at each line of code below, and take a guess as to what the result will be ***before*** you run it in your console:

```javascript
console.log(5 === 5);
console.log("5" === 5);

console.log(5 == 5);
console.log("5" == 5);

console.log(true == true);
console.log(true == 1);
console.log(false == 0);
console.log(false == "");

console.log(true === true);
console.log(true === 1);
console.log(false === 0);
console.log(false === "");
```
 
What do you think is the difference between the double equals comparison operator (`==`) and the triple equals version (`===`)? Why do you think JavaScript has both?

Do a little research for say 15 minutes to see what others say about this topic, and try to *identify some new vocabulary* related to these concepts! Be sure to take notes and write down any questions this sparks!

<br/>

## Challenge 3:

Did you know that there's one data type for `null` and another one for `undefined`? Why do you think we have both? They're obviously very similar, but what's one important difference between them? (This is another research challenge!)

<br/>

<hr/>

🏆 ***Hope you had fun exploring!*** Data types go straight to the heart of computer science, so it's a deep rabbit hole indeed -- so much more to learn! But with what you've practiced so far, you'll already have a much greater insight into how different data types can work together in your code.
