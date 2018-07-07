# Section 1.9: Putting it all together to build Dragon Defeater!

After diving into the Document Object Model, using the browser console, working with the different data types of strings and numbers, and storing variables in the computer's memory... we're *almost done!*

The only piece remaining is a more complex topic: *how to know when the user clicks that button!* 

 <hr/>

## A preview of event listeners

Events and event listeners allow you to **respond to user input, like when the user clicks on a button (among many other types of events)**. The event listener tells a section of your code to ***wait*** until a particular event occurs.

<br/>

Web browsers provide a built-in JavaScript function named **`addEventListener()`**, which is available on *any* element of the web page. So *anything* on a web page can respond to various actions from the user!

<br/>

Before we dive in, let's try out an example.

<br/>

⭐️ **Open your personal copy of our HTML mockup for our game on Glitch**, or if you lost track of the link, feel free to [**click here and make another remix of it**](https://glitch.com/edit/#!/dragon-defeater-v0-starter).

</br>

Copy-paste the code below into your `script.js` file. Then click "Show Live" to view the live web page, and then open the browser console while you're looking at the live page.

```javascript
document.getElementById("defeat").addEventListener("click", logClick);

function logClick () {
  console.log("This message should appear in the browser console!");
}
```

<br/>

After running the code...

<br/>

Nothing happens! Why's that? 

<br/>

***...because the event hasn't been triggered yet!***

<br/>

To trigger the event, ***click on the button***. Then look inside the console. You should see a message show up in your console when you click!

<br/>

## Group coding challenge: Building the Dragon Defeater game!

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/f282c39a-7953-4184-8963-02463f66049a) that we can all edit together in real time!

<br/>

**Recap of feature requirements:**

  - There should be a button that the user can click on.
  
  - And there should be a paragraph that says how many times the button was clicked.
  
  - Every time the user clicks that button, the number of clicks should increase by one, and that new number should be displayed in the paragraph described above. The paragraph should say something like `"Dragons defeated: 27"`
  
  - Initially, that paragraph should say `"Dragons defeated: 0"`.
  
  - ... and that's all! Super simple!

<br/>

**We'll take turns writing code together in the same JavaScript file (see the link to our shared group project above), combining the event listener code above with everything that we've learned so far.**

<br/>

:books: **Note:** It's totally OK -- and *often necessary* -- to use some code before you fully understand it. That's just part of the learning process. We will spend more time learning about event listeners in details in our next class.

But for now, we're practicing a very important skill: taking a piece of working code and figuring out ***which part*** to change, in order to make it work *slightly* differently.

<br/>
<hr/>

:trophy: **Great job, team!** As you can see, even building a *very simple* (and very boring) game still has quite a few moving parts, and it touches on a lot of very big computer science topics.

:point_right: **In our next class**, we'll learn more about event listeners to respond to all sorts of user input!
