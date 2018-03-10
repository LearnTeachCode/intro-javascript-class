# 2.2: Event listener challenges

:tv: **Video: Intro to events and event listeners (19 min): https://youtu.be/UbwCNBCUrhQ**

Events and event listeners allow you to respond to user input (among many other types of events), telling a section of your code to *wait* until a particular event occurs, and then execute one of your functions when triggered by the event.

Web browsers provide a built-in JavaScript function named `addEventListener`, which is available on any DOM element in JavaScript.

:books: **Related review materials:**

  - [Section 1.5.4: Video review of DOM elements](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md#154-the-dom-interacting-with-html-and-css-using-javascript)
  - [Section 1.2: DOM element practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-2-dom-challenges.md)

<hr/>

## First, an example:

Before we dive in, try out this example of an event listener by copy-pasting the code below and running it directly in your browser console (on *any* web page):

```javascript
document.body.addEventListener("click", logMouseEvent);

function logMouseEvent (event) {
  console.log(event);
}
```

After running the code... nothing happens! Why's that? 

*...because the event hasn't been triggered yet!* 

To trigger the event, click anywhere on the web page. Then look inside the console. You should see a `MouseEvent` object show up in your console every time you click the page, and you can expand that object to look inside it:
![console-expand-object](https://user-images.githubusercontent.com/1555022/26953972-67a12a30-4c62-11e7-8bb0-bb786e433bd1.gif)

*Pretty cool, right?!* :)

Every time you use an event listener, there are **three main questions** you'll need to answer:

  1. **Where is the event happening?** Here, it's happening anywhere in the `document.body` (the `<body>`, the entire web page!)
  2. **Which event are we listening for?** Here, it's a `"click"` event ([see the list of all built-in events here!](https://developer.mozilla.org/en-US/docs/Web/Events))
  3. **What should happen when the event occurs?** Here, we run our function named `logClick`

This is totally optional, but in our example above, our `logClick` function also receives an ***input*** from the event listener, which contains information about the event that just occurred! This is something we'll learn more about in our next set of challenges on functions.

  > :pencil: **Preview of a more advanced topic:** In the example code above, the `event` variable is a *parameter* that the `addEventListener` function will replace with a `MouseEvent` object, which is what contains all the information about each mouse click. (Phew, try saying that 10 times fast! Again, just a note for later. Not important right now.)

<br/>

## Setup:

**Remix this Glitch project for our Hangman game** with the HTML and CSS (but no JavaScript!): https://glitch.com/edit/#!/hangman-v0-starter

**Glitch instructions** (a refresher from last week):

  - To **remix** a project on Glitch, click the project's name in the top left corner, and then click "Remix This" in the dropdown menu to make your own personal copy.
  
  - **To see the live app and test it out**, click "Show Live" on the top left and it'll open the web page in another tab.

  - Remember to check *both* the **live web app** and the **JavaScript console in Chrome's developer tools** to see the results of your code, hunt down any bugs, and check if you've fixed those bugs!

  > You can review our [**intro to Glitch video** in section 1.1.3](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#113-intro-to-glitch) if you need a refresher on what Glitch is all about!


<br/>

## Challenge 1:

In your personal copy of the Hangman game, write some JavaScript code to display the message `"User clicked the button!"` in the console every time the user clicks on the button in our game.

  > Be sure to reference past examples of accessing DOM elements, along with the event listener example that we just tried out.

<br/>

## Challenge 2:

Take a look at [this reference page listing *all* the built-in web browser events](https://developer.mozilla.org/en-US/docs/Web/Events), and change your code from the previous challenge so that your function is instead triggered when the user **double clicks** on the button.

<br/>

## Challenge 3:

**Discuss:** what events would your own project need to use? What action(s) would each event trigger in your app?

**Bonus:** Look up the names of some of those events in the reference page linked to above. (If there aren't other events applicable to your project, browse for some other interesting events -- see what you find!)

<br/>

<hr/>

:trophy: ***Woohoo!*** You can now say you've already written your first bit of *asynchronous code!* (A more advanced topic, but in short, this refers to the fact that now you know how to write code that *waits* for an event to happen.)

**Next up:** we'll take a closer look at how functions work with some more practice challenges!
