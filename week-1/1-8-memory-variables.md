# Section 1.8: Intro to variables and storing data in memory

We've now learned about a couple different *types* of data, and we've learned how to *display* the data, either on the web page or in the browser's console. But that can only get us so far!

In this section, we'll dig into the guts of the computer and use its *memory* to enable us to do more complex things in our application.

<hr/>

## Review and group discussion:

Reflecting on what we've learned so far, let's discuss:

  1. Where have we been sending our data so far?
  
  2. What's one big limitation of how we've been working with data so far, and why?
  
  3. How would you define what the computer's *memory* actually is, in one plain-English sentence (no tech jargon)?

<br/>

## Challenge 1:

⭐️ Once again, make sure to **open your personal copy of our HTML mockup on Glitch**, or if you lost track of the link, feel free to [**click here and make another remix of it**](https://glitch.com/edit/#!/dragon-defeater-v0-starter).

<br/>

Take a look at the following code, and first make a prediction: what do you think you'll see in the console? What do you think this code is doing?

```javascript
let myNerdyJoke = "Debugging is like being the detective...";
console.log(myNerdyJoke);
```

<br/>

After discussing your ideas, then test it out and see if you were right!


<br/>

## Challenge 2:

A message should appear in the browser console, but the code is broken! Make a guess as to what you think went wrong, and then test it and fix it up:

```javascript
lot veryTrue = "Using a program: frustrating for a day. Learning to program: frustrating for a lifetime!";
console.log(veryTrueStatement);
```
<br/>

## Challenge 3: 

I found a great joke [from the creator of Stack Overflow](https://twitter.com/codinghorror/status/506010907021828096), but the code below isn't showing the joke in the console like it's supposed to!

Make a prediction about why it's broken, and then test it and see if you can fix it:

```javascript
let anotherJoke = "There are three hard things in coding: naming things, and off-by-one errors."
console.log("anotherJoke");
```

<br/>

## Challenge 4: 

Take a look at the code below. What do you think it'll show in the console, and why?

After discussing your ideas, run the code to see what happens:

```javascript
let nerdJoke = "Debugging is like being the detective...";
let nerdJoke = "...in a crime novel where you're ALSO the murderer!";
console.log(nerdJoke);
```

We'll discuss how to fix this bug soon enough!

<br/>

## Storing data in the computer's memory

In all of the above examples, we're telling the computer to ***remember*** a piece of information. A more techie way to say that is: *we're storing data in memory.*

<br/>

***You can visualize the computer's memory as a spreadsheet with two columns: name and value.***

| name | value |
|------|-------|
| `myNerdyJoke` | `"Debugging is like being the detective..."` |
| `anotherJoke` | `"There are three hard things in coding: naming things, and off-by-one errors."` |

Once the data is stored in memory, this opens up some very useful new possibilities:

  1. We can ***access*** the data later on, at any time in our program!
  
  2. We now have a much ***shorter name*** for the data, so we don't have to do as much typing if we need to reuse it.
  
  3. We can ***change*** the data over time!

<br/>

That last point -- being able to change a piece of data over time -- is especially important, both for our Dragon Defeater game and for just about *every* software application ever invented! That's why we give these stored pieces of data a special name: *variables*!

<br/>

:star: **A *variable* is a *changeable* piece of data that's stored in memory in a location that's labelled with a symbolic *name*.**

You can think of a variable as a ***labelled container***. Its contents can change, but the label should (ideally) always describe what it contains.

![labelboxes](https://user-images.githubusercontent.com/1555022/42399563-22b0d460-8123-11e8-9b23-4e8359eae398.jpg)


<br/>

Next, let's practice visualizing how code affects what's stored in the computer's memory.

<br/>

## Challenge 5:

:pencil: For the next challenges, we'll be using pen and paper! (We really do learn better when we explore ideas in different ways. It's good to get away from the keyboard for a bit!)

<br/>

When we first start our program, imagine the computer's memory as a spreadsheet with headings but no rows:

| name    | value |
|------|-------|

On your piece of paper, draw the headings and leave plenty of space below them -- you'll be drawing rows as you mentally execute each line of example code provided below. (Our brains are the best computers, after all!)

<br/>

For each line of example code below, ***add onto or modify your drawing*** to show how the memory would look after executing the code:

```javascript
// Example 1:
let x = 5;
```

```javascript
// Example 2:
let y = 7;
```

```javascript
// Example 3:
let z = 5 + 7;
```

```javascript
// Example 4:
let myName;
```

```javascript
// Example 5:
let sum = x + y;
```

```javascript
// Example 6:
let greeting = "Hello";
```

<br/>

Next, open up [**Python Tutor's online code visualization tool**](http://pythontutor.com/javascript.html#mode=edit), make sure it says "Write code in JavaScript" at the top, and then paste in all of the above code examples into the text box.

Then click the **"Visualize execution"** button and you'll see a new screen.

In that new screen, click the **"Forward"** button to see what the code does, one line at a time. The computer's memory will be visualized on the right side in a blue/grey box.

  > **Note:** Python Tutor used to only run Python, hence the name. But now it also runs JavaScript, C++, Ruby, and Java! It's a great free tool for visualizing your code step-by-step.

<br/>

**Discuss:**

  1. How accurate was your drawing? What did you get right or wrong?
  
  2. Based on our experiments so far, how would you explain what the `let` keyword does in one simple sentence?


<br/>

## Challenge 6:

Take a look at the computer memory drawing below, and then ***write the code*** that, once executed, would make the state of the memory look like this:

| name    | value |
|------|-------|
| `favFood` | `undefined` |
| `favColor` | `undefined` |

<br/>

Then [**open Python Tutor**](http://pythontutor.com/javascript.html#mode=edit) again and run your code to see if the computer's memory looks like the drawing above. 

<br/>

## Challenge 7:

For this one, write your code ***three different ways*** that would *all* make the state of the memory look like this:

| name    | value |
|------|-------|
| `numOranges` | `4` |
| `orangePrice` | `1.5` |
| `totalPrice` | `6` |

<br/>

Test each of your three answers in [**Python Tutor**](http://pythontutor.com/javascript.html#mode=edit) to see if they all make the computer's memory look like the drawing above.

  > There's *always* more than one way to accomplish any goal -- in code, as in life! ;)

<br/>

## Challenge 8:

Take a look at the computer memory drawing below, and then look at the example code below that. 

**Initial state of the memory:**

| name    | value |
|------|-------|
| `favFood` | `undefined` |
| `favColor` | `"green"` |

**Code that will run:**

```javascript
favFood = "cupcakes";
favColor = "blue";
```

**Make a predication:** what do you think the memory will look like *after* the line of code executes? Why?

<br/>

After discussing your ideas, [**review the answer in Python Tutor here**](https://goo.gl/p7iusC).

<br/>

## Creating new locations in memory with the `let` keyword

As we've learned by experimenting so far, the `let` keyword tells the computer to ***create a new slot in memory*** -- like *adding a new row to our spreadsheet!*

<br/>

We can ***initialize*** a variable with or without a value. That's why `let x = 3;` works, but `let x;` by itself also works. If a variable is empty, the computer represents its empty value with the special data typed `undefined`.

When data is stored in memory, it's always stored in pairs -- a *name* and a *value*.

<br/>

:star: **Remember: the `let` keyword creates *new* name-value pairs**, just like adding new labelled storage boxes to your shelf, or adding new rows to a spreadsheet. 

<br/>

## Challenge 9:

Take a look at the code below, and discuss:

  1. Will it work? If so, what will it do? Or if not, what error message do you think you'll see?
  
  2. Why or why not?
  
  3. What is the code below trying to accomplish? What is its purpose?

```javascript
let x = 3;
x + 2 = 5;
```

After discussing your ideas, test your code either inside your Glitch project, or inside [**Python Tutor**](http://pythontutor.com/javascript.html#mode=edit). What happened, and why?

<br/>

## Challenge 10:

What's the difference between each line of code below? What is the data? Where is it being sent to?

```javascript
document.body.textContent = "Hi";

console.log("Hi");

let phrase = "Hi";
```

<br/>

## Challenge 11:

Take a look at the example code below, and discuss:

  1. Will there be an error message, and if so, what do you think it'll say?
  
  2. What will the computer's memory look like after this code executes?

```javascript
let fruit = "apple";

fruit = fruit;
```

<br/>

After discussing, test the code inside [**Python Tutor**](http://pythontutor.com/javascript.html#mode=edit) to see if you're right!

<br/>

## Using the assignment operator (`=`) to modify data

As you probably noticed, the equal sign (`=`) works differently with code than it does with math equations!

In math class, we use this sign to show that both sides of the equation are *equal* to each other -- that they're balanced, like a scale:

![balance-equation](https://user-images.githubusercontent.com/1555022/42401930-d74d2db6-812c-11e8-8235-a6eb3584ce2b.gif)

So we can say that `4 + 1 = 5` and we can say that `5 = 4 + 1`. The order doesn't matter wiht an equation, because both sides are balanced.

We can also write an equation like `x + 2 = 5` (which is the same as `5 = x + 2`), and we can *solve* the equation -- the answer must be `3`!

<br/>

:star: **But in programming languages, the equal sign (`=`) is *NOT* for equations. It *assigns* the value on the right *into* the variable name on the left.** That's why we call it the *assignment operator*.

<br/>

When we're writing code, the order ***does*** matter! Here's what happens when the computer runs the line of code `let x = 2 + 3;`:

  1. The computer reads the ***right side first***. In this case, it sees `2 + 3` first.

<br/>

  2. Then it ***evaluates*** whatever's on the right side of the assignment operator (the `=`), turning it into a ***single value***. In this case, it converts `2 + 3` into `5`. So the code is effectively turned into `let x = 5;`.

<br/>

  3. Finally, it ***assigns*** that value into the memory slot for the variable name on the left.
  
     - If the `let` keyword is used (`let x = 2 + 3.`), the computer creates a ***new*** memory slot with the label `x`, and then assigns it the value (which is `5` in this case).
     
     - Or if not, as in `x = 2 + 3;`, then it will insert the value (`5`) into the *pre-existing* memory slot labelled `x`.
  
<br/>

So the left side of the assignment operator (`=`) can *only* be the name of a variable, like `x` or `document.body.textContent`. And the right side can be *any* combination of variable names or values.


<br/>


## Challenge 12:

Our Dragon Defeater game needs to keep track of how many dragons have been defeated -- this is our variable that changes over time! Let's imagine we'll save it in memory like this, so that the initial value will be 0:

```javascript
let dragonsDefeated = 0;
```

How could we write one additional line of code to change this variable, so that its *new* value will become the **sum of its previous value plus one**?

<br/>

  > **Hint:** This problem is very tricky for most first-time programmers who haven't already seen this type of code before. Keep in mind the ***order*** in which the computer reads our code when we use the assignment operator.
  
<br/>

**To test your code:** Paste the provided line of code in [**Python Tutor**](http://pythontutor.com/javascript.html#mode=edit) and then paste *several copies* of the line of code you wrote as your answer. Run it in Python Tutor, and if it's correct, you should see the value of the `dragonsDefeated`variable continue to count up every time you run that same line of code!

<br/>

**Example:**

```javascript
// This line initializes our variable. It should only run ONCE:
let dragonsDefeated = 0;

// If you solution was this:
dragonsDefeated = 1;

// Then you should paste several copies of that solution like this:
dragonsDefeated = 1;
dragonsDefeated = 1;
dragonsDefeated = 1;
dragonsDefeated = 1;
dragonsDefeated = 1;
dragonsDefeated = 1;

// ... This is NOT the answer, of course!
```

<br/>

## Bonus challenge:

Similar to the previous challenge, complete this unfinished code to add the string `" and again"` to the end of the variable named `neverEndingSentence`, and then *copy-paste* that line of code to repeat it 10 more times!

```javascript
let theCoderLife = "Debug it again"; // Don't modify this line of code!

// Write a line of code here (between the others) to solve this challenge:

// ...and then copy-paste that line of code 10 more times here to make the string longer and longer
```

The sentence should turn into something like `"Debug it again and again and again and again"`, getting longer each time.


<br/>

<hr/>

:trophy: ***Congrats!*** Understanding how to manipulate information in the computer's memory will help you with *any* programming language you learn in the future.

:point_right: **Next up: in [section 1.9, we'll put everything together to build our Dragon Defeater game](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-1/1-9-putting-it-together.md)!**
