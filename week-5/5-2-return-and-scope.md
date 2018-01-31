## 5.2: Overview of the return statement and variable scope

Now that you know how to define functions, run functions, and use inputs (parameters and arguments), it's time to dive a little deeper into how functions work! This will also be our introduction to a very important programming concept: scope. This guide will also serve as a reference for solving our [function practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-2-function-challenges.md).

:books: **Prerequisites:**
  - [Section 5.1: Overview of functions: Defining them, running them, and using inputs](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-1-function-basics.md).

**Table of Contents:**
  - 5.2.1: The return statement versus `console.log()`
  - 5.2.2: Variable scope: local and global scope

<hr/>

## 5.2.1: The return statement versus `console.log()`

So far we've mostly been using `console.log()` within our functions, and/or using functions to show things on a web page. But there's a very important limitation to the way we've been using functions: any data inside the function ***cannot*** be reused in other parts of our code. ***The computer instantly forgets all the data inside a function as soon as the function finishes running!***

Let's take a look at a couple examples.

**Imagine a function that adds two numbers and displays the sum:**

```javascript
// Define our new function:
function displaySum (x, y) {
   console.log(x + y);
}

// Run our function with the arguments 2 and 4:
computeSum(2, 4);
```

Sure, it can show the final result `6` in the browser console, but that data -- the sum of the two numbers -- is deleted from the computer's memory as soon as the function is finished! What if we want to save that final value and use it for something else later? *With the code above, we can't!*

**Here's another example. What if we wanted to do something like this:**

```javascript
// Define a generic function that adds two numbers
function computeSum (x, y) {
   console.log(x + y);
}

// Pretend we're at a restaurant:
let mealCost = computeSum(17, 3);

// Then find out how much we should tip:
let tipAmount = mealCost * 0.18;

// Find the total amount to pay:
let totalCost = mealCost + tipAmount;

// Finally, display the total amount to pay:
console.log(totalCost);
```

The code does not work as expected! Try testing it in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit) and/or try using `console.log()` in several places to see what's happening to the data at each step.

### How to fix this? The `return` statement to the rescue!

The ***return*** statement is what allows us to pass data from *inside* the function to *outside* the function. It sets the data free!

**Fixing the broken code from above by using the `return` statement:**

```javascript
function computeSum (x, y) {
   console.log(x + y);
   // Now we'll ALSO use the return statement to pass the data to the rest of our code:
   return x + y;
}

let mealCost = computeSum(17, 3);
let tipAmount = mealCost * 0.18;
let totalCost = mealCost + tipAmount;

console.log(totalCost);
```

Now it works! By ***returning*** the sum, we can pass the data from *inside* the function to *outside* the function, so that way the computer can *remember* it even after the function has finished running.

  > **Helpful metaphor:** It's like passing the baton from one person to another in a relay race! :running: 

If you want to *reuse* any data from inside your functions -- for example, chaining functions together to do more complex things -- it's *very* important to use the `return` statement.


## 5.2.2: Variable scope: local and global scope

The concept of ***scope*** is intimately connected to the `return` statement and why we need to use it. (We will define "scope" in the next section below.) But first, why are these topics connected? Well, you can think of functions like miniature programs or even **miniature universes** with their own data wrapped up (and trapped!) inside.

**Here's another example similar to those above:**

```javascript
// Define our new function:
function capture (name) {
  let person = "This is " + name + " speaking. Help, I'm trapped inside a function!";
}

// Save the result of running the function:
// NOTE: this is just like using: let submitElem = document.getElementById("submit");
let me = capture("Liz");

// Display the message:
console.log(me);
```

But that code doesn't work! The person is quite literally *trapped* inside the function, like being stuck in a parallel universe, for you sci-fi fans. ;) And how do you move from one universe to another? I guess you could think of the `return` statement as sort of a portal or a wormhole that lets the data escape!

**Now let's set that person free with the `return` statement:**

```javascript
function setFree (name) {
  let person = "Set " + name + " free!";
  
  // Now we'll use the return statement instead of console.log()
  return person;
}

let me = setFree("Liz");
console.log(me);
```

Yay, it works! Like we saw earlier, the `return` statement allows us to pass data from inside our function and move it over to the rest of our code *outside* the function -- setting it free! Once it's free, the computer can save it in memory to reuse it later. (Remember, data inside a function is *forgotten* or *deleted* from memory as soon as the function finishes running.)


