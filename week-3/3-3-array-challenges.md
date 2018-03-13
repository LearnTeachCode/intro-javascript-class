## 3.3: Practice challenges: Intro to arrays

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
