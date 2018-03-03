# 1.4: Practice challenges: Conditional statements and comparison operators

Conditional statements (also called `if` statements or `if/else` statements) are the commands that allow us to tell computers to make a decision based on some given information. Any time we have questions or decision points in our app's flow chart, we'll need to use conditional statements in our code. Let's learn with some more practice challenges!

**Again, you can run your code in several different ways:**

  1. Use [Python Tutor](http://pythontutor.com/javascript.html#mode=edit) to visualize your code step-by-step (no access to HTML or CSS though, only simple JavaScript that can run on its own)
  
  2. Run your code directly inside your web browser's JavaScript console (see [section 1.1.4 for a review](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#114-intro-to-chromes-developer-tools-and-the-browser-console))
  
  3. Use a [Glitch](https://glitch.com/) project to test your code with HTML, CSS, and JavaScript files all within your web browser (see [section 1.1.3 for a review](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#113-intro-to-glitch))
  
  4. Create everything locally on your computer with Visual Studio Code or any text editor that you prefer (see [section 1.1.5 and 1.1.6 for a review of VS Code](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#115-intro-to-text-editors-visual-studio-code))

  > All the tools listed above have their pros and cons. Try them all and see what you like best!

<hr/>

## Challenge 1:

So far we've tinkered with two types of data: ***strings*** (like `"hello"`) and ***numbers*** (like `42`). There's another data type that's equally important -- in fact, it's the foundation of *all of computer science!*

Meet the ***Booleans***: this special data type can only have a value of either `true` or `false`. Booleans go hand-in-hand with ***comparison operators*** -- remember the "less than", "greater than", or "equal to" symbols from math class? That's how we write ***conditions*** in all programming languages: by *comparing* one value to another.

The result of a condition is always a Boolean value: `true` or `false`. In other words, *computers can only answer "yes or no" questions!*

  > **Fun fact:** Booleans are named after "Boolean algebra" (an area of mathematics where variables can only be `true` or `false`), which was named after this awesome guy [George Boole](https://en.wikipedia.org/wiki/George_Boole). Way back in the 1800s, he came up with some of the theories in math and logic that laid the foundation for the information age!

:trophy: **Your challenge:** *Before* you run any of the code below, take a look at it and discuss whether each line of code will show `true` or `false` in the browser console. Then run the code to see if you guessed correctly!

```javascript
// Just like we can put strings or numbers directly into the console.log(),
// we can put COMPARISONS (also called CONDITIONS) right in there too:

// For each of the below, guess if it will show true or false!
console.log(2 === 2);
console.log(5 > 0);
console.log("pizza" === "salad");
console.log(-17 > 4);
console.log(9 < 8);
```

## Challenge 2:

Run the following code to see what happens, and then ***break it five different ways***. Be sure to save your code, so you can share it with us afterwards!

  > Remember you can "comment out" code to save it in your file without running it. The `Ctrl + /` or `Cmd + /` keyboard shortcut is super nifty!

```javascript
console.log("******* #1: BEGIN if statement *******");
// Modify the code below to break it 5 different ways:
if (true) {
    console.log("This condition is true!");
}
// Don't modify the console.log() statements though
console.log("******* #1 END of if statement *******");
```

**Discuss:**

  1. Which parts of the code can you change without causing any errors?
  
  2. What do you think the parentheses `()` mean here?
  
  3. And what do you think the curly brackets `{}` mean here? Why do we need them?
  
  4. Why is the code inside the `if` statement indented further over to the right?
  
  5. Would it still work if all the code was written on *one long line* instead of on multiple lines?

<br/>


## Challenge 3:

Copy the code snippet from the previous challenge, and modify it so that the condition is ***not true*** -- so that way, the conditional statement *won't* run the code inside of it! Try making the condition *not true* in these three different ways:

  1. Checking if one number is greater than another
  2. Comparing a string to another string
  3. Using only a Boolean value with *no* comparison operators
  4. Comparing one Boolean value versus another Boolean value
  
**Bonus questions to discuss:**

  1. What happens if you compare a string to a number?
  2. Or a string to a Boolean?
  3. Or a number to a Boolean?

<br/>


## Challenge 4:

Google challenge! Look up how to write an `if/else` statement, and then create your own example code snippets based on the example provided in challenge #2 to show **two examples**: one where the condition is true, and one where the condition is false.

Both examples should make a message appear in the browser console. (And nothing else! Don't get too fancy just yet.)

<br/>


## Challenge 5:

Fix the code snippet below to make the console show the message `"Wear a sweater!"`:

```javascript
let temperature = 65;

if (temperature) {
    console.log("Wear a t-shirt!");
} else if (temperature > 65) {
    console.log("Wear a sweater!");
} else {
    console.log("Wear a jacket!");
}
```

**Discuss:**

  1. Can the code written above ever display *more than one* message in the console? Why or why not?
  
  2. How would you rewrite the code above using nothing but `if` and `else` statements, without any `else if`s? Is that possible?
  
  3. Can you have more than one `else if` statement? Is there a limit to how many you can use in the same group of conditional statements? 

<br/>


## Challenge 6:

**Discuss:** What decisions do we need to make for our Hangman game to work? How can you break up that logic into questions a computer can answer based on the variables for the `correctAnswer`, the `userInput`, and the `guessesRemaining`?

Then **write the code** for those conditional statements with some fake values for the three variables needed for the game!

  > Again, be sure to ***save your code*** to share it with us. :)

<br/>


## Challenge 7:

**Discuss:** What decisions need to be made in your own project idea, if any? How might you break it down into questions a computer can answer?

  > Write down your answers in your notes -- this is a step in your project planning process!

<br/>


## Bonus challenge 1:

Google challenge! Look up the other comparison operators and find out how to check if two values are ***not*** equal.

<br/>

## Bonus challenge 2:

Another Google challenge: do some research and experimentation to find out what the difference is between JavaScript's ***strict*** type of comparison versus the ***lazy*** type of comparison.

Write down what you find, and code that you tested, a description of how it works *in your own words* -- and be sure to *cite your sources*.

<hr/>

:trophy: ***Great job!*** Be sure to [review all the material for week 1](https://github.com/LearnTeachCode/intro-javascript-class/tree/march-2018/week-1), including background info about debugging and some videos reviewing the concepts we practiced in class today, and [start on the homework for week 1](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-7-homework.md) if you have time to. :)
