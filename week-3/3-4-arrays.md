# Section 3.4: Intro to arrays

An array is an *ordered list* of things. They can contain any type of data: numbers, strings, Booleans, objects, other arrays, etc. But as we discussed earlier, arrays and objects have different pros and cons.

<br/>

:tv: **Video: Intro to arrays (6 min): https://youtu.be/QlfR6ICa3gQ**

  > **Note:** This is also an older video, which is why you'll see `var` instead of `let`. Planning to remake this one later too.

<br/>

In these next challenges, let's take our first look at creating and working with arrays!

<hr/>


## Challenge 1:

Let's do a little Googling! Look up how to create an array in JavaScript. (There's always more than one way to do something, but use whichever example looks the most simple and straightforward.)

As always, for any code snippets you find online, test them out to make sure that you understand how they work!

<br/>

## Challenge 2:

Create an array containing a list of three of your favorite movies.

Then display the whole array in your browser console. (Take a look in the console to see how it conveniently displays arrays!)

<br/>

## Challenge 3:

First, make a prediction: if you create an array that contains a string, a number, and a Boolean (all in the same array), will the web browser give you an error? If so, what do you think the error message will say?

Then try it out to see what happens!

<br/>


## Array elements and indexes:

:star: The things inside an array are called ***elements***, and they each have a number assigned to them, called the ***index***.

Computers start counting at zero, not at one! (This goes *way* back to the early days of computing.) So **the first element of an array has an index of 0.**

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/CPT-programming-array.svg" width=240/></p>

  > **Fun tangent:** [See this forum discussion for some interesting reasons why computers start counting at zero!](https://superuser.com/questions/578292/why-do-computers-count-from-zero)

<br/>
  
:star: **To access an element in an array:** We type the name of the array followed by a pair of ***squarebrackets*** (`[]`), with its index number inside the brackets.

<br/>

  > **Note:** We can't use dot notation with arrays, unfortunately! So `myArray.0` won't work!<br/><br/>**Fun fact:** But you *can* use bracket notation with any object! 

<br/>

## Challenge 4:

Using your array of favorite movies:

  1. Display the ***second element*** in the browser console.

  2. After that, write one line of code to ***change*** the value of that second element, assigning it the string `"Sharknado"` as its new value.

  3. And finally, log the second element of your array to the console again (exactly as you did in step 1).

<br/>

Did your array change as expected?

<br/>

## Challenge 5:

To find out how many elements are inside an array, just type the name of the array followed by `.length`! Test this out by telling the console to display the length of your array of favorite movies.

<br/>

  > **Note:** You may have noticed the *dot syntax* here works the same way as with our objects! That's because arrays are also objects -- just a special type of object with its own special syntax! Under the hood, arrays have lots of built-in variables (like the `length` property) as well as built-in functions, as we'll see later!

<br/>

## Challenge 6:

Anywhere you can use a literal value (like `3` or `"hi"`), you can also use the name of a variable! This will be *super important* when you're working with arrays in more advanced ways later on.

<br/>

**Your challenge:** 

  1. Create a variable named `myIndex` that contains the index number of the *third* element in your array.
  
  2. Then access an element from your array of favorite movies using `myIndex` *instead* of directly using a number.

<br/>

## Challenge 7:

Time for another Google challenge! How do you add a new item onto the end of an array? Find some sample code and test it out.

Then use what you found to **add another movie** to the end of your array of favorite movies.

<br/>

  > Remember to use the console to check if it worked! You can display arrays using `console.log()` just like you can with any other data type.

<br/>

## Bonus challenge 1:

Pretend you're building a social network site, and you have an array that contains a list of all the users. At any point in time, new users can sign up and be automatically added to the end of that array. So the length of this array is constantly changing!

<br/>

**Your challenge:** How would you access the most recent user who signed up for your social network site? In other words, how do you access the ***last element*** of an array in a way that would work for ***any*** array, of ***any size***?

<br/>

  > **Hint:** This requires a teeny tiny bit of math! But everything you need to solve this is here on this page. Solving bonus challenge #1 above might also make this easier.

<br/>

## Bonus challenge 2:

Create an example of an ***array inside an array***, like a list of recipes where each recipe is a list of its step-by-step instructions.

<br/>

## Bonus info:

Watch [this famous talk named "Wat", presented by Gary Bernhardt](https://www.destroyallsoftware.com/talks/wat). It's a very famous 5-minute talk that takes a hilarious look at the quirks of two popular programming languages: Ruby and JavaScript.

The JavaScript part is at the end. Bonus points if you try running some of his code examples in your browser console!

<br/>

## One more bonus:

Back in the days of Shakespeare, people used to say "Huzzah!" to celebrate things. Most people I know just say "Yay!" or "Woohoo!" So... how do you think programmers shout for joy?

<br/>

... *wait for it* ...

<br/>

... *scroll down* ...

<br/>

... *a bit more* ...

<br/>

... *keep going* ...

<br/>

They type `["hip", "hip"]` -- a "hip hip" *array!* :laughing:

<br/>

<hr/>

🏆 ***Wonderful!*** You can now work with lists of data like a pro!

:point_right: **Next up:** [....](#)

