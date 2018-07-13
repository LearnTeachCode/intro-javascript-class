# Section 2.5: Events and event listeners

Events and event listeners allow you to **respond to external events** (like when a user clicks the page), telling a section of your code to *wait* until a particular event occurs.

Web browsers provide a built-in JavaScript function named `addEventListener()`, which is available on ***any DOM element*** in JavaScript -- so *any* element of the web page can respond to various actions from the user!

<br/>

:tv: **Video: Intro to events and event listeners (19 min): https://youtu.be/UbwCNBCUrhQ**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

<hr/>

## Quick recap

[In our previous class](https://github.com/LearnTeachCode/intro-javascript-class/tree/july-aug-2018/week-1), we copied this example code and used it in our Dragon Defeater game:

```javascript
document.body.addEventListener("click", logClick);

function logClick () {
  console.log("The user just clicked!");
}
```

Let's take a closer look at event listeners with some more practice challenges!

<br/>

## Challenge 1:

:star: **For these next challenges, remix this Glitch project: https://glitch.com/edit/#!/js-event-listeners1**

<br/>

**Your first step:** Copy-paste the code from the example code above, and test it to make sure the code works!

<br/>

**As a quick bonus challenge:** Does the message appear if you click anywhere, or only in some places? Why or why not? 

After experimenting and discussing what you find, then see if you can change the code a tiny bit so that you can click *literally anywhere* on the page and still see the message appear.

  > **Hint:** What do you think the difference is between the `document` itself versus the `body` of the `document`?

<br/>

## Challenge 2:

Add one additional line of code so that when the user clicks on the page, **the entire body of the document** will be replaced with the text `"You clicked on the page!"`.

<br/>

## Challenge 3:

Modify your code for the previous challenge so that when the user clicks anywhere the page, instead of overwriting the *entire page*, your code will only overwrite the text inside the ***last paragraph*** at the bottom of the page.

<br/>

## Challenge 4:

It's very rare that we would want a user to click *anywhere* on our web page -- usually they need to click on a button or an image to make something happen. (Otherwise it would be pretty confusing!)

Change your code again so that your function will only be called if the user clicks on one of the buttons. (It doesn't matter which button you choose.)

<br/>

## Challenge 5:

Create *another* event listener and *another* function, to accomplish the following:

  - If the user clicks button #1, make the background of button #1 turn green and the background of button #2 turn red
 
  - If the user clicks button #2, switch the background colors of the two buttons. So one should always turn green and the other should always turn red, toggling them on and off.

<br/>

## Challenge 6:

Let's get even crazier! Create a *third* event listener and function to accomplish the following:

  - When the user clicks on the last paragraph at the bottom of the page, change the text of that paragraph to say `"Hahaha, that tickles! Stop clicking me!"`

<br/>

## Challenge 7:

There are *lots* of built-in events that web browsers provide for you to use in your code! So far, we've only been using one: `"click"`.

Take a look at [this reference page listing *all* the built-in web browser events](https://developer.mozilla.org/en-US/docs/Web/Events), and **change your code** from challenge #6 so that your function is triggered when the user **double clicks** on the last paragraph (instead of a single click).

  > **Important note:** The name of every event is just a **string**, and *every single built-in event* is included in that giant list! You'll probably only need a handful of those events; most of them are rarely used.


<br/>


## Recap: Three parts for setting up event listeners:

Every time you use an event listener, there are **three main questions** you'll need to answer:

  1. **Where is the event happening?**
  
  2. **Which event are we listening for?**
  
  3. **What should happen when the event occurs?**

<br/>

### Visualizing the event listener pattern in code:

![eventlistener-example](https://user-images.githubusercontent.com/1555022/41071909-97028790-69af-11e8-94fd-2c3fada9499d.png)

<br/>

### Answering the three questions for the example in the picture above:

  1. **Where is the event happening?** On the DOM element with the id of `"main"`.
  
  2. **Which event are we listening for?** A `"click"` event ([again, see the list of all built-in events here!](https://developer.mozilla.org/en-US/docs/Web/Events))
  
  3. **What should happen when the event occurs?** Here, we run our function named `funcName`

<br/>

:bulb: Notice how `document.body` and `document.getElementById("main")` are also ***interchangeable*** here, like in the examples we worked with in last week's class.



<br/>

## Challenge 8:

Find the name of the event that's triggerd when the user types on their keyboard! There's actually *more than one* event name to accomplish this.

Create an event listener so that if the user types on their keyboard, *anywhere on the web page*, the console will display the message `"The user typed something!"`

Then test it out with *all of the keyboard events* and discuss:

  1. What's the difference between each of the keyboard events?
  2. What are some situations where one type of keyboard event would be better than another? Why?

<br/>

## Challenge 9:

Usually we only care about the user typing into some sort of *input field*, like a text box. And, very conveniently, our example web page already has a text box!

Change your code from challenge #8 so that instead of calling your function *anywhere* on the page, it will only call your function if the event happens *in the text box*.

<br/>

## Getting more information about the event

The code below is *very similar* to our very first example at the top of this page, but notice one importance difference: the function that's triggered by the event now has a **parameter**! 

```javascript
document.body.addEventListener("click", logMouseEvent);

function logMouseEvent(event) {
  console.log(event);
}
```

Try running this code, either inside your Glitch project or directly in your browser console on any web page. (Be sure to also click somewhere on the page to trigger the event!) Then take a look at what appears in the console -- a `MouseEvent` object!

![console-expand-object](https://user-images.githubusercontent.com/1555022/26953972-67a12a30-4c62-11e7-8bb0-bb786e433bd1.gif)

If you expand the object inside your browser's console, you can see it contains a long list of information about the event that just occurred. Each category of events will provide different information about the event that just happened.

  > **Note:** The magic of *how* that information gets sent to your function is a more advanced topic that we'll return to later. For now, we'll just focus on putting this to use!

<br/>

## Challenge 10:

Time for a quick scavenger hunt! After trying out the example code provided above, expand the MouseEvent object in your browser console and look through the long list to find out: what's the name (or names!) used to show us the ***coordinates*** of where the user clicked on the page?

  > **Bonus:** You'll see that web pages have a somewhat unintuitive coordinate system. What are the x and y coordinates of the very *top-left corner* of the web page? As you move to the right, or as you move down, how do those coordinates change?


<br/>

## Challenge 11:

Take the code provided below, and modify it slightly so that instead of displaying `"An event just happened!"` in the console, it should instead display ***the event object*** inside the console, so you can see that long list of information about the `"keypress"` event!

```javascript
document.addEventListener("keypress", logEvent);

function logEvent() {
  console.log("An event just happened!");
}
```

Be sure to test your code and confirm that it works! You can run it directly in the browser console on *any* web page. Make sure the web page is in focus first by clicking somewhere on the page, and then you can trigger the event by pressing a button on your keyboard.

<br/>

## Challenge 12:

Using your browser's console, take a look at the information contained inside that event object to find out: what's the name (or names!) used to show us ***which key** was pressed by the user?

<br/>

## Accessing information inside of JavaScript objects

So far, we've already used some built-in JavaScript objects -- for example, the `document` object, which represents the *entire web page!*

<br/>

:star: **You can think of JavaScript objects as *folders***, which can contain files and even *more* folders inside of them, just like how you organize things on your computer's hard drive. (`"Documents/Homework/JavaScript"` or `"Pictures/2018/Hawaii"`)

<br/>

In JavaScript, instead of using slashes like we do with files and folders, we can use what's called ***dot notation*** to access information that's contained inside of an object.

**Examples:**

  - `document.body` means: "Look inside the `document` object to find the `body`"
  
  - `document.body.textContent` means: "Look inside the `document`, then look inside the `body` to find the `textContent`"
  
  - `console.log()` means: "Look inside the `console` which contains its own function named `log()`

<br/>

This is just a quick preview of a very big topic that we'll return to in our future classes. But we already know enough to put this information to good use with our event listeners!

<br/>

## Challenge 13:

First, let's take another quick look at our previous example, where we got our first look at the `MouseEvent` object that contains all that extra information related to where/when/how the user clicked on the page:

```javascript
document.body.addEventListener("click", logMouseEvent);

function logMouseEvent(event) {
  console.log(event);
}
```

Looking inside the browser console, we saw information like this:

![console-expand-object](https://user-images.githubusercontent.com/1555022/26953972-67a12a30-4c62-11e7-8bb0-bb786e433bd1.gif)

So to access one of those specific pieces of information contained inside the `MouseEvent` object, we can make one tiny change to our code like this:

```javascript
document.body.addEventListener("click", logMouseEvent);

// The parameter named event is what represents that giant MouseEvent object:
function logMouseEvent(event) {

  // So we can access data inside that giant object like this:
  console.log(event.clientX);
  console.log(event.clientY);
}
```

The code above will display the pieces of information named `clientX` and `clientY` that are contained inside that giant `MouseEvent` object, so we can see *only that one number* appear in the console.

<br/>

:star: **Your challenge:** Modify your existing code in your Glitch project to accomplish the following:

  - When the user clicks anywhere on the page, display their mouse's X and Y coordinates on the web page, replacing the text of the last paragraph at the bottom of the page.

<br/>

## Challenge 14:

First, take all the existing JavaScript code in your Glitch project and ***comment it out!*** (Or delete it if you prefer, or paste it into a file or an email to yourself to save your work.)

<br/>

  > **Remember this keyboard shortcut:** You can comment or uncomment multiple lines all at once by selecting the text and the pressing `Cmd + /` on a Mac of `Ctrl + /` on a PC. <br/><br/>**To download a backup of your Glitch project:** Click the project name in the top left, then click "Advanced Options" at the very bottom, and then click "Download Project".

<br/>

Alright, clean slate! (It's always good to test your code one piece at a time and not let your projects get too cluttered with old code.)

<br/>

:star: **Your challenge:** Write the code to accomplish the following:

  1. When the user presses a key on their keyboard, *anywhere on the web page*, trigger a function named `handleKeyPress`.
  
  2. Make sure that your `handleKeyPress` function is defined with a parameter, so it can receive all that extra information about the event.
  
  3. Display the entire event object in the console whenever the user presses a key.
  
  4. Find out what the key code is for the letter A and the letter B.
    
  5. Use conditional statements as needed so that if the user presses the letter A, display in the console: `"You pressed A"`; otherwise, if the user presses B, display in the console: `"You pressed B"`.
  
  6. Then add a bit more so that in addition to displaying those messages in the console, your code will also display those messages inside that last paragraph at the bottom of the page.

<br/>

## Bonus challenge 1: Build a virtual drum set!

There are *so many* cool features built into modern browsers now, and one of them is the ability to easily play audio files using JavaScript!

Try running this code directly in your browser console, and make sure your audio is on so you can hear it:

```javascript
let audio = new Audio('https://raw.githubusercontent.com/siggy/beatboxer/master/sounds/snare_drum.wav');
audio.play();
```

<br/>

The audio file above was borrowed from [this open-source drum machine web app](https://github.com/siggy/beatboxer), and you can [play the demo here](https://sig.gy/beatboxer/)!

Try out the other sounds by replacing `snare_drum.wav` at the end of the file URL with the name of one of the other sound files listed here: https://github.com/siggy/beatboxer/tree/master/sounds

<br/>

**Your challenge:** Build a virtual drum set, by combining this new example code with the code you already wrote for challenge #14.

A couple suggestions:

  - Start with playing the same sound when the user presses any key, just to make sure it works.
  - Then try playing two different sounds based on which key the user pressed.
  - Once you get that working, go crazy! You could assign a different key for every sound file provided in that list!


<br/>

<hr/>

:trophy: ***Woohoo!*** You can now say you've already written your first bit of *asynchronous code!* (A more advanced topic, but in short, this refers to the fact that now you know how to write code that *waits* for an event to happen!)

:point_right: **[Next up: as another group project, let's build a minimal version of the Hangman game!](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-2/2-6-group-project-hangman.md)**
