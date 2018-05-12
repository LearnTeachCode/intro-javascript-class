# 1.4: Homework Part 2: Planning your project

Now that you've finished [homework part 1 (section 1.3)](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-3-homework-part1-review.md), it's time to practice with your own project!

If it feels intimidating to get started on a project, *that's totally normal!* Try to avoid the temptation to think about everything all at once; start small, have fun with it, and experiment! You can always change your mind later.

The planning process we went through in [section 1.1 to create our click-counter game](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-1-review-game.md) is exactly the same process you'll use to get started on your own project.

  > :elephant: Like the saying goes: how do you eat an elephant? *One bite at a time!*

<br/>

✔️ **To submit this assignment:** Share a link to your Glitch project in our private Slack chat channel!

❓ **If you have any questions, please ask on the private Slack channel for our class.** (See our [**intro to Slack video**](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#111-intro-to-slack) if you need a refresher.)

:clock2: **Time to complete: 1 to 2 hours.**

<br/>

<hr/>

## Setup

  1. **Remix the official Glitch web page starter template: https://glitch.com/edit/#!/hello-webpage**

  > See our [intro to Glitch video](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#113-intro-to-glitch) if you need a refresher!

  2. **In the `README.md` file in your Glitch project,** click the "Markdown" button above where it says "Welcome to Glitch" -- now you can edit that text!
  
  3. **Replace the "Welcome to Glitch" text with the name of your project.** You'll also be replacing the text in that file with your answers to the challenges below.
  
  4. **Share your progress and post the link to your Glitch project on our private Slack channel**!

<br/>

## Challenge 1:

In your `README.md` file on Glitch, write a short list of features for a ***bare minimum, unfinished, first version of your project***. This list should be short and simple -- don't overthink it!

**Examples:**

  - Feel free to copy ideas from [the feature list for our click-counter game in section 1.1](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-1-review-game.md).

  - Review the [Hangman game from our beginner class](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md) -- it's nothing like Hangman, but it's a start!

<br/>

**Prompts to help you write your feature list for version 0 of your project:**

  1. **What elements would be on your web page?**
  <br/> Buttons? Text input boxes? Images? Paragraphs? Bullet points?
  
  2. **What actions can the user take to interact with the app?**
  <br/> Think in terms of *events* that are outside of your control as the developer -- like when the user clicks a button, scrolls up or down on the page, presses certain keys on the keyboard, etc.
  
  3. **Which elements on the page will need to be accessed or changed by JavaScript?**
  <br/> Maybe only one of the paragraphs will change, or maybe new bullet points need to be created and added onto the page. Keep it as simple but also as specific as you can.
  
  4. **What decisions, calculations, or internal logic would the computer need to perform?**
  <br/> Are there any numbers increasing or decreasing? Are pieces of data being added, removed, or changed?

<br/>

Again, only do this for the *very first steps* towards building your project; it should be *simplified and unfinished!* There are no "right" answers here; the point is just to put your ideas on paper to help you break your idea down into small steps.

<br/>

## Challenge 2:

Next, write a short list describing the ***data*** used in your application.

For ***each*** piece of information that your program will need to store or keep track of, answer the follow prompts:

  1. **What data type would you use for this information?**
  <br/> Is it a string, a number, something else? If you think you'll need objects or arrays, break them down to describe the data type of each key-value pair or each element individually.

  2. **What would you name the variable that contains this data?**
  <br/> Remember, variable names should be specific enough that if you don't look at your code for a month and then return to it, you should be able to quickly jog your memory just by looking at the variable names.

  3. **What is the initial value of this data?**
  <br/> When your web app is first opened by the user, what is this variable's default or initial value?

  4. **How does this data change over time (if at all)? What actions cause the data to change?**
  <br/> Think in terms of cause and effect. Maybe this data comes from the user, maybe it's randomly generated, or maybe it depends on *another* piece of data?
  
  5. **Where is this information displayed on the web page, if at all?**
  <br/> Be as specific as possible; which HTML element would display this data? Or is it hidden from the user?

<br/>

## Challenge 3:

Also in the `README.md` file in your Glitch project, spend ***five minutes or less*** writing **pseudocode** for this first version of your project.

  > Remember, pseudocode is a list of steps in plain English, *not code*, but it should specific enough that you could hand this list to any programmer and they'd be able to follow it like a recipe and turn it into working code.

<br/>

**Example pseudocode for our [click-counter game](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-1-review-game.md):**

  - When the user opens the web app (when the page loads):
    1. Initialize a new number starting at 0
    2. Make variables to represent the button and paragraph on the web page    
    3. Start waiting for the user to click the button

  - When the button is clicked:
    1. Increase the number variable by one and save that new value to memory
    2. Display the new number inside the paragraph

<br/>

## Challenge 4:

Finally, start writing the actual code for this first version of your project!

**Some pointers:**

  - The goal is simply to *practice turning your ideas into code* -- it doesn't matter if it works or not! So don't be afraid to ***"fail fast, fail often"*** as they in the world of tech startups. We learn more from our failures than our successes, right? 
  
  - Feel free to recycle your code from [homework part 1 (section 1.3)](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-4-homework-part2-project.md) or from any of our example projects.
  
  - You can start by coding the HTML, or start by coding the JavaScript! At some point you'll have to link them together, but it doesn't matter which side you start from.
  
  - Don't worry about making it look nice. Use placeholders, just like we did with our [Hangman game](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md)!
  
  - For chunks of text beyond headings and short descriptions, just use some fake data! Try a [lorem ipsum generator](https://loremipsumgenerator.com/) to copy-paste paragraphs of text. That's what professional web and graphic designers do!
  
  - For images, you can generate some placeholder images of any size with these free tools: [PlaceIMG](https://placeimg.com/) or [Placeholder.com](https://placeholder.com/). Or feel free to leave out all the images entirely!

<br/>

<hr/>

:trophy: **Wonderful!** Little by little, you're turning your ideas into reality! By creating a project of your own, you're learning *so much more* compared to following step-by-step tutorials. Keep up the good work!

:point_right: **In our next class:** [we'll start learning about persistent data, the JSON data format, and Google's Firebase database library!](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-2)
