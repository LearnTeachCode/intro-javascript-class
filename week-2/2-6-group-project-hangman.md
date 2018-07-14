# Section 2.6: Putting it all together to build Hangman!

With our new conditional-logic superpowers, we can build applications that *make decisions* based on all sorts of data! Let's take one small step up from last week's Dragon Defeater game and do something just a *little* bit more complex: the classic [Hangman game](https://en.wikipedia.org/wiki/Hangman_(game))!

But as with any project, we'll start by making something *as simple and minimal* as we possibly can. What's the simplest and most important feature of Hangman? You make a guess and find out if you're right or wrong! So for now, that's all we'll create: you can guess a single-letter word.

 <hr/>

## What are we building?

:star: **Take a look at [our finished Hangman game](https://hangman-v0-final.glitch.me) for all the following challenges.**

  > Just promise you won't cheat and look at the code yet! ;)

<br/>

**High-level overview:**

  1. What are the features of this game?
  
  2. What are some limitations of the game?
  
  3. What programming concepts will we need to use in order to build this game from scratch?
  
  4. Is there anything involved in this game that we haven't learned how to do yet? If so, what?

<br/>

## Challenge 1:

:hourglass_flowing_sand: Get out your pencils and paper! Let's draw ***two versions*** of a flowchart to visualize how this game works.

<br/>

**First:** In *two minutes or less*, draw a quick flowchart from the ***user's perspective***: what steps would the user take in order to use this app? How would they experience it?

<br/>

**Second:** In a few more minutes, draw a second flowchart, this time from your perspective as a *developer*, including all the implementation details -- in other words, from the ***computer's perspective***. Be as detailed as possible.

<br/>

## Take a look at our HTML mockup

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/c88e45bc-1c83-4791-afc8-aa37cfeca162)!

We'll be writing code here together as a group!

<br/>


## Challenge 2:

What information does the computer need to remember for this game to work, and what data type should we use for each piece of information?
 
 <br/>
 
  > **Side note:** As we briefly discussed in our previous class, we call this [the ***state*** of the program](https://en.wikipedia.org/wiki/State_(computer_science)). The *state* refers to the information stored by the computer to remember past actions. The *state* combined with any *inputs* determine what the computer program will do next.

<br/>

## Challenge 3:

Let's take a closer look at the user interface, and how our JavaScript code will interact with it:

  1. How many **HTML elements** (parts of the web page like a button or paragraph) will our JavaScript code need to interact with?
  
  2. What do we need to *access* or *change* for each of these elements?
  
  3. What are the `id` attributes of each of these elements that we'll need to access wiht our JavaScript code?


<br/>

## Challenge 4:

What **external events** (outside the control of your code) will affect the state of this system? Let's answer those three important questions that we need to think about for *every* event listener:

  1. Where is the event happening?

  2. Which event are we listening for?

  3. What should happen when the event occurs?


<br/>

## Challenge 5:

Next, let's write the conditional logic for our Hangman game -- the entire decision-making process that makes our game work!

An easy way to test this in isolation from the rest of our code is to use ***fake / example data*** and test the logic on its own; this way, we don't need to type in the text box and click the button over and over again. This also makes it easier for us to isolate any bugs that come up.

<br/>

Below is an example set of conditional statements with fake/placeholder, as an example of what we'll be doing:
 
```javascript
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

}
```

<br/>

## Challenge 6:

Let's find out how to use JavaScript to access the user's input (whatever they type into the text box on the web page). 

This will be trickier than you might think!

<br/>

## Challenge 7:

Let's actually count down the number of guesses that the player has left before they lose the game, and display that number inside a message that appears on the web page!

<br/>

## Challenge 8:

There's one last feature that's still missing. What happens if you win or lose the game, but then you make another guess? Let's try it out.

<br/>

...that shouldn't happen!

<br/>

So to solve this and create a better user experience, let's start with one of the easiest solutions: when the user wins or loses, we'll ***turn off*** the event listener so that additional clicks will no longer trigger the code to do anything!

Let's do a little research to figure out how to do that, and then compare notes.

<br/>

## Final notes to review:

<br/>

:star: ***Don't review these links until after you've completed the steps above on your own, and you've put in a good effor into writing the code yourself.***

<br/>

**Flowcharts** from the user's perspective (simpler version) and from the developer's perspective (with implementation details): https://github.com/LearnTeachCode/hangman-game
  
  > Notice how more detailed flowchart breaks down the decision point into ***yes/no*** questions -- whereas humans can easily ask a quesiton and answer it with three possibilities, computers can't! So, in our code, we need to turn our one question into *two separate yes-no questions*.

<br/>

**Code for the finished version** of this first Hangman game prototype: https://glitch.com/edit/#!/hangman-v0-final


<br/>
<hr/>

:trophy: **We did it!** It's definitely not a finished product, but we made use of *every* programming concept that we've learned so far. You already have enough pieces to build this into a much better game, if you'd like some bonus homework! ;)

:point_right: **In our next class**, we'll dig into some more fun and powerful topics like drawing and animation with p5js, loops, and modeling data with objects and arrays!
