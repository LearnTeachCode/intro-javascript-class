# Section 4.4: Drawing with the p5js library

We'll be working in pairs to tinker with more code, using functions provided by awesome [**p5js library**](https://p5js.org/) designed to making coding more accessible for beginners, especially for artists who want to make creative works with code.

<br/>

:books: **For future reference:**

  - [Official p5js "Getting Started" guide](https://p5js.org/get-started/)
  - [Full reference manual](https://p5js.org/reference/) about all the p5js functions


<hr/>

<br/>

## Challenge 1:

<br/>

:star: [**Click here to open a template project with p5js already set up**](https://glitch.com/edit/#!/canvas-challenges) and be sure to ***remix it*** to save your own copy. :star:

<br/>

Copy the example code below and paste it ***right after*** the `createCanvas()` function that's being used on **line 10** in our example JavaScript file.

```javascript
rect(200, 300, 50, 100);
```

<br/>

Then try ***changing*** those four numbers that draw the rectangle, and ***identify*** what they all do!

  > Be sure to click **"Show Live"** at the top left of the page to open your live web page and see your amazing rectangle!

<br/>

## Challenge 2:

Draw a circle using the `ellipse()` function -- see [the p5js reference page for ellipses](https://p5js.org/reference/#/p5/ellipse) and feel free to copy code examples from there!

<br/>

## Challenge 3:

Copy the sample code below into your project, and then write two more lines of code to create two more variables, one for each coordinate that determines where the square will be drawn on the canvas. Assign a number between 0 and 500 to each of your two variables, to make this code work:

```javascript
let squareWidth = 75;
// Write two more lines of code below to create the variables for xPos and yPos


rect(xPos, yPos, squareWidth, squareWidth);
```

<br/>

## Challenge 4:

Let's spice things up with a little *randomness*! First, do a quick search on Google to see if you can find out how to generate random numbers using JavaScript code. There's a built-in function that does exactly that!

<br/>

Next, try it out -- if you found any example code, see if it actually works!

<br/>

## Challenge 5:

Just like how [the MDN reference page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) suggests creating your own functions to generate the types of random numbers that you want, the p5js library did exactly that!

In p5js, they named their custom function `random()`. Take a look at [the p5js reference page for `random()` here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) to see how to use their function.

<br/>

**Your challenge:** Combine the p5js random number generator function with your code from challenge #3 above to draw a square at a ***random*** location (with randomized coordinates)!

  1. If you draw the random square inside the `setup()` function, it'll be drawn ***once*** when the page loads. (If you refresh the page, it'll appear somewhere else.)

  2. If you draw the random square inside the `draw()` function instead, p5js will call it ***over and over again***, once for every animation frame. (Right now, it's set to animate at a speed of 2 frames per second.)

<br/>

## Challenge 6:

Now draw ***three*** randomly placed squares! (Your choice as to whether you want them to be drawn once on page load, or as part of an animation.)

<br/>

## Challenge 7:

Now draw ***one hundred*** randomly placed squares!

<br/>

***...what, you don't want to copy-paste 100 times?*** *Yeah, I don't blame you!*

<br/>

Remember, you always want your code to be [ ***DRY: Don't Repeat Yourself!*** ](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

  > The opposite is ***WET*** code: "write everything twice", "we enjoy typing" or "waste everyone's time." :laughing:

<br/>

**Your challenge:** Write a regular `while` loop or `for` loop that runs 100 times, and move your square-drawing code into that loop.

It's time to do some Googling for a refresher on how to write basic loops, if you don't remember off the top of your head. (Remember: that's why you should create your own cheat sheet of common code examples, to save yourself some time in looking everything up.)

<br/>

## Bonus challenge 1:

Look at [the reference page for the `fill()` function](https://p5js.org/reference/#/p5/fill) and use it to change the color of your squares.

<br/>

## Bonus challenge 2:

Combine our random number generating function with the `fill()` function so that every square will be a random color!

<br/>
<hr/>


🏆 ***It's a work of art!*** Code is a form of art; it's creative, expressive, and fun to experiment with! As you continue to learn more challenging concepts, think of ways to make it artsy or silly; it will help you learn more!

