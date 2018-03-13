## 2.2.3: Practice challenges: Intro to objects

Objects are basically bags of variables! They help us keep our code organized -- like when you tidy up your desk by separating things into different drawers and boxes, instead of leaving everything scattered randomly all over the place. :)

:tv: **Video: Intro to objects (13 min): https://youtu.be/Bza2U5mLxIQ**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on!

<hr/>

## Examples of objects we've already used

  - The `document` object is one object we've been using all the time! It contains all of JavaScript's built-in information (and functions) related to the current web page! 
  
  - The `console` object is another one we use a lot, for its built-in function `console.log()` (among a few others)!

<br/>

## Creating an object with object literal notation

There are a few different ways to create an object in JavaScript. For now, we'll be using ***object literal notation**, which looks like this:

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

## Properties and key-value pairs

When a variable is inside an object, we call it a ***property*** or a ***key***. All information stored inside an object comes in *pairs*, which we call **key-value pairs**.

Here's an example of the same information being created as separate variables, and then being created as key-value pairs inside an object:

```javascript
// Creating two normal variables that stand on their own:
let myDogsName = "Fido";
let myDogsAge = 3;

// Creating an object to contain both of those related variables:
let myDog = {
  name: "Fido",
  age: 3
};
```

<br/>

## Pay attention to the syntax

In object literal notation, we use a pair of **curly brackets** to wrap up the contents of the object. Each key is followed by a **colon** and then its value, and multiple key-value pairs are separated by a **comma**. Quick tip: Never put a comma after the last key-value pair! This is a common cause of errors:

```javascript
// This will cause an error because of the comma after the last key-value pair:
let incorrectObject1 = {
  firstKey: "first value",
  sceondKey: "second value",
};
// This will also cause an error for the same reason as above:
let incorrectObject2 = {
  onlyKey: "value here",
};
```

<br/>

## Accessing and changing properties of objects

To access anything that's inside an object, you type the object's name followed by a period (` . `), then immediately followed by the name of the thing you want to access. Anything you can do with a normal variable, you can do with a property of an object:

```javascript
// Create myDog:
let myDog = {
  name: "Fido",
  age: 3
};
// Display the value of myDog's "name" property in the console":
console.log( myDog.name );

// Create a new separate variable that contains myDog's age in human years (very rough estimate):
let myDogsHumanAge = myDog.age * 7;

// We can change the value of an object's property just like changing any other variable. So on myDog's birthday:
myDog.age = 4;

// We can add new properties to an object like this:
myDog.breed = "Poodle";

// But to completely delete a property from an object, we need to use a special keyword. It looks weird, but this is how:
delete myDog.breed;

// You can see what's inside an object at any time with console.log():
console.log(myDog);
```

<br/>

<hr/>

:trophy: ***Great job!*** You can now use objects to store and access collections of data, an essential tool for every software application you'll ever create! Next up, we'll look at a very special kind of object: arrays!