### So *why* does data get trapped inside a function?

This brings us to finally define the concept of ***scope*** or ***variable scope***. The word *scope* in computer science isn't that different from the plain English meaning -- for example, I can say that how to bake a souffle is ***outside the scope*** of this class! (In the context of our class, all we talk about is code!) So scope is all about ***context***, like the context of a conversation.

***In computer science, scope refers to where we will (or won't) use certain variables -- the context in which certain variables can exist.***

So remember how we said that data can be *trapped* inside a function? Another way to think about it is that the function is a particular *context* or *conversation*; we might have a `codingClass()` function that only contains data related to learning how to code, and we might have another function for `bakingSouffle()` that only contains data related to souffles.

### Global versus local scope

There are two main types of scope that exist in JavaScript: global or local. Variables can belong to one or the other, *never both!*

  - **Global scope:** Anything created at the top-most level of your code -- *outside of any functions* -- is said to be in the *global scope*. If it's *global*, that means it can be accessed from *anywhere* in your code. We call these ***global variables***.
  
    > One example of a special built-in global variable we've used already is the `document` object. We can access it from *anywhere* in our program because it's a global variable.

  - **Local scope:** Anything created *inside a function* exists ***only*** inside that function -- again, like they're trapped inside! The only way to set ***local variables*** free and pass them into the *global scope* is by using the `return` statement.


Phew, those definitions are pretty dense! Don't worry, we'll unpack what that all means with more examples.

Just remember, in short: when you create variables outside of a function, they're *global variables* that are accessible anywhere in your code. But when you create variables *inside* a function, they're *local variables* that are only accessible in that one function (unless you `return` them to "set them free" so to speak).

### Examples of variable scope (with a dream metaphor)

Here's a metaphor that helps me remember how variable scope and `return` statements work: it's like when you have a dream!

***Reality, the physical universe, is like the global scope.*** Things exist here! They're real! For example: a table, a tree, or you and me:

```javascript
let table = 1;
let me = "Liz";
```

When I go to sleep and I have a dream, it's like my brain is creating its own miniature universe, which can contain its own imaginary things:

```javascript
let table = 1;
let me = "Liz";

function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know kung foo!";
}
```

Things that exist in the real world often appear in our dreams. ***Global variables are accessible inside all functions.*** So variables go from the ***outside-in***, just like things from the real world can be pulled into our dreams:

```javascript
let table = 1;
let me = "Liz";

// Define a function (what the dream will be)
function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know kung foo!";
  console.log(me);
}

// Run the function (like falling asleep and dreaming NOW):
myDream();
```

***Try out the code above.*** Notice that we can `console.log(me)` *inside* the `myDream()` function because `me` is a *global variable*; it was created *outside* of any function, in the *global scope*. Again, variables can go from the *outside-in*.

But local variables *cannot* go from the inside-out! ***Local variables are only accessible inside the function in which they were created.*** So back to our metaphor, this is just like how imaginary things in your dream world *can't* affect reality directly! (That sounds like the plot of a good horror movie, doesn't it?)

Here's an example of how local variables *cannot* be accessed outside of their function:

```javascript
let table = 1;
let me = "Liz";

function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know kung foo!";
}

// This won't work! The robotNinjaPirate doesn't exist in the global scope!
console.log(robotNinjaPirate);
```

***Recap: how do you free a local variable? Use the `return` statement!*** In our dream metaphor, *returning* an output from your function is like *remembering* something from your dream after you wake up. So in JavaScript, it's like `return` actually *brings back* a piece of the miniature dream world into the real world, so that way you can tell people about your dream!

```javascript
let table = 1;
let me = "Liz";

function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know kung foo!";
  // I'll RETURN this value, so that way I can remember it after waking up:
  return robotNinjaPirate;
}

// Upon waking up, I'll remember part of my dream (creating a new variable to store it in memory):
let memoryOfMyDream = myDream();

// Now I can tell the world about my dream (at least the part that I remembered):
console.log(memoryOfMyDream);
```

I hope this metaphor helps you remember the basics of variable scope and the `return` statement. :) As always, it will only sink in with *lots of practice!*

<hr/>

:point_right: **Next, you can practice what you've learned about functions in [section 5.3: Function practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-3-function-challenges.md)!**
