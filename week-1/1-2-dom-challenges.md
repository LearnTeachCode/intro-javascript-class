# 1.2: Practice challenges: Interacting with the web page (Document Object Model)

Next, let's use JavaScript to dynamically modify the HTML and CSS of a web page! For the following challenges, you'll be using the Glitch links provided to test out some example code, fix some bugs, and create some bugs of your own.

**Instructions:**

  - To **remix** a project on Glitch, click the project's name in the top left corner, and then click "Remix This" in the dropdown menu to make your own personal copy.
  
  - **To see the live app and test it out**, click "Show Live" on the top left and it'll open the web page in another tab.

  - Check both the **live web app** and the **JavaScript console in Chrome's developer tools** to see the results of your code, to help you hunt down any bugs, and to check if you've fixed those bugs!

  > You can review our [**intro to Glitch video** in section 1.1.3](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#113-intro-to-glitch) if you need a refresher on what Glitch is all about!

<hr/>

## Challenge 1: 

Take a look at the JavaScript code in this Glitch project, then take a look at the live web page and look inside your web browser's JavaScript console -- you'll see a message!

**Remix this Glitch project:** https://glitch.com/edit/#!/challenge-1-2

Next, go back to the JavaScript file in Glitch, **modify the message** (without breaking the code!), and then check again to see if the new message does indeed appear in the browser console when you refresh the live web page.

*Did it work??? If so...*

:trophy: **Woohoo!** Now you already know the basics of how to use what's probably the most important built-in JavaScript function: `console.log()`! As you'll see with more practice, it's very useful for seeing what's happening in your code.

<br/>

## Challenge 2:

Using the same Glitch project from the previous challenge, create some bugs of your own in the JavaScript file! ***Break the code in at least 5 different ways.***

:star: Save all your versions of broken code inside a comment (with `//` in front of every line of code), so that way you can share your beautiful new bugs with the rest of us! So keep track of the URL for your Glitch project too!

:bulb: **Important tip:** You can "comment out" a bunch of code all at once by selecting multiple lines of code and then pressing `Ctrl + /` on Windows or `Cmd + /` on Mac. You can repeat the process to *uncomment* lines of code too.

**Then discuss** *(in other words, take random guesses and talk about your ideas!)*:

  1. Which words or symbols can we *change* without breaking the code? Which words/symbols need to stay the same?

  2. What is `console`, what is `log`, and what is `console.log`?
  
  3. And what does the period (`.`) mean in JavaScript?
  
  4. Why do we use a pair of parentheses `()` after `console.log` and what would happen if we used `console.log` without any parentheses after it?
  
  5. Why do we surround the message with quotation marks?

<br/>


## Challenge 3:

For this challenge, **remix this Glitch project:** https://glitch.com/edit/#!/challenge-3-4 and follow the steps below:

  1. Take a look at the HTML file, the JavaScript file, and the live web page to see an example of how we can use JavaScript to ***change*** all the text inside the `<body>` element of the HTML file.

  2. **Change the message inside the JavaScript code** and take another look at the web page -- did it work? It should change again to show your new message right there on the page!

  3. Next, **copy that line of code** from the JavaScript file, open the live web page again, open the browser console while on that page, and then **paste the code directly into the browser console.**
  
  4. Before you run the code inside the console, **change the message one more time** and then press the `Enter` key to run the code. *Cool, right?! The web page changes instantly!*

  5. **Discuss:** what's the difference between using `console.log()` versus this new command? In which situations would it be better to use one and not the other?

<br/>


## Challenge 4:

Not only can we can *change* the text that appears on the web page, but we can also *inspect* the current value of that data (the text in the `<body>` element of the web page) using our handy dandy `console.log()` function!

Using the same Glitch project from the last challenge, ***combine pieces of the code*** from the last two challenges so that the **browser console** will display all the text inside the `<body>` element in the HTML file.


<br/>


## Challenge 5:

What if we want to change the text inside ***one particular element***, not the entire `<body>` of the page? There's another built-in function named `document.getElementById()` which will let us access an element of the web page.

<br>

**To use this new function and solve challenge #5, you'll need to know the following:**

  1. HTML elements can have an `id` attribute, which lets you assign a label to an element of your page. For example:
  
```html
<p id="special">This paragraph is different from the other paragraph below!</p>
<p>Plain ol' regular paragraph.</p>
<p>Another boring, non-special paragraph.</p>
```

<br>

  2. The `document.getElementById()` function in JavaScript takes **one input**: the ID of whichever HTML element you want to access. For example, to change the text inside that example paragraph with the ID of `"special"`, we can do this:
  
```javascript
document.getElementById("special").textContent = "This text will replace what the text of that special paragraph.";
```

<br>

  3. Notice how the `getElementById()` function is ***interchangeable*** with `body` in JavaScript code:

```javascript
// Using body
document.body.textContent = "This replaces the text of the entire body element.";

// Using the getElementById() function
document.getElementById("special").textContent = "This replaces the text of that special paragraph.";
```

<br>

:bulb: Switching out interchangeable pieces -- like Lego blocks! -- is one of the most fundamental concepts in every programming language. Coding is all about recognizing *which* pieces can be swapped out, *where* they can and can't be used, and *how* to mix and match them to create new things!

<br>

:trophy: **Finally, here's your challenge:** Remix the Glitch project at https://glitch.com/edit/#!/challenge-5-6 and solve the bug!

  > **Hint:** Be sure to check the live web page, the browser console, the HTML file, and the JS file!

<br/>


## Challenge 6:

Open the live web page from the previous challenge, and then open your web browser's JavaScript console while on that page. Write some code *directly* into the console to accomplish the following:

  1. Change the text of the **red** box to say `"Beep!"`
  
  2. Change the text of the **green** box to say `"Kaboom!"`
  
  3. Change the page heading to say `"I am a JavaScript Jedi Master!"` (Hint: look for the `<h1>` tag in the HTML)

<br/>


## Bonus challenge 1:

This is a Google challenge! Look online to figure out how to ***change the background color*** of the entire web page, and test it on *any* live website by running the code in your browser console. Try it on [Google.com](https://www.google.com/), for example!

<br/>


## Bonus challenge 2:

Take a look at the code in this very tiny web app and solve the bug:<br/>
https://glitch.com/edit/#!/bonus-challenge-2

  > **Hint:** This one can be *tricky!* You'll need to look carefully at the HTML file, and it has something to do with an important topic covered in [one of the review videos in section 1.5](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-5-review-hangman-game.md).


<hr/>

:trophy: ***Great job!*** **Next up:** we'll practice making decisions JavaScript based on some data with conditional statements!
