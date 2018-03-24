## 4.2: Practice challenges: Functions with inputs (parameters and arguments)

Let's have some more fun with functions! The last time we looked at functions, we just practiced *defining* and *calling* them. Now let's take a look at using *inputs* and *outputs* with our functions!

📺 **Video: Review of Function Basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Planning to remake it later on and fix it up!

:books: **Resources to use in these challenges:**
  - [Section 2.3: Intro to functions with practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-3-function-intro-challenges.md).
  - [Section 5.2: Overview of the return statement and variable scope](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-2-return-and-scope.md)
  - Remember, you can also search for stuff online!

<hr/>

## Recap: How to define and call functions

**Defining functions:** There are ***four parts*** to every function definition:

  1. The `function` keyword
  2. The name of the function (follow same naming rules as variables)
  3. Parentheses containing placeholder names for future inputs (called *parameters*)
  4. Curly brackets containing the code that it will run (called the function body)

**Calling functions** (also called *running*, *executing*, or *invoking* functions):

  1. The name of the function
  2. Parentheses containing any specific inputs (called *arguments*)

<br/>

## Challenge 1:

What's wrong with the code below? Your challenge is to fix it!

```javascript
function (userName) {
  console.log("Welcome, " + userName);
}
```

Once you've solved the bug, try calling the function **three times** with **three different names** as inputs. Be sure to check the console to see if it worked; you should see three diffierent messages, welcoming each new user!

  > **Functions are like reusable templates:** you can write the code once, and use it multiple times. And with inputs, now your functions can accomplish one common task in *many different scenarios!*

<br/>

## Challenge 2:

Define a function that takes one input, subtracts 10 from it, and `console.log()`s the result. Name it whatever you want -- but best to use a descriptive name, and stick to camel case style formatting.

Next, test your function by **calling it three times** with three different numbers as inputs! Be sure to check the console to see if it worked; you should see three diffierent results.

<br/>

## Vocabulary note: Arguments versus parameters

When casually speaking about functions, we use the word ***inputs*** to refer to the values that go into the function (also phrased as "the values that are passed into the function"). But there are two other more *technical* and *specific* terms that you'll hear: ***arguments*** and ***parameters***.

  - A **parameter** is a *placeholder* used to represent an input inside a ***function definition***. The parameters represent values that have not been defined yet.
  
  - An **argument** is an *actual value*, a piece of data, that is passed into a function ***when you run the function***. Arguments *replace* the parameters (placeholders) in the function definition.
  
So remember: parameters are part of the *first stage* when you *define* a function, and arguments are part of the *second stage* when you *run* a function.

***Example:***

```javascript
// 3 PARAMETERS, placeholders that will be replaced with the actual values later:
function displayThreeWords (word1, word2, word3) {
	console.log(word1 + ' ' + word2 + ' ' + word3);
}

// 3 ARGUMENTS, specific values:
displayThreeWords('pineapple', 'motorboat', 'toothbrush');
```

:star: **Here's a handy way to remember it:**

  - The ***parameter*** is the ***parking space*** (a placeholder, an empty space).
  - The ***argument*** is the ***automobile*** (that parks in the empty space).

<br/>

## Challenge 3:

Define a function that takes **two parameters**, adds them together, and `console.log()`s the sum. Again, name the function whatever you want, but be sure to use a descriptive name!

Next, test your function by **calling** it a couple times, using **two arguments** each time you call the function.

<br/>

## Challenge 4:

Define a function that takes **five parameters**, but it should only use **one** of them, logging just *one* of those input values to the console.

What do you think will happen when you call this function? Any errors? Try it!

<br/>


## Challenge 5:

Define a function that takes **one parameter**, multiplies it by 100, and displays the result in the console.

If you then call the function with **three arguments**, do you think you'll get any error messages or weird bugs? Try it!

<br/>

## Bonus challenge 1:

Define a function that takes **three strings** as input and console.log()s an ***array*** that contains those three strings. Test that it works in the console!

<br/>


## Bonus challenge 2:

Define a function that takes two inputs: an **object** and a **string**. The function should *create a new key-value pair* inside the provided object, with the key/property name of `"myNewProperty"` and its corresponding value should be the given string. Finally, this function should display the entire object in the console.

  > **Hint:** Remember, you can always review [section 3.2: Intro to objects with practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-3/3-2-object-challenges.md) for example code snippets!

</br>



<hr/>

:trophy: ***Great job!*** Understanding how to use inputs with functions will make all the difference in your programming skills. There's a lot more to learn of course, but knowing the very basics is half the battle!
