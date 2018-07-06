# Section 1.4: Interacting with the web page and the Document Object Model

To create our game, we'll need to *change* the text that appears on web page, so the user knows what's going on!

In order to access the web page with our JavaScript code, we'll work with the ***Document Object Model (DOM).*** The DOM represents how the web browser sees a web page -- as a *hierarchy* of objects, each with its own set of characteristics (like the text inside it, the font, the color, etc).

![dom-diagram](https://user-images.githubusercontent.com/1555022/41071577-7a781542-69ad-11e8-97dd-274355e2d2d1.png)

We use the term ***DOM element*** to refer to pieces of the web page like a paragraph (`<p>`), an image (`<img>`), a heading (`<h1>`), etc.

<br/>

:trophy: Let's use JavaScript to access the **DOM** and modify the HTML and CSS of some web pages! For the following challenges, you'll be using the Glitch links provided to test out some example code, fix some bugs, and create some bugs of your own.

<hr/>

## Challenge 1:

:star: **Make sure you have your personal copy of our HTML mockup on Glitch open in a tab**, following the instructions from the previous section.

Take a look at the example code below and make a prediction about what you think it will do:

```javascript
document.body.textContent = "Hello, world!";
```

<br/>

Next, copy-paste that code into your `script.js` file inside Glitch. How did it change your web page?

  > Be sure to click "Show Live" in the top left corner of the Glitch code editor, and switch to the tab that has your live web page open.

<br/>

Notice that the `index.html` file has some text and HTML tags, but now if you look at the live web page (click "Show Live" inside Glitch), that's not the text you see on the screen!

<br/>

## Challenge 2:

**Change the code** that you just copy-pasted to make the web page show the message: `"I love JavaScript"`

<br/>

## Challenge 3:

Let's hack Google! (Well... not really, but sort of!)

  1. Copy that one line of JavaScript code from your `script.js` file.
  2. In a new browser tab, go to Google.com (or any website of your choosing!)
  3. Then open your browser's JavaScript console while you're on that page.
  4. Paste that line of JavaScript code into the console, and press Enter to run the code!

<br/>

What happened to the web page?

  > But what happens if you refresh the page, or close and reopen it?

<br/>

## Challenge 4:

Take a look at the example code below. How is this different from the code in the previous challenge?

```javascript
document.getElementById("outcome").textContent = "Penguins are cool";
```

<br/>

Next, in your `script.js` file, delete or *comment out* the line of code from the previous challenge. Replace it with the code above.

**Discuss:**

  - What happened to the web page?
  - How is this line of code *different* from our previous example?
  - How does it know *where* to put our new phrase "Penguins are cool"?

<br/>

## Challenge 5:

Let's experiment with this new mini-superpower that lets us change text on certain parts of the web page!

<br/>

  1. Create *another* paragraph in the HTML file -- just add it to the bottom of the page, somewhere before the closing `</body>` tag. It should display: `"Something will go here"`.
  
  2. Before anything else, open your live web page again to check that it worked. You should see your new text appear on the page.
  
  3. Give your new paragraph a ***unique ID***. (Something like `"special"` or `"quicktest"`, anything you like, as long as it's a unique name!)
  
  4. Then in your JavaScript file, make a *duplicate* of the code from the previous challenge -- so you should now have ***two*** lines of code.
  
  5. Change one of those lines of code so that your JavaScript file will tell the web browser to find your new paragraph in the HTML file and *change* its text to display: `"Here is some new info"`.

<br/>

## Selecting specific elements of the web page

Notice that for challenges #1, 2 and 3 above, we used JavaScript to change the text of ***document.body***, the **entire** body of the web page! But for challenge #4 and #5, we changed the text of just ***one paragraph***.

<br/>

The **`document.getElementById()`** function in JavaScript lets us easily access ***just one element*** of the web page. It takes **one input**: the ID of whichever HTML element you want to access:

![getelementbyid-example](https://user-images.githubusercontent.com/1555022/41071606-acf9eb58-69ad-11e8-8c71-63ebabdfa948.png)

<br/>

For example, to change the text inside an example paragraph with the ID of `"main"`, we can do this:
  
```javascript
document.getElementById("main").textContent = "This text will overwrite the text of a special paragraph.";
```

<br>

Notice how the `document.getElementById()` function can be ***swapped out*** with `document.body`, like Lego blocks that can fit into the same slot in our code:

```javascript
// Using document.body
document.body.textContent = "This replaces the text of the entire body element.";

// Using the getElementById() function
document.getElementById("main").textContent = "This replaces the text of that special paragraph.";
```

<br/>

![textcontent-example](https://user-images.githubusercontent.com/1555022/41071785-e859b268-69ae-11e8-9f0a-a29b7c902029.png)

<br/>

:bulb: Switching out interchangeable pieces -- like Lego blocks! -- is one of the most fundamental concepts in every programming language. Coding is all about recognizing *which* pieces can be swapped out, *where* they can and can't be used, and *how* to mix and match them to create new things!

<br>

## Challenge 6:

For these next two challenges, **remix this Glitch project: https://glitch.com/edit/#!/js-challenge-dom1**

**Your challenge:** Take a look at the code for this project. There's a bug! Can you fix it?

  > **Hint:** Be sure to check the live web page, the browser console, the HTML file, and the JS file!

<br/>


## Challenge 7:

Next, write three more lines of code in the JavaScript file to accomplish the following:

  1. Change the text of the **red** box to say `"Beep!"`
  
  2. Change the text of the **green** box to say `"Kaboom!"`
  
  3. Change the page heading to say `"I am a JavaScript Jedi Master!"` (Hint: look for the `<h1>` tag in the HTML)

<br/>


## Bonus challenge:

This is a Google challenge! Look online to figure out how to ***change the background color*** of the entire web page, and test it on *any* live website by running the code directly in your browser console. Try it on [Google.com](https://www.google.com/), for example!

<br/>

## Group review:

:star: [**Click here to open a shared Glitch project**](https://glitch.com/edit/#!/join/f282c39a-7953-4184-8963-02463f66049a) that we can all edit together in real time!

**Review challenge:**

  1. Create a new paragraph at the bottom of our HTML file with a unique `id` attribute (you can just use your name)
  2. Then in the JavaScript file, change the `textContent` of your unique paragraph to display a sentence about yourself!
  3. Bonus: use JavaScript to change the background color of your unique paragraph.

<br/>

## Applying our new knowledge:

Let's take another look at our flowcharts outlining the steps of our game and discuss:

  1. Which step of the game can we now implement using our JavaScript code?
  
  2. What's missing? What do we still need to learn how to do in order to implement this feature?


<br/>
<hr/>

:trophy: ***Wonderful!!*** This is a fundamental first step in using HTML and JavaScript together to make truly interactive web pages!

:point_right: **[Next up: .....](#)**
