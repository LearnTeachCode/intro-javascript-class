# 1.3: Practice challenges: Variables and data types

Time to tinker with code and break stuff! Below are several practice challenges where you either need to solve a bug, *create* a bug, or write some code from scratch.

:trophy: For all of the discussion prompts below, the goal is just to brainstorm and come up with your own guesses -- and ***have fun!*** It doesn't matter if you're correct or not. Like they say, we learn more from our failures than from our successes. So let's have fun "failing", breaking things on purpose, and learning from the experience!

**You can run your code in several different ways:**

  1. Use [Python Tutor](http://pythontutor.com/javascript.html#mode=edit) to visualize your code step-by-step (no access to HTML or CSS though, only simple JavaScript that can run on its own)
  
  2. Run your code directly inside your web browser's JavaScript console (see [section 1.1.4 for a review](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#114-intro-to-chromes-developer-tools-and-the-browser-console))
  
  3. Use a [Glitch](https://glitch.com/) project to test your code with HTML, CSS, and JavaScript files all within your web browser (see [section 1.1.3 for a review](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#113-intro-to-glitch))
  
  4. Create everything locally on your computer with Visual Studio Code or any text editor that you prefer (see [section 1.1.5 and 1.1.6 for a review of VS Code](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#115-intro-to-text-editors-visual-studio-code))

  > All the tools listed above have their pros and cons. Try them all and see what you like best!

<hr/>

## Challenge 1: 

Run the following code, and then be sure to check your browser's JavaScript console (see [section 1.1.4 for a review](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#114-intro-to-chromes-developer-tools-and-the-browser-console)) to see what happens! Then ***break it five different ways***. Save all your code in a file or on Glitch so you can share it with the rest of us!

```javascript
// Create a new variable
let myNerdyJoke = "Debugging is like being the detective in a crime drama where you are also the murderer";

// Display it in the console
console.log(myNerdyJoke);
```

**Then discuss** *(in other words, take random guesses and talk about your ideas!)*:

  1. Which words or symbols can we *change* without breaking the code? Which words/symbols need to stay the same?
  
  2. What do you think the equal sign (`=`) means in JavaScript?
  
  3. What do you think the keyword `let` means here?
  
  4. And what's the deal with those semicolons at the end of each line of code?
  
  5. Does the *order* matter for which of these two lines of code runs first? Why or why not?


## Challenge 2: 

A message should appear in the browser console, but the code is broken! Let's fix it up:

```javascript
lot veryTrueStatement = "If you give someone a program, you will frustrate them for a day; if you teach them how to program, you will frustrate them for a lifetime!";
console.log(veryTrueStatement);
```

## Challenge 3: 

This code isn't working either. :( Can you fix it so that the joke will appear in the browser console?

```javascript
let coderJoke = "My software never has bugs. It just develops random features.";
Console.log(coderJoke);
```

## Challenge 4: 

I found a great joke [from the creator of Stack Overflow](https://twitter.com/codinghorror/status/506010907021828096) but the code below isn't showing the joke in the console like it's supposed to! Can you fix it?

```javascript
let anotherJoke = "There are two hard things in computer science: cache invalidation, naming things, and off-by-one errors."
console.log("anotherJoke");
```

## Challenge 5: 

I could've sworn that computers were good at math, so why isn't my code working? Fix all the code below to make the computer actually *add up the numbers* and display each result in the console:

```javascript
// The answer should be 9, unless the rules of addition have changed since I finished school?!
console.log("4" + "5");

// Last time I checked, 2 + 2 was 4!
console.log("2" + 2);

// And four sets of 4 should be 16, unless you're deadmau5 (see https://www.youtube.com/watch?v=_9IBbMW2o_o)
console.log(4 + "4" + 4 + '4');

let x = 1;
let y = 2;
let z = 3;
// The code below is supposed to display the number 6
console.log('x' + 'y' + 'z');
```

**Discuss:**

  1. Why did the broken code work the way it did?
  2. Why are computers so stupid?
  3. Does it matter whether we use single or double quotation marks?


## Challenge 6: 

So it turns out that in JavaScript, the plus sign (`+`) is used for two different things: adding numbers and combining words! In computer science jargon, we use the word ***string*** to refer to any data that should be treated as a word, a label, or literally a bunch of letters and symbols *strung* together like [those alphabet beads that you can *string* together into a necklace](https://www.etsy.com/market/alphabet_beads)!

Here's another fancy word that will make you sound like a computer scientist: ***concatenation***. It means "chaining things together", just like making a necklace from alphabet beads. So when we write `"hello" + "world!"` in our code, we're *concatenating* the two strings `"hello"` and `"world!"` to create one longer string! In this context, the plus sign (`+`) is called the *concatenation operator*.

Armed with this new knowledge, **complete the unfinished code below** so the console will show one long string that says `It's peanut butter jelly time!`:

  > If that's too easy, solve this challenge *10 different ways* by mixing and matching strings and variables in every combination you can think of!

```javascript
let pb = "peanut butter"
let jt = "jelly time"
console.log(pb + jt)
```

## Challenge 7: 

Create three separate variables of your own to represent your name, your favorite food, and your favorite number. Be sure to give your variables descriptive names, and use [**camelCase style**](https://en.wikipedia.org/wiki/Camel_case) (where `variableNamesLookLikeThis`, which is the msot common convention among JavaScript programmers).

Next, display a message in the browser's console that combines each of your three variables into a sentence where you awkwardly introduce yourself by saying something like `"Hi there! My name is Liz, my favorite food is chocolate, and my favorite number is 42!"`


## Challenge 8: 

The code below is for a video game where you start with 100 health points, and then after getting attacked by a dragon, you now have only 45 health points. Why doesn't the code work, and how can you fix it?

```javascript
// Start with 100 HP (health points)
let healthPoints = 100;

// Just to easily see every step of our code, show the HP in the console
console.log("Health points remaining:" + healthPoints);

// Dragon attack, oh nooooo!!!
// (some other code will be written here later to create the dragon and make it attack)
console.log("A dragon just sneezed on you! Ouch, it burns!!! OMG SO HOT~~!!!!!!!!1!!11!!1eleven");

// After being engulfed in dragon flames, player only has 45 HP left
let healthPoints = 45;

// Show the value of the user's health points in the browser console
console.log("Health points remaining:" + healthPoints);
```

**Discuss:**

  1. Why exactly was the code broken?
  2. Why would this broken code be so confusing to the computer that it can't even run it?


## Challenge 9: 

Imagine you're creating a social network application like Facebook where you'll need to store information about each user. For each piece of information listed below, discuss whether it would make more sense to store the data as a ***string*** or as a ***number***:

  1. Full name
  2. Age
  3. Job title
  4. Zip code
  5. Date of birth


## Challenge 10: 

Based on what you've learned so far, discuss:

  1. What pieces of information would you need for your own project?
  2. Which data types (strings or numbers) would you need to use for each piece of information in your own project?
  3. Does some of that data *not fit* neatly into the category of a string or a number?

:pencil: Jot down your answer in your notes too, because this is an important part of the project planning process!

**Bonus:** Discuss *other* data types if you're already familiar with them, or *search online* to learn more about the term "data types" and what types there are in JavaScript!


## Bonus challenge 1:

First run the following code and check the browser console to confirm that it works as you'd expect:

```javascript
console.log(jokeVersionOne);
let jokeVersionOne = "When Apple employees die, does their life HTML5 in front of their eyes?";
```

Now, compare it to the code below which uses `var` instead of `let` to create the new variable:

```javascript
console.log(jokeVersionTwo);
var jokeVersionTwo = "When Adobe employees die, does their life Flash in front of their eyes?";
```

**Discuss:**

  1. Which version do you think is more intuitive -- using `var` or using `let`? And why?
  2. What would you guess the computer is doing differently in these two scnearios?  


## Bonus challenge 2:

Complete the unfinished code below to update the variable named `bugsSolvedToday` to become the **sum of its previous value plus one**, but *without modifying the code already provided below*:

```javascript
let bugsSolvedToday = 7; // Don't modify this line of code!

// Write ONE line of code here (between the others) to solve this challenge:

console.log(bugsSolvedToday); // Don't modify this line either!
```

## Bonus challenge 3:

Similar to bonus challenge #2 above, complete this unfinished code to *concatenate* the string `" and again"` onto the end of the variable named `neverEndingSentence`, and then *copy-paste* that line of code to repeat it 10 more times! (Again, don't modify the first or the last line of code provided below.)

```javascript
let theCoderLife = "Debug it again"; // Don't modify this line of code!

// Write a line of code here (between the others) to solve this challenge:

// ...and then copy-paste that line of code 10 more times here to make the string longer and longer:

console.log(theCoderLife); // Don't modify this line either!
```

<hr/>

:trophy: ***Great job!*** **Next up:** in [section 1.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-4-conditional-challenges.md)we'll practice using JavaScript to interact with the web page using the browser's built-in Document Object Model API!
