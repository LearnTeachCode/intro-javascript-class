# Section 1.6: Using the browser console

Now that we've learned the very basics of how to display new information onto a web page using JavaScript, we're one step closer to finishing our Dragon Defeater game!

In this next set of coding challenges, we'll take a little detour to learn about a built-in function that can make our lives as developers *much, much easier!*

<hr/>

## Review and group discussion:

Let's take a closer look at what we've learned so far and discuss it from a different perspective:

  1. In our previous practice challenges, what was the information or the ***data*** that we were putting into our code?
  
  2. ***Where*** did the data come from, and where did we send it?

<br/>

Next, let's tinker with a new function that will let us display our data somewhere else!

<br/>

## Challenge 1:

⭐️ **Open your personal copy of our HTML mockup on Glitch** or if you lost track of the link, feel free to [**click here and make another remix of it**](https://glitch.com/edit/#!/dragon-defeater-v0-starter).

<br/>

Before anything else, take a look at the code below and ***make a prediction*** about what you think each line of code will do:

```javascript
document.getElementById("outcome").textContent = "hi!";

console.log("hi!");
```

<br/>

***Before* you run the code, discuss:**

  1. What's the ***data*** that we're sending to the computer in both lines of code?
  
  2. What's the difference between the first line and the second line?
  
  3. ***Where*** will the data be sent to, for each line of code?

<br/>

Finally, ***paste the code*** into your JavaScript file! Next, we'll take a look at where it's being sent.

<br/>


## How to open your web browser's JavaScript console

:tv: You can also review our **4 min video on the console in Chrome: https://youtu.be/O_sJE_3jKZ4**

<br/>

**Keyboard shortcuts to open your browser's console:**

|  | Chrome | Firefox | Safari |
| --- | ---- | ---- | ---- |
| **Windows:** | Ctrl + Shift + J | Ctrl + Shift + K | |
| **Mac:** | Cmd + Opt + J | Cmd + Opt + K |  Cmd + Opt + C |

<br/>

Once you have the code from challenge #1 above pasted into your JavaScript file, click **"Show Live"** at the top left of the Glitch code editor and then look at the live web page. Do you see your data on the page?

Next, **open the console** while you're looking at the live web page. Do you see your data there too?

<br/>

:star: As you can see, **the `console.log()` function allows us to display any data inside the web browser's console.**

<br/>

So our code `console.log("hi!")` displays (or ***logs***) the data `"hi!"` inside the console:

![consolelog-hi](https://user-images.githubusercontent.com/1555022/41071035-d340ea9e-69aa-11e8-9585-a0477f15fa46.png)

<br/>

## Challenge 2:

Let's discuss:

  1. Why do you think `console.log()` would be useful?
  
  2. What's an example of some data that you'd want to display on the web page, and why would you want to put it there?
  
  3. And what's an example of some data that you *wouldn't* want to display on the web page? Why not?
  
  4. Aside from these two options, *where else* could we put or send our data? (There are *lots* of other options!)

<br/>

## Challenge 3:

There's a bug in the following code. Before you run it, make a prediction:

  1. What do you think the problem is?
  
  2. Will the browser give you an error message? If so, what do you think the error will say?
  
  3. Why would this code confuse the web browser?

<br/>

```javascript
console.log(hello);
```

<br/>

Then ***run the code*** by copying it into your JavaScript file in the Glitch code editor, open the live page by clicking "Show Live", and open the console while you're looking at the live page.

<br/>

Were your predictions correct? Now, solve the bug! Test it again to make sure it works.

<br/>

## Challenge 4:

Here's another bit of broken code. Make a prediction first, discuss it, and then test the broken code. After all that, the last step is to fix it!

```javascript
Console.log(hello);
```

<br/>

## Challenge 5:

Another quick bug:

```javascript
consolelog(hello);
```

<br/>

## Challenge 6:

Yet another bug. For this one, first **discuss:**

  1. What error message do you think you'll see?
  
  2. Will it be different from the previous error messages? Why or why not?

<br/>

Then run the broken code below, and look inside the console again to see if your predictions were correct:

```javascript
console.log "hello";
```

<br/>

Finally, fix it!

<br/>

## Challenge 7:

OK, one last bug! Once again, first **discuss:**
  
  1. Will this give a different error compared to the previous bugs? Why or why not?
  
  2. What do you think the console will show?
  
  3. How is this code different from the previous examples?
  
  4. Compare this to the code we used in our previous section to display text on the page. How is it similar, and how is it different?

<br/>

Then run broken code below, and look inside the console:

```javascript
console.log = "hello";
```

<br/>

Why do you think it worked that way?


<br/>
<hr/>

:trophy: ***Congrats!*** The browser console and the `console.log()` function are a couple of the most useful tools that you'll be using to inspect data in your application and "look under the hood" to see how your code is working.

:point_right: ***Next up: [section 1.7](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-1/1-7-data-types.md)!***

