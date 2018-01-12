# 2.2: Intro to objects and arrays

❓ **If you have any questions,** please ask on the private Slack channel for our class.

:books: **Prerequisites:**
  - This section builds upon [everything in section 1 covering what we learned in our first class](https://github.com/LearnTeachCode/intro-javascript-class/tree/master/week-1).

**Table of Contents:**  
  - 2.2.1: Overview of data types
  - 2.2.2: Objects versus arrays
  - 2.2.3: Intro to objects
  - 2.2.4: Intro to arrays
  - 2.2.5: Intro to JSON

<hr/>

## 2.2.1: Overview of data types

First, here's a high-level look at data types in general, with a fun example of listening to a photograph by opening an image file in an audio editor:

:tv: **Video: Intro to data types with glitch art (10 min): https://youtu.be/aSba04iZWEY**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!


## 2.2.2: Objects versus arrays

Whereas the "primitive" data types like numbers, Booleans, and strings contain a single chunk of information, objects and arrays are **containers** for *multiple* pieces of data. So you can think of objects and arrays as containers for other variables, to help keep them organized.

**So what's the difference between an object and an array?**

  1. The main difference: arrays contain an ***ordered*** *list of things*, whereas things inside an object have no inherent order. Sort of like the difference between a filing cabinet and a bag.

  2. Things inside an array can only be accessed by an ***index number***, but things inside an object can be accessed by a ***label***, which you can think of as a string.

  3. Arrays and objects have different built-in functions and properties, which you'll learn more about gradually.

  4. Technically speaking, in JavaScript, arrays are a special type of object! (See an example of this in the section on arrays below.)


**Group discussion exercises: array or object?**

For each real-world example below, discuss whether you think it makes more sense to model it in our code as an array, an object, or some combination of the two. (Yes, you can put arrays inside objects, objects in arrays, arrays inside other arrays, etc!)

  1. The chapters in a book
  2. The lyrics for a song like "The Twelve Days of Christmas"
  3. A particular car with information like its make, model, and a list of its parts
  4. All the letters in the alphabet
  5. The coordinates for an item on a game board grid (like Battleship)
  6. A character in a role-playing video game like Dungeons and Dragons or World of Warcraft
  7. A user’s profile info (on a site like Facebook)
  8. A database containing many many users on a site like Facebook
  9. A deck of cards
  10. Ikea furniture instructions (just kidding, nobody reads them!)


## 2.2.3: Intro to objects

The video linked to below is a short review of the basics of objects: why they're useful, how to create them, access properties inside them, edit and create properties, plus a quick bonus on functions and methods at the end.

:tv: **Video: Intro to objects (13 min): https://youtu.be/Bza2U5mLxIQ**

  > **Note:** This is also an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on!

Objects are basically bags of variables! They help us keep our code organized -- like when you tidy up your desk by separating things into different drawers and boxes, instead of leaving everything scattered randomly all over the place.

**Examples of objects we've already used:**

  - The `document` object is one object we've been using all the time! It contains all of JavaScript's built-in information (and functions) related to the current web page! 
  
  - The console object is another one we use a lot, for its built-in function `console.log()` (among a few others)!

**Creating an object with object literal notation:**

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

**Properties and key-value pairs:**

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

**Pay attention to the syntax:**

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

**Accessing and changing properties of objects:**

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


## 2.2.4: Intro to arrays

The video below is a quick review of the very basics of arrays in JavaScript, plus a little practice challenge. :)

:tv: **Video: Intro to arrays (6 min): https://youtu.be/QlfR6ICa3gQ**

  > **Note:** This is also an older video, which is why you'll see `var` instead of `let`. Planning to remake this one later too.

An array is an *ordered list* of things. Just like objects, they can contain any type of data: numbers, strings, Booleans, objects, other arrays, etc. 

**Using an array's index:**

The things inside an array are called ***elements***, and they each have a number assigned to them, called the ***index***. And remember: computers always start counting at 0! So the first element in an array is at index 0:

![Diagram of an array](https://upload.wikimedia.org/wikipedia/commons/b/bf/CPT-programming-array.svg)


**Creating an array:**

```javascript
// Creating an array of strings
let studentNames = ["Amy", "Bob", "Calvin"];

// Creating an array of numbers
let favoriteNumbers = [3, 42, 7];

// Sometimes we format arrays like this too:
let myNicknames = [
  "Liz",
  "Frizzy Lizzy",
  "Lizards"
];

// You can mix and match different data types in the same array:
let someRandomData = [99, true, "ahhh!!", undefined, -15];
```

**Accessing and changing elements of arrays:**

To access an element in an array, type the name of the array followed by a pair of square brackets (`[ ]`) with the index number inside:

```javascript
// Create myFavoriteFoods:
let myFavoriteFoods = ["chocolate", "cupcakes", "donuts"];

// Display the value of my first favorite food:
console.log( myFavoriteFoods[0] );

// Create a new separate variable that uses my second favorite food in a sentence:
let greeting = "Hi, I'm Liz and I love " + myFavoriteFoods[1];

// We can change the value of an element in an array just like changing any other variable. So to change "donuts" to "pie":
myFavoriteFoods[2] = "pie";

// You can see what's inside an array at any time with console.log():
console.log(myFavoriteFoods);

// Very important: you can use a variable for the index! This is very useful when working with loops and many other scenarios:
let foodIndex = 1;
console.log( myFavoriteFoods[foodIndex] );
// The code above is the same as doing this:
console.log( myFavoriteFoods[1] );
```

**Adding and removing elements from arrays:**

All arrays have a number of built-in functions and properties, just like any other object in JavaScript. Yes, *arrays are technically a special type of object!*

  > In JavaScript, practically everything is an object. That's one of its quirks, which is both a strength and a weakeness of the language.

A couple of the most common built-in array functions are `push()` and `pop()`, to add or remove an element from the *end* of an array, respectively.

```javascript
// Create rainbow:
let rainbow = ["red", "yellow", "green", "blue"];

// Add "pot of gold" to the end of the rainbow:
rainbow.push("pot of gold");

// Show what's in the rainbow now, in the console:
console.log(rainbow);

// Somebody found the gold, so let's remove that last element:
rainbow.pop();

// Now the gold is gone again:
console.log(rainbow);
```

Notice how we're using ***dot notation** above! So we can do `rainbow.push()` just like we can do `console.log()`, because the `rainbow` array is technically a type of object. (Remember, if you see a period after a variable name, that means it's an object!)

