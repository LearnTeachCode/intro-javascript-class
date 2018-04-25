## 4.3: Practice challenges: Intro to variable scope, functions with outputs, and the `return` statement

We learned how functions can take ***inputs*** by assigning special variables (called *parameters*) inside the *function definition*, which later get replaced with specific values (the *arguments*) when the function is *called*.

Well, functions can also give ***outputs*** to the rest of your code! Let's learn more about that, along with the closely-related topic of *variable scope*. As always, we'll be learning by tinkering, breaking stuff, taking it apart and putting it back together again!

📺 **Video: Review of Function Basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

:books: **Prerequisites:**
  - [Section 2.3: Intro to functions](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-3-function-intro-challenges.md)
  - [Section 4.2: Intro to functions with inputs (parameters and arguments)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-4/4-2-function-input-challenges.md)
  
<hr/>

## Challenge 1:

Take a look at the function defined below, and ***before you run the code***, **discuss**: What do you think will appear in the console?

Then test it out for yourself in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit).

```javascript
function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know ninjitsu!";  
}
console.log(robotNinjaPirate);
```

**Discuss:** Was your hypothesis correct? Why or why not? (Just take some guesses and talk about them.)

**Next, try to fix the code** so that the value of `robotNinjaPirate` will appear in the console. See if you can fix it ***three different ways***.

<br/>


## Variable scope: global versus local

Let's take a first look at the concept of ***variable scope*** and ***scope*** in general. The word *scope* in computer science isn't that different from the plain English meaning -- for example, I can say that how to bake a souffle is ***outside the scope*** of this class. (In the context of our class, all we talk about is code!) So scope is all about ***context***, like the context of a conversation.

