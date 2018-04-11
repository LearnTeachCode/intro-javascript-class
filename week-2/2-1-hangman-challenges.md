# 2.1: Hangman game challenges


In [week 1](https://github.com/LearnTeachCode/intro-javascript-class/tree/march-2018/week-1) we started learning about variables, data types, DOM elements, and conditional statements. (That was a lot, wasn't it?!) As a warm-up challenge to review all of that -- and to learn some *new* tricks too -- let's start writing the code for our super minimal one-letter Hangman game!

  > Our goal will be to finish the game by the end of class today, after we learn a bit about functions and event listeners. :)

:books: **Resources:**
  - [All of the week 1 materials](https://github.com/LearnTeachCode/intro-javascript-class/tree/march-2018/week-1)
  - [JavaScript Cheat Sheet](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/JavaScript%20Reference%20Sheet%201.pdf)
  - [Flowcharts for our Hangman game](https://github.com/LearnTeachCode/hangman-game) (scroll down to see the images)
  - And/or feel free to watch the [flowcharting videos in section 1.5.1](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md#151-flowcharting-our-hangman-game)

<hr/>

## Challenge 1:

:star: **Take a look at [our finished Hangman game](https://hangman-v0-final.glitch.me) for all the following challenges.**

Identify each DOM element (pieces of the web page/the HTML code) that will need to be accessed or modified by JavaScript. How many DOM elements do we need to worry about for this Hangman game?

  > **Review:** A DOM element (DOM as in the Document Object Model) is the term often used to refer each part of a web page. Each HTML tag is a DOM element -- each paragraph, image, link, etc. <br/><br/>
  The DOM is how the web browser sees the web page (as a ***heirarchy*** of objects inside other objects), and that's also how the web page elements are represented in JavaScript code.
  
 <br/>

## Challenge 2:

Remix this blank hangman game: [https://glitch.com/edit/#!/hangman-v0-blank](https://glitch.com/edit/#!/hangman-v0-blank)

Look in the HTML file in your copy of the Glitch project and identify the `id` attribute of each of those elements you identified in the previous challenge.

Did you find them all? :) Did they match up with what you came up with for the previous challenge?

<br/>

## Challenge 3:

Using your browser console (remember to open it while on the *live web page* for the game), use JavaScript to test out how you would access each of those three DOM elements that you identified.

**Some tips:**

  - Remember, you'll need to use that handy `document.getElementById()` function here!
  
  - Feel free to reference the [JavaScript Cheat Sheet](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/JavaScript%20Reference%20Sheet%201.pdf) -- see the sections on creating variables and turning HTML elements into JavaScript variables!
  
  - Be sure to give your variables *descriptive* names and use camelCase format (example: `hereIsACamelCaseVariableName`)


**Bonus:** How would you create three *variables*, one for each of those DOM elements?

  > That way you can essentially give them shorter names, instead of typing that whole long line of code every time you want to reference one of those DOM elements. Very handy! (Remember, lazy programmers are the *best* programmers; do as little typing as possible!)

<br/>

## Challenge 4:

Identify the three pieces of information that control how the Hangman game works. What data type do you think we should use for each of them?

These three variables encompass what we call the ***state*** of the application; in other words, the state of the Hangman game at any given moment depends on these three variables, and the game won't work unless our code keeps track of all three!

  > Silly metaphor: This is just like how a person's *emotional state* at any given moment depends based on variables like how much sleep they got the night before, their blood sugar levels, whether or not somebody cut them off on the freeway that morning, etc. (But code is a million times simpler than humans are!)

<br/>

## Challenge 5:

Next, write the conditional logic (using the three variables fake/placeholder data) for our Hangman game to specify the entire decision-making process that makes our game work! Be sure to test your code to check that it works for every situation that can happen in the game.

In addition to using the flowcharts for our game and any other review materials, below is an example set of conditional statements with fake/placeholder data for you to reference:
 
  - You can open the sample code in PythonTutor here: https://goo.gl/i2LTuS
  - Or you can test the code in your browser console. The code is included below:

```javascript
// Example code:
// Imagine this is part of the code for a game,
// and the user just "leveled up". We need to decide
// what bonus item to give them as a reward:

// Our fake data to test our game logic below:
//    *** CHANGE THIS VALUE to test the logic!
let newplayerLevel = 7;

// If player just became level 9 or higher:
if (newplayerLevel >= 9) {
  
  console.log("Here we would give the player a magical sword");

} else if (newplayerLevel >= 7) {
  
  // Otherwise, if player just became level 7 or higher:
  console.log("Here we'd give the player a golden necklace");

} else if (newplayerLevel >= 3) {
  
  // Otherwise, if player just became level 3 or higher:
  console.log("Here we'd give the player a silver arrow");
  
} else {
  
  // Otherwise, for any other case:
  console.log("Here we'd give the player a loaf of bread");
  
}
```

<br/>

## Challenge 6:

Find out how to use JavaScript to access the user's input (whatever they type into the text box on the web page). 

  > **Hint:** you'll need to look up something **new** that we haven't learned in our class yet! Take a look through [our JavaScript Cheat Sheet](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/JavaScript%20Reference%20Sheet%201.pdf) for pointers.
  
**How to test if you got this right:** 

  1. Open the live web page for our Hangman game.
  2. Then open your browser console.
  3. Type something into the text box (as if you're playing the game)
  4. Run your code *directly in the console* to access the user's input.
  5. Remember to use the `console.log()` function to display the value of any variables you created!

<br/>

## Challenge 7:

In our Hangman game, we need to count down the number of guesses that the player has remaining. Figure out how to count down with JavaScript code! Test this out in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit) or directly in your browser console.

  > **Hint:** You'll need to store the number in a variable, and you'll need to *update that same variable* to change its value so it can count down. You should have ***one*** line of code that accomplishes this, and if you run that *same* line of code multiple times, it should count down as expected!

<br/>

<hr/>

🏆 ***Great job!*** **Next up:** we'll learn about functions and event listeners to let our JavaScript code respond to user interactions!