There are *lots* of other very useful functions built into arrays! We'll look at more of them later on. For now, feel free to explore [the MDN reference page for arrays in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).


**The length property:**

We can find out how many elements are inside an array using the ***length*** property that's built into every array:

```javascript
// Create switches:
let switches = [false, true, false, false];

// Show how many elements are in that array:
console.log( switches.length );

// Create a new variable that contains the current number of elements in the array:
let numberOfSwitches = switches.length;

// Display it to confirm it's the same number as before:
console.log(numberOfSwitches);
```

## 2.2.5: Intro to JSON data

**JSON** stands for **JavaScript Object Notation**, and it's just a data format that uses JavaScript syntax. That's it! Nothing special.

The code for our penguins database in the previous section is already in JSON format!

**What are data formats (like JSON) all about?**

First, a metaphor: you and I are able to communicate because we both know how to *interpret* the sounds and symbols used in our common language. We've both *agreed* to use the same language: in this case, English! We wouldn't be able to communicate directly if I only spoke English and you only spoke French.

Computers also need to agree a common language in order to be able to communicate with each other! Every time you send or receive data over the internet, both computers need to agree on which *data format* they're using in that particular scenario.

**Data formats** are a lot like **data types** in our code; whereas individual variables can contain data of different types (like strings, numbers, etc), entire *collections* of data (or *entire files*) can also be structured using different data formats.

When you request data from an API over the internet -- for example, asking Facebook to send your app a list of all your Facebook friends -- you can often request the data in JSON format or several others, like XML (which used to be the main standard before JSON got popular).

**Example of an object formatted as valid JSON:**

```javascript
let gameCharacter = {
  "skillLevel": 9,
  "name": "Leeroy Jenkins",
  "alive": true
};
```

**Rules for the JSON format:**

  - JSON can contain strings, numbers, objects and arrays -- the only thing you can't have in JSON data are functions! (Since by definition, data doesn't really *do* anything on its own; it just sits there, waiting for some software program to do something with it.)

  - **In valid JSON, the property names (or keys) of any objects must be** ***strings***! That's why in our penguin database example above, the property names looks like `"canFly"` and `"origin"`, instead of `canFly` and `origin` (without the quote marks).

So in short: to turn a JavaScript object into valid JSON-formatted data, just make sure every property name is surrounded with quote marks, and make sure your object doesn't contain any functions. (We'll talk about functions inside objects later on.)


**The JSON.stringify() and JSON.parse() functions:**

Whenever you send or receive data within your software app, it's basically just one giant **string**; our code doesn't know what it means until we analyze it! Data only has meaning based on *context*; it needs to be *interpreted* based on what data format it's written in. (Again, that's what data types and data formats are all about: telling the computer *how* to interpret the raw data.)

Going back to our metaphor: if you and I are speaking in person, the actual data of our conversation could be the *sound waves* that my vocal coords produce, which your ears can then pick up. But sound waves *by themselves* have no meaning! They're just vibrations in the air molecules. They only have *meaning* when they're interpreted by a human brain that understands that particular language.

In JavaScript, the built-in `JSON.stringify()` function is the equivalent of converting your thoughts into those sound waves, ready to be sent to somebody else. The "stringify" function converts our JavaScript object into one giant string, because later on when you use other built-in functions to actually *send* data over the internet, those functions require a string as input.  Another metaphor I like: it's just like stuffing things into an envelope or box before you ship it!

To do the opposite -- *unpacking* the data, opening the envelope, converting sound waves back into English words  -- we use another built-in function: `JSON.parse()`! That "parsing" function analyzes and interprets a JSON-formatted string, translating it back into actual code that can run inside our application.

**Example of stringifying an object into a JSON-formatted string:**

```javascript
// Create a JavaScript object that follows JSON formatting rules:
let player1 = {
  "skillLevel": 9,
  "name": "Leeroy Jenkins",
  "alive": true
};

// Here's what it looks like in the console as an object:
console.log(player1);

// Pretend we want to SEND our character data to someone over the internet.
// This is how we turn our actual code into a string, all packaged up and ready to be sent:
let stringifiedData = JSON.stringify(player1);

// You can see the result in the console. It's now a string:
console.log(stringifiedData);
```

**Example of parsing a JSON-formatted string into a JavaScript object:**

```javascript
// Now pretend we RECEIVED this data from somebody else:
let rawData = '{"skillLevel": 1, "name": "Newbie", "alive": false}';

// This is how we convert it from the raw data (a string) back into
// an actual JavaScript object:
let player2 = JSON.parse(rawData);

// If we console.log this new result, it will be treated as an actual
// JavaScript object again!
console.log(player2);
```

So `JSON.stringify()` and `JSON.parse()` are *opposites*; they undo each other. You *stringify* your code when you're going to *send* it somewhere. Or the opposite: you *parse* a string when you *receive* data from somewhere.

That's just a quick preview of JSON data for now. We'll do more with it later on!
