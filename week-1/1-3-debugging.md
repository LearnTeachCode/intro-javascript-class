# 1.3: Debugging tips and tools

:star: ***Note: Videos covering the material below, and the solution to the Hangman game bug, will be posted a bit later!***

Debugging is one of the most important skills you'll ever need as a software developer! As you've seen, debugging can be *incredibly frustrating!* But learning to embrace that frustration is also a skill that you can practice and get better at.

Debugging and feeling stuck is a *big* part of software development; in fact, it's a common joke among developers to say that they get paid to be frustrated all day long, and every so often they get something working! :laughing: In this section, we'll review some debugging tips, tricks, and tools that can help save you from at least *some* of that frustration.

❓ **If you have any questions,** please ask on the private Slack channel for our class.

:clock2: **Time to complete: about 30 minutes**, or more if you dive deeper into the topics and do your own research, which I always recommend!

:books: **Prerequisites:**
  - First review [everything in section 1 for what we learned in our first class](https://github.com/LearnTeachCode/intro-javascript-class/tree/march-2018/week-1).


**Table of Contents:**  
  - 1.3.1: Common bugs to watch out for
  - Debugging tools to try:
    - 1.3.2: Make use of your text editor's built-in features
    - 1.3.3: Remember, `console.log()` is your friend
    - 1.3.4: PythonTutor helps you visualize your code
    - 1.3.5: Your browser's built-in debugger tool is all-powerful
    - 1.3.6: Code linters can spot bugs for you
  - 1.3.7: Solution to our Hangman game bug (to be posted later!)

<hr/>

## 1.3.1: Common bugs to watch out for

  1. **Typos and capitalization:**<br/>This is the most common cause of bugs, especially when you're a beginner. The `document.getElementById()` function is notorious for this; the `d` in `Id` is lower-case! (See the debugging tools section below for some ways to make these easier to spot.)

  2. **Missing or mismatched punctuation marks:**
  <br/>It's very easy to accidentally leave out the starting or close brackets, as in `{ }` or `[ ]` or `( )`! It's also very easy to lose a quote mark or mismatch them. You can use single (`' '`) or double (`" "`)quotes, but they have to match!

  2. **Counting and "off by one" errors:**
  <br/>A [famous programming joke](https://twitter.com/codinghorror/status/506010907021828096) goes like this: "There are two hard things in computer science: cache invalidation, naming things, and [off-by-one errors](https://en.wikipedia.org/wiki/Off-by-one_error)." :laughing: It's very easy to forget that *computers start counting at zero!* It's also easy to be off by one when writing your loops, so always double-check the starting point and the "keep-going" condition.

  3. **Loading your JS file at the wrong time:**
  <br/>Remember to include that `defer` keyword in your HTML script tag, so your JS file will load *after* your HTML has loaded! Also remember that when you're using libraries, the *order* in which you include those script tags for each JS file does matter!

  4. **Incorrect `id` from your HTML:**
  <br/>This is another example of a JavaScript bug that requires you to check your HTML file too! It's easy to mix up your `id` attributes when accessing parts of your web page using JavaScript. So always double-check! (It can help to include a list of all the `id`s in a comment at the top of your JS file to use as a quick reference.)

  5. **Logic errors:**
  <br/>Double-check the logic in any conditional (`if / else`) statements. The best way to test this is *in isolation*, separated from the rest of your code, with some fake data.
 
  6. **Equality comparisons:**
  <br/>A common bug is to mix up the single equals sign (`=`) with the triple equals sign (`===`). Other bugs can be caused by using the double equals sign (`==`) instead of the triple, so be careful! (For comparisons, just stick with the triple equals sign until you're very comfortable with this topic later on.) The same mistakes can happen with the *"not equal"* comparison operators; again, always use the more strict version (`!==`) for now.

  7. **Missing or incorrect inputs for functions:**
  <br/>Whenever you're using a function, whether it's built-in or a function you created yourself, always check what the *the inputs and the output* should be! What data types are expected for the inputs and for the output of this function? How many inputs are there? (Good documentation is the best remedy to prevent this issue!)

  8. **Doing things in the wrong order:**
  <br/>Sometimes your bug can be found in the *design* of your system, before you even started writing any code! Always refer back to your notes or flowcharts to check if the steps are happening in the right order. Using `console.log()` or other debugging tools to see what's happening and *when* is also very helpful here!

  9. **Variable scope issues:**
  <br/>Always declare you variables *at the top* of any function or at the top of your JavaScript file. And always use `let` instead of `var` at least for now, because that helps with certain bugs too! (We'll learn more about variable scope later, along with some more specific types of bugs related to this topic.)

  10. **Other syntax mistakes:**
  <br/>Especially when you're first learning a programming language, it's very easy to use the wrong punctuation mark or put things in the wrong place. To avoid this, make your own cheatsheets with short examples of all the building blocks you use most often, like variables, conditional statements, functions, loops, etc. (See the debugging tools section below for ways to help here too.)


## Debugging tools to try

There are lots of tools out there to help you hunt down those bugs! Here's an overview of a few of the most common ones, ordered from *easiest to get started with* up to more advanced tools.


### 1.3.2: Make use of your text editor's built-in features

Modern text editors like Visual Studio Code and others make it easier to spot errors with a few built-in features, and you can add more later on by installing various plugins too!

**The first features to remember to use:**

  - **Syntax highlighting** can help you spot typos or missing quote marks, so pay attention to the colors! (For example, strings are a pastel red color by default, and variables are white.)

  - **Autocomplete and "IntelliSense"** features also make it easy for you to avoid typos and save you time by showing a dropdown menu of suggestions for what to type next. (The browser console does this too!)

  - **Detect mismatched brackets** by clicking on one; it will add a subtle white box outlining the starting and ending brackets. This works for curly brackets (`{ }`), square brackets (`[ ]`), and parentheses (`( )`).

  - **Check for typos** in any variable names or strings that you use multiple times in your code by double-clicking on any word; it will highlight *all instances of that word* in your file. That can often help you spot typos; if you expect two words to match but they aren't both highlighted, one of them is spelled wrong!

There are *many other features* built into your text editor, so explore the documentation and tutorials sometime to learn more about what it can do! The [Visual Studio Code documentation website](https://code.visualstudio.com/docs/) has some great information and lots of pictures!


### 1.3.3: Remember, `console.log()` is your friend

  - Use this built-in function throughout your code to see what's happening step by step. When debugging, you're a detective; `console.log()` leaves a trail of breadcrumbs for you to follow!

  - Remember that you can not only `console.log()` strings; you can also log the value of variables, or even evaluate expressions on the spot! **Examples:**

    ```javascript
    let myName = "Liz";
    console.log(myName);
    // Or even better, make your log messages easier to read like this:
    console.log("Value of myName is: " + myName);
    // Or evaluate expressions on the spot!
    console.log(2 > 3);
    console.log(5 + 5 - 1);
    console.log(myName === "Liz");
    ```

  - Use `console.log()` on the first line of your JavaScript file to confirm that the file is being loaded into your web page! **Example:** `console.log("The JavaScript has loaded!");`

  - Even *before* you discover a bug, you can always sprinkle `console.log()` statements throughout your code while you're building your application. That's the easiest way to start to become a [defensive programmer](https://en.wikipedia.org/wiki/Defensive_programming)!
  
  - When in doubt, you can always just log *every single step* in your code and log *every variable that changes over time*! That can help you to better understand your code while you're still learning how it all works, too!

  - Write *clear, plain English* messages for yourself. With a lot of `console.log()`s, you can start to forget what's what. So help yourself out! **Example:**
  
    ```javascript
    console.log("The user guessed this number: " + userInput);
    ```


### 1.3.4: PythonTutor helps you visualize your code

[PythonTutor.com](http://pythontutor.com/javascript.html#mode=edit) is an excellent resource both for debugging and for understanding the flow of your program.

  > Note: The name is misleading; it works for JavaScript and several other languages, not just Python!

**A few features to try out:**

  - You can walk through your code step by step or even *rewind* and go backwards one step at a time. (It'll make you feel like Doctor Who!)

  - It shows you a red arrow to the left of your code, pointing to the line of code that will execute next. (It also shows a light green arrow pointing the the previous line of code that just executed.)
  
  - You can see a list of all the variables being stored in memory and how they change over time.

  - If you accidentally create an infinite loop, PythonTutor *will not* run the code. That's much better than testing loops directly in your project or in your browser console, where an infinite loop will usually crash your browser!


### 1.3.5: Your browser's built-in debugger tool is all-powerful

The debugger tool built into Chrome and all other major web browsers practically gives you super powers! The only downside is that it can feel a bit overwhelming at first; it has so many buttons and menus, it feels a bit like a NASA control center.

:tv: I will post a video reviewing the basics of the debugger tool soon. **For now, see [Chrome's official debugger tutorial video and article](https://developers.google.com/web/tools/chrome-devtools/javascript/) as an extra reference.**

**How to start using the debugger in Chrome:**

  - One way to start the debugger: you can write the word `debugger` in your JavaScript file and the refresh the web page for your project. The debugger should pause your code on whichever line you wrote `debugger`! **Example:**

    ```javascript
    console.log("JS file has loaded!");
    // Make sure you type debugger on its own line, with NO semicolon! 
    debugger
    let x = 3;
    let y = 2;
    console.log(x + y);
    ```

  - Another way: open the developer tools panel while you're on the web page for your project, then go to the "Sources" panel, click on your JavaScript file from the list of files on the left, and then [set breakpoints (see a picture here)](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints#loc) by clicking on any line numbers of your code displayed on the right. Then refresh the page. The debugger will pause on those lines of code!

**Chrome debugger features to try out first:**

  - Test out [setting breakpoints](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints#loc) to pause the code on certain line numbers. Just click a line number next to the code (see instructions above on where to find that), and the line number itself will turn blue to show that it's now a breakpoint. Click again to *remove* the breakpoint.

  - Click the blue arrow (that's the "resume" button) on the top right to resume your code after it has paused. If you set *multiple* breakpoints, it will pause again on the next line of code witha breakpoint.

  - You can see the value of any variables at a particular point in time either by hovering your mouse over the variable name while the debugger has paused your code, or here's a fancier way: [how to "watch" specific variables in the Chrome debugger](https://developers.google.com/web/tools/chrome-devtools/javascript/watch-variables).

  - While your code is paused, you can even switch back to your browser's JavaScript console and type some code in there to test it *while your page is frozen in time*! That code can also affect the web page while it's frozen.

  - Notice that if you set a breakpoint on a line of code *inside a function that waits for an event* (like the user clicking a button), the debugger won't pause the code until that line of code is executed. So you'll only see it pause if you actually click the button yourself.


### 1.3.6: Code linters can spot bugs for you

A [code linter](https://en.wikipedia.org/wiki/Lint_%28software%29) is a tool that analyzes your code and identifies errors, often suggesting style and formatting improvements too! Here are a couple linting tools to try out:

  1. [**JSHint.com**](http://jshint.com/) is an online tool where you can paste in your JavaScript code and it'll identify potential bugs and suggest changes to write better code! This is the easiest way to get started using a code linter. 

  > **Note:** The font on their website is very small by default; press `Ctrl` and the plus sign (`+`) on your keyboard to make the font bigger.

  2. For later on when you want to get fancier, [**ESLint**]() is the most popular JavaScript linter by far (according to the [State of JavaScript 2017 survey](https://stateofjs.com/2017/other-tools/)). But getting it set up on your computer is a bit complicated, so I wouldn't recommend using it just yet.

  3. [**Prettier**](https://prettier.io/playground/) is another tool that formats your code and makes it look pretty! You can [test it out on their website](https://prettier.io/playground/) or install it as a [plugin for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) or other text editors.

