# Section 2.6: Putting it all together to build Hangman!

With our new conditional-logic superpowers, we can build applications that *make decisions* based on all sorts of data! Let's take one small step up from last week's Dragon Defeater game and do something just a *little* bit more complex: the classic [Hangman game](https://en.wikipedia.org/wiki/Hangman_(game))!

But as with any project, we'll start by making something *as simple and minimal* as we possibly can. What's the simplest and most important feature of Hangman? You make a guess and find out if you're right or wrong! So for now, that's all we'll create: you can guess a single-letter word.

 <hr/>

## Challenge 1:

:star: **Take a look at [our finished Hangman game](https://hangman-v0-final.glitch.me) for all the following challenges.**

  > Just promise you won't cheat and look at the code yet! ;)

<br/>

**We'll discuss:**

  - What are some limitations of the game?
  - What programming concepts will we need to use in order to build this game from scratch?
  - Is there anything involved in this game that we haven't learned how to do yet? If so, what?
<br/>

## Challenge 2:

Identify each DOM element (pieces of the web page/the HTML code) that will need to be accessed or modified by JavaScript. How many DOM elements do we need to worry about for this Hangman game?

<br/>

## Challenge 3:

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/c88e45bc-1c83-4791-afc8-aa37cfeca162)!

<br/>

Let's look in the HTML file and identify the `id` attribute of each of those elements that we identified in the previous challenge.

Did you find them all? :) Did they match up with what you came up with for the previous challenge?

<br/>

## Challenge 3:

Using your browser console (remember to open it while on the *live web page* for the game), use JavaScript to test out how you would access each of those DOM elements that you identified, to make sure your JavaScript code works before we continue with writing more of the code.

<br/>

**Bonus:** How would you create three *variables*, one for each of those DOM elements?

  > That way you can essentially give them shorter names, instead of typing that whole long line of code every time you want to reference one of those DOM elements. Very handy! (Remember, lazy programmers are the *best* programmers; do as little typing as possible!)

<br/>

## Challenge 4:

Let's identify the three pieces of information that control how the Hangman game works. What data type do you think we should use for each of them?

<br/>

These three variables encompass what we call the ***state*** of the application; in other words, the state of the Hangman game at any given moment depends on these three variables, and the game won't work unless our code keeps track of all three!

<br/>

## Challenge 5:

Next, let's write the conditional logic for our Hangman game to specify the entire decision-making process that makes our game work! Be sure to test your code to check that it works for every situation that can happen in the game.

<br/>

Below is an example set of conditional statements with fake/placeholder data for you to reference:
 
```javascript
// Example code:
// Imagine this is part of the code for a game, and the user just "leveled up".
// We need to decide what bonus item to give them as a reward.

// Our fake data to test our game logic below:
//    *** CHANGE THIS VALUE to test the logic! ***
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

  > **Hint:** you'll need to look up something **new** that we haven't learned in our class yet!
  
**How to test if you got this right:** Open the live page for our game, type something into the text box, and then open the browser console while you're on that page. Run your code in the console -- something like `console.log(document.body.textContent)` -- but of course that isn't the answer. If it works, you'll see the text that hte user typed (and *only* that text) appear in the console.

<br/>

## Challenge 7:

In our Hangman game, we need to count down the number of guesses that the player has remaining. When should we do this? Let's get this part working!


<br/>
<hr/>

:trophy: **We did it!** It's definitely not a finished product, but we made use of *every* programming concept that we've learned so far. You already have enough pieces to build this into a much better game, if you'd like some bonus homework! ;)

:point_right: **In our next class**, we'll dig into some more fun and powerful topics like drawing and animation with p5js, loops, and modeling data with objects and arrays!
