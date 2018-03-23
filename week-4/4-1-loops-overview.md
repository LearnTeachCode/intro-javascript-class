# 4.1: Intro to loops

Loops are a lazy programmer's best friend; they tell the computer to repeat an action multiple times, so that we don't have to! In this section, we'll review the concept of looping and some examples of creating loops in our code.

❓ **If you have any questions,** please ask on the private Slack channel for our class.

**Table of Contents:**  
  - 4.1.1: The four parts of every loop
  - 4.1.2: Creating a loop with `if` statements
  - 4.1.3: Creating a `while` loop
  - 4.1.4: Bonus material on the GOTO statement and the famous "10 PRINT" maze

<hr/>

## 4.1.1: The four parts of every loop

The video linked below is a slow and detailed walkthrough covering the concept of loops, creating `while` loops and `for` loops (even though we won't be covering `for` loops yet, so that part is meant to be bonus material).

:tv: **Video: Intro to loops (54 min): https://youtu.be/YmyROsrVQWI**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. I'm planning to remake it later on, and I also hope to make a *short* review of loops too!

![Loops save you time!](http://jeffiscool.com/pictures/Foxtrot/foxtrot_blackboard.JPG)

Even if you don't understand the code in the comic pictured above, you might guess that the kid wrote some code that would display "I will not throw paper airplanes in class" 500 times, hoping that he could get out of *actually* writing it 500 times himself! Smart kid. ;) Let's learn how to make computers do our work for us too!

**There are four parts to defining any looping action:**

  1. The starting point

  2. The "keep-going" condition (keep repeating as long as some condition is true)

  3. How to change some data over time so that eventually the "keep going" condition will become false. (Oftentimes, we're just counting up or counting down.)

  4. The body of the loop, the action that should be repeated

Let's walk through an example of **how to program a robot to wash the dishes for us**. We'll start with answering those four questions, identifying the four pieces of information we need to make this loop work as expected. Then we'll test out our logic with some `if` statements before moving on to the code for a proper loop.

**Four parts for telling a robot to wash the dishes:**

  1. Start with a number of `dirtyDishes` (in our example, pretend there are 10 dishes to wash)

  2. Keep going as long as there are still some dirty dishes remaining (if the number of `dirtyDishes` is greater than zero)

  3. Count down the number of dirty dishes, one at a time

  4. On each iteration of the loop, log a message to the console (since we don't have a real robot)

Now we have all the ingredients to implement this in our code!

## 4.1.2: Creating a loop with `if` statements

To illustrate how loops work and check our understanding, it's helpful to first do loops the *wrong* way by starting with an `if` statement to test the logic and then copy-pasting the code to create a loop. Again, this is not how you should do it in real-world projects! This is just for the sake of learning, like training wheels.

Let's continue with our dish-washing robot exampmle from above.

**Example code with just one `if` statement first:**

```javascript
// 1. Starting point:
let dirtyDishes = 10;

// 2. Keep-going condition:
if (dirtyDishes > 0) {
  // 3. Changing the data over time (here we count down by 1 each time):
  dirtyDishes--;

  // 4. Body of the loop, action to repeat:
  console.log("Dirty dishes remaining: " + dirtyDishes);  
}
```

That code is just enough to test our logic and perform *one* iteration of the loop. So the code will only run one time, and then it'll stop. (That's how `if` statements work; they don't repeat any actions on their own.)

  > **Quick reminder:** In the code above, we're using the **decrement operator** as a shortcut. Remember that `dirtyDishes--;` is the same as `dirtydishes = dirtyDishes - 1;`. You can review all the [arithmetic operators on MDN's reference page here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators).

Next, let's copy-paste our code to make it repeat multiple times!

**Looping with multiple `if` statements:**

```javascript
// 1. Starting point <-- ONLY DO THIS ONE TIME!
let dirtyDishes = 10;

// TO REPEAT, COPY-PASTE THE CODE BETWEEN HERE .............
// 2. Keep-going condition:
if (dirtyDishes > 0) {
  // 3. Changing the data over time (here we count down by 1 each time):
  dirtyDishes--;

  // 4. Body of the loop, action to repeat:
  console.log("Dirty dishes remaining: " + dirtyDishes);  
}
// ............................................... AND HERE!

// TO REPEAT, COPY-PASTE THE CODE BETWEEN HERE .............
// 2. Keep-going condition:
if (dirtyDishes > 0) {
  // 3. Changing the data over time (here we count down by 1 each time):
  dirtyDishes--;

  // 4. Body of the loop, action to repeat:
  console.log("Dirty dishes remaining: " + dirtyDishes);  
}
// ............................................... AND HERE!

// ...copy-paste it more than 10 times!
```

To definitively test that your looping logic is correct, you can copy-paste that code (parts 2, 3, and 4 of the loop) a bunch of times and see how it works. To save time, remember that you can also change the starting point and the keep-going condition to a smaller number! (Don't forget to change the number in *both* places to make it work correctly!)

If you copy-paste that the code *more than 10 times*, no more messages will appear in the console. That's because *as soon as the keep-going condition becomes false (as soon as `dirtyDishes` is no longer greater than zero), the computer will look at those `if` statements and ignore them when their conditions are false.

Next, let's create an actual `while` loop so we don't have to do the repetitive work of copy-pasting those `if` statements!

## 4.1.3: Creating a `while` loop

Our code from the previous section works just fine, but it completely defeats the purpose of having a computer or a robot in the first place! What good is a computer if we still need to repeat ourselves? 

  > Remember, you always want your code to be [***DRY: Don't Repeat Yourself!***](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) The opposite is WET code: "write everything twice", "we enjoy typing" or "waste everyone's time." :laughing:

To turn an `if` statement into an actual `while` loop, as long as you have all those parts working in your code, then all you need to do is... 

**Replace the keyword `if` with the word `while`!**

```javascript
// 1. Starting point:
let dirtyDishes = 10;

// 2. Keep-going condition:
while (dirtyDishes > 0) {
  // 3. Changing the data over time (here we count down by 1 each time):
  dirtyDishes--;

  // 4. Body of the loop, action to repeat:
  console.log("Dirty dishes remaining: " + dirtyDishes);  
}
```

Try it out! So that's the exact same code as our first example, but now it loops on its own, without us copy-pasting to make it repeat manually. Phew! That's so much nicer. This is what computers are meant for.

:bulb: **Pro tip: Practice and test out your loops using [PythonTutor.com](http://pythontutor.com/javascript.html#mode=edit)** instead of directly in your own JavaScript file or your browser's console. Why? Because if you make a mistake, you could accidentally create an infinite loop that would crash your browser! (And it’s annoying to have to restart everything.) PythonTutor will **prevent** infinite loops; it refuses to run your code if it's infinite, and it lets you know with a red error message on their website when you try to visualize the code.

  > Be sure to review the [debugging tips and tools in **section 2.1**](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-1-debugging.md) for more tips like this!

**Important points to remember about loops:**

  - So remember, `while` loops have the same exact pattern as `if` statements: a condition goes inside the parentheses `( )`, and the resulting action (which happens only if the condition is true) goes inside the curly brackets `{ }`.

  - The only difference between `while` loops and `if` statements is that a `while` loop does those actions over and over again until the condition in the parentheses is no longer true, whereas an `if` statement does its actions just *one time*.

  - There's another type of loop called a `for` loop, which is just a shortened syntax. Anything you can do with a `while` loop, you can also do with a `for` loop, and vice versa! (I recommend just sticking with `while` loops until you're really comfortable with loops.)

## 4.1.4: Bonus material on the GOTO statement and the famous "10 PRINT" maze

In class and in the long review video covering loops (https://youtu.be/YmyROsrVQWI), we started by taking a look at one of the most famous lines of code, called "10 PRINT" for short. It's a single line of code (written in an old language called [BASIC](https://en.wikipedia.org/wiki/BASIC)) that creates an infinite loop, generating a maze on the screen by randomly displaying forward slashes or backslashes!

:tv: **Watch the video demonstrating the famous "10 PRINT" code that creates a maze: https://www.youtube.com/watch?v=Ov0baPrRNkc**

**Some bonus links and tidbits:** 

  - That line of code is *so* famous, a group of academics wrote an entire book on *just* that line of code! You can read the whole book for free online at [10Print.org](https://10print.org/).

  - In the early days of computing, programmers had to manually assign line numbers to each line of their code.

  - The [GOTO statement](https://en.wikipedia.org/wiki/Goto) is an old programming instruction that tells the computer to jump from one line of code to another. (So in the example code that creates the maze, "GOTO 10" says "next, go to line 10". And since that line of code *already is on line 10*, that creates an infinite loop!)

  - Infinite loops like this are very similar to that joke about how to trap a robot in the shower forever: just tell it to follow the instructions on the shampoo bottle, which say "Wash, rince, repeat"!

Anyway, **now you know how to make computers do repetitive work so that you don't have to!** We will definitely return to loops many times throughout our class. Hopefully you're not feeling too loopy after reading all of that. ;) This takes a lot of practice to get comfortable with, so practice, practice, practice! (Just like a loop! But practicing is one thing a computer *can't* do for you. At least not yet.)