:star: ***In computer science, scope refers to where we will (or won't) use certain variables -- the context in which certain variables can exist.***

You can think of each function as a conversation with its own particular *context*. We might have a `codingClass()` function that only contains data related to learning how to code, and we might have another function for `bakingSouffles()` that only contains data related to souffles.

This ["separation of concerns"](https://en.wikipedia.org/wiki/Separation_of_concerns), with each function focused on just *one task* with *its own self-contained data* is a great way to keep our code organized and easier to debug -- nice and [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) (Don't Repeat Yourself)!

<br/>

## Variable scope and a dream metaphor

Let's take another look at the code from the previous challenge: my dream (the function) about a robot ninja pirate (the variable):

```javascript
function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know ninjitsu!";  
}
console.log(robotNinjaPirate);
```

<br/>

Next, here's another example, building on this dream metaphor. Things that exist in the real world often appear in our dreams! Similarly, variables defined *outside* of a function can also exist *inside* a function:

```javascript
// Just like I exist in real life, this variable exists outside of any functions:
let me = "Liz";

// Defining our function (what the dream will be)
function myDream () {
  console.log(me);
}

// Call our function, which will then run console.log to display the variable named: me
myDream();
```

**Try running the code above in your console.** It works just fine -- again, just like how stuff from real life can seep into our dreams, variables can move from the ***outside-in***, from outside a function to *inside* the function.

<br/>

But as you may have noticed from the previous challenge with the `robotNinjaPirate`, variables ***cannot go from the inside-out***! Local variables are only accessible inside the function in which they were created, just like how imaginary things in your dream world *cannot* affect reality directly!

  > That sounds like the plot of many horror movies, where nightmares become real. Scary! lol.

<br/>

:books: **New vocabulary:** variables that exist *outside* of any function are said to be in the ***global scope***, whereas variables defined *inside* a function are said to be in the ***local scope.*** (We also call them "global variables" or "local variables".)

So why does any of this matter? Let's take a look at another bug before moving forward.

<br/>

## Challenge 2:

There's one small bug in the code below -- you only need to change *one* line of code to fix it. Follow the steps below:

  1. Before running the code, come up with a hypothesis. What do you think will appear in the console?
  2. Test it out and see what happens!
  3. Discuss: What's wrong, and why?
  4. Finally, take a couple guesses as to how you might fix it.

```javascript
function calculateTax(itemPrice) {
  console.log(itemPrice * 0.0725);
}
let initialCost = 20;
let taxAmount = calculateTax(20);
let totalCost = initialCost + taxAmount;
console.log("Total amount due: " + totalCost);
```

**Hint:** Remember that the *only* thing `console.log()` does is display the value of something to the console -- nothing else!

**Another hint:** This is something we haven't specifically talked about in our class yet. But tinker with the code and try some stuff out! Next, we'll take a closer look at what's going on here.

<br/>

## Setting variables free with the `return` statement

In the previous challenge, the function calculates how much tax you might pay for something that costs $20. But that result isn't being sent to the rest of the code, so the next steps don't work correctly!

Since *local variables* are only accessible inside the function in which they're defined, that means they're essentially trapped there!

Take a look at at this other example: 

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

**Try running that code.** It doesn't work either! The `person` is quite literally *trapped* inside the `capture()` function, like being stuck in a parallel universe, for you sci-fi fans. ;) And how do you move from one universe to another?

<br/>

:star: **The `return` statement can release a local variable**, letting it ***out*** -- and that's why we call it the ***output*** of the function!

So that's how we can release our `person` variable from the confines of the `capture()` function, letting it ***out*** of its *local scope*, setting it free to live happily ever after in the wide open *global scope*. (In that sci-fi metaphor, I guess you could think of the `return` statement as sort of a portal or a wormhole that lets the data escape!)

<br/>


## Challenge 3:

Look online for a simple example of how to use the `return` statement, and based on what you find, see if you can fix the previous example so that you'll see the message in the console: `"This is Liz speaking. Help, I'm trapped inside a function!"`

<br/>

## Challenge 4:

And now let's return to that other previous example with calculating the total cost of a purchase. Use what you've learned to solve the bug in the code below:

```javascript
function calculateTax(itemPrice) {
  console.log(itemPrice * 0.0725);
}
let initialCost = 20;
let taxAmount = calculateTax(20);
let totalCost = initialCost + taxAmount;
console.log("Total amount due: " + totalCost);
```

**Hint:** The solution will look *very* similar to how you solved the previous challenge. You only need to add *one line of code*.

<br/>

## Returning back to where you started (dream metaphor)

Back to our silly dream, to recap: ***Reality, the physical universe, is like the global scope.*** Things exist here! They're real! For example: a table, a tree, or you and me:

```javascript
// I exist in the global scope, and in real life!
let me = "Liz";

// Defining our function (what the dream will be)
function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know ninjitsu!";  
}

// Remember, this won't work!
// robotNinjaPirate only exists in our dream; it's a local variable, local to the myDream() function!
console.log(robotNinjaPirate);
```

<br/>

***Recap: how do you release a local variable? Use the `return` statement!*** In our dream metaphor, *returning* an output from your function is like *remembering* something from your dream after you wake up. So in JavaScript, it's like `return` actually *brings back* a piece of the miniature dream world into the real world, so that way you can tell people about your dream!

Let's see this in action:

```javascript
function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know ninjitsu!";
  
  // I'll RETURN this value, so that way I can remember it after waking up:
  return robotNinjaPirate;
}

// Upon waking up, I'll remember part of my dream
// (and in this case I'm saving it to a global variable to store it in the global memory):
let memoryOfMyDream = myDream();

// Now I can tell the world about my dream (at least the part that I remembered):
console.log(memoryOfMyDream);
```

We call it the `return` statement because once that line of code is executed, the computer literally ***returns*** back to where the function was called, and it ***replaces*** the function call with its output.

:star: **See for yourself!** Run the code above in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit) one step at a time, and see the arrows to the left of the code indicating which line of code runs and in what order. You can see how it jumps to the *function definition* after the function is called, and then once it executes the `return` statement, it jumps (or *returns*) back to the line where it was called!

<br/>

You can remember that ***return and replace*** behavior by visualizing it happening in these steps:

  1. Define the `myDream()` function (see function definition in example code above)
  
  2. Call that function (fall asleep and start dreaming!)
  
  3. The computer runs the code inside the function definition for `myDream()`
  
  4. Once it executes the `return` statement, it *releases* whatever value is *to the right* of `return` (this is you waking up from your dream and remembering a small piece of what happened in the dream!)
  
  5. Then the computer *brings back* that value (the part of the dream you remembered), and it *returns* back to the line of code where the function was called (like your brain returning to consciousness, back to real life!)
  
  6. The function call `myDream();` is replaced with its ***output***, whatever was *released*, whatever value was to the right of the `return` keyword.

See the example below for this last step. **Note:** the code below *will not work* if you run it all. This is just a visualization of what's happening in step 6 above:
  
```javascript
function myDream () {
  let robotNinjaPirate = "Arr matey, beep boop, I know ninjitsu!";
  
  // I'll RETURN this value, so that way I can remember it after waking up:
  return robotNinjaPirate;
}

// In step 6 above, the line below changes from this:
let memoryOfMyDream = myDream();

// ...to this:
let memoryOfMyDream = "Arr matey, beep boop, I know ninjitsu!";
```

<br/>


## Challenge 5:

Take a look at the slightly different code below. *Before you run the code*, **discuss**: Which value do you think will appear in the console? 999 or 5?

```javascript
let testNum = 999;
function pointlessFunction() {
  let testNum = 5;
}
pointlessFunction();
console.log(testNum);
```

Then try ***running*** the function defined above. **Discuss:**
- Does running the function change what appears in the console?
- Does it matter *when* you run the function in relation to the code presented above?
- Why or why not?

After you've discussed this a bit, test that code inside [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit) and pay special attention to what happens in the computer's ***memory*** (shown on the right side of the screen).

<br/>

## Challenge 6:

Next, look at another slightly different example. Again, *before you run the code*, **discuss:**
  - What looks different about this code compared to the previous examples?
  - What will appear in the console?

```javascript
let someNum = 999;
function anotherFunction() {
    someNum = 5;
}
anotherFunction();
console.log(someNum);
```

Run the code above (exactly as it's written) in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit), and/or try adding more `console.log()` statements to see what's happening at each step.

Then **discuss**: What's different from the previous example, and why?

<br/>

## Challenge 7:

Take a look at this other variation of the code, and again, *before you run the code*, **discuss:**
  - What looks different about this code compared to the previous example?
  - What will appear in the console?

```javascript
let exampleNum = 999;
function sillyFunction() {
  let exampleNum = 5;
  console.log(exampleNum);
}
sillyFunction();
```

**Discuss:** Why does this work differently compared to the previous examples?


<br/>

## Recap: global versus local variables, `return` versus `console.log()`

Let's recap: there are *two* main types of scope that exist in JavaScript: global and local. Variables can belong to one or the other, *never both!*

  - **Global scope:** Anything created at the top-most level of your code -- *outside of any functions* -- is said to be in the *global scope*. If it's *global*, that means it can be accessed from *anywhere* in your code. We call these ***global variables***.
  
    > One example of a special built-in global variable we've used already is the `document` object. We can access it from *anywhere* in our program because it's a global variable.

  - **Local scope:** Anything created *inside a function* exists ***only*** inside that function -- again, like they're trapped inside! The only way to set ***local variables*** free and pass them into the *global scope* is by using the `return` statement.

<br/>

And here's a recap of our lessons learned about `return` versus `console.log()`:

  - The `console.log()` function only ***displays*** a value in the console; it ***does not save it in memory***. (The computer displays it and then *instantly* forgets what it was!)
  
  - The `return` statement is sort of the opposite: it ***does not display*** the value to the right of it, but it ***does allow you to save it*** outside of the function so you can pass it along to your other code.

<br/>

By ***returning*** a value, we can pass that data from *inside* the function to *outside* the function, so that way the computer can *remember* it even after the function has finished running.

  > **Helpful metaphor:** It's like passing the baton from one person to another in a relay race! :running: 

If you want to *reuse* any data from inside your functions -- for example, chaining functions together to do more complex things -- it's *very* important to use the `return` statement.


<br/>
<hr/>

:trophy: ***Congrats!*** Variable scope and returning outputs from your functions are definitely more advanced topics. So practice, practice, practice! Soon enough, you'll be using functions like a pro to create wonderfully [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and reusable code!
