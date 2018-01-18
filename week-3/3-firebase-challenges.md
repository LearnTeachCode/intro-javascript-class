# 3.****: Firebase practice challenges (in class)

Let's tinker with Firebase, jumping in with some practice challenges to learn how to display, add, update, and delete data from our shared Firebase database!

:star: **For the challenges below, first make a remix of this Glitch project (or copy the code into a local file) to use our demo Firebase app: https://firebase-starter1.glitch.me/**

:books: **Resources to use in these challenges:**
  - [Section 3.1: Core functions of the Firebase database library](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md)  
  - [Section 2.2: Intro to objects and arrays](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-2-objects-arrays.md)
  - You can also search for stuff online, especially in the [official Firebase documentation](https://firebase.google.com/docs/reference/js/) (but that might be trickier to navigate)

<hr/>

## Challenge 1: 

There's already a location in the database with *your actual name* as the property name! So for example, if your name is Liz, the **path** to your personal section of our database would just be `"liz"` -- all *lower-case* and only your *first* name.

**Display the value stored in that database location on the page, inside the HTML element with the id of `"yourname"`.**

Be sure to look through [our Firebase notes](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md) and use our example code as a reference for *all* of these challenges!

## Challenge 2:

Below your previous code that displays your name, write **one new line** of code to **update** that same location in the database with a string containing *your actual name*!

## Challenge 3: 
  
Using the code you wrote for challenge 1, now **change one tiny thing** in your code to display the name of your study partner instead of yourself!

## Challenge 4:

  - First, create a **new object** with key-value pairs to specify some information about yourself -- maybe your name, your favorite food, etc.

  - Second, **change one small thing** in your code from challenge 3 to update your database location again, replacing that string containing your name and **overwriting it with the new object** you just created.

  - Third, add one line of code that **logs the value of your data snapshot to the console.** Take a look -- the object you created should now appear in the console, showing all the information you included about yourself!

  - Finally, take a look at your web page again. You should see something like **[object Object]** appear on the page instead of a name. That's how you'll know it worked!

## Challenge 5:

Now change **one more tiny thing** in your code from challenge 4 so that instead of displaying the *whole object* on your web page, just **display the value of one property that's inside your object.* The value should now appear on your webpage instead of [object Object]!

## Challenge 6:

Displaying one value at a time like that is great, but what if you want to display *all the data* inside your object? **Use the `JSON.stringify()` function to convert your entire object into a string**, and then display that string on the web page instead of what you displayed for challenge 5.

  > **Note:** The web browser doesn't know how to display objects automatically if you try to display them using that `textContent` property, so that's why we need to convert our object into a string. Since a Firebase database is just a bunch of JSON (a JavaScript object formatted a certain way), then it's very easy to just use the `JSON.stringify()` function on our data!

### Challenge 7:

Below the code you wrote for the above challenges, next create a new database reference object that represents a path in the database named **"ourlist"**. (It already exists in our shared database.)

Using that database reference object and Firebase's `push()` function, **add a string to that list!** (The string can be anything you want -- bonus points if it's silly or funny, like "Help I'm trapped in a Firebase database factory!")

### Challenge 8:

Now add **one small change** to your code for challenge 7 to **save the result of executing that `push` function into a new variable**. Name your new variable something like `newItemRef` because it will now contain a database reference object pointing to the new value that you just pushed onto the end of our list!

### Challenge 9:

Next, change **one small thing** in your code from challenge 7 and 8 above to **push an object onto the end of our list**. (The object could represent anything -- a penguin, a wizard, a car... again, bonus points for something silly!)

### Challenge 10:

Next, **display our entire list** on your web page inside the HTML element with the id of **"ourlist"**. You can copy-paste from all your previous code to get this working.

Be sure to use `JSON.stringify()` again to see the actual data instead of `[object Object]`!

### Challenge 11:

Phew! Congrats on making it this far! One last easieer challenge. Now that our shared list is full of stuff, **remove the item you just pushed into the list** using that database reference object you saved into a variable for challenge 8.

If you refresh the page, it should now be gone!

:trophy: ***Great job! Now you're practically now a Firebase database ninja!*** You can already start building database-driven apps with these few functions you just practiced using. :)
