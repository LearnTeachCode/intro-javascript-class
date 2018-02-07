# 3.3: Firebase practice challenges

Let's tinker with Firebase, jumping in with some practice challenges to learn how to display, add, update, and delete data from our shared Firebase database!

:star: **For the challenges below, first make a remix of this Glitch project (or copy the code into a local file) to use our demo Firebase app: https://firebase-starter1.glitch.me/**

:books: **Resources to use in these challenges:**
  - [Section 3.1: Core functions of the Firebase database library](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md)  
  - [Section 2.2: Intro to objects and arrays](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-2-objects-arrays.md)
  - You can also search for stuff online, especially in the [official Firebase documentation](https://firebase.google.com/docs/reference/js/) (but that might be trickier to navigate)

<hr/>

## Challenge 1: 

There's already a location in the database with *your actual name* as the property name! So for example, if your name is Liz, the **path** to your personal section of our database would just be `"liz"` -- all *lower-case* and only your *first* name.

**Get the value stored in that database location (described above) and display it on the page, inside the HTML element with the id of `"yourname"`.** You'll know you got it working if you get your web page to display `"put your name here"`, because in challenge 2 you'll replace that value with your actual name.

Be sure to look through [our Firebase notes](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md) and use our example code as a reference for *all* of these challenges!

## Challenge 2:

Below your previous code that displays your name, write **one new line** of code to **update** that same location in the database with a string containing *your actual name*!

:star: **Important thing to avoid:** Please *do not* put this line of code inside any of your previous functions; make sure it's ***outside*** any functions and just put it at the very bottom of your JavaScript file.
  > Why? Because adding/updating/removing data triggers the `"value"` event, so if you were to put the add/update/delete instruction *inside* the function that's called any time the `"value"` event is triggered, then you'll create an infinite loop that might seriously slow down or crash our database!

## Challenge 3:

  - First, create a **new object** with key-value pairs to specify some information about yourself -- maybe your name, your favorite food, etc.

  - Second, **change one small thing** in your code from challenge 2 to update your database location again and **set the value to your new object**, overwriting the string you wrote containing your name for challenge 2.

  - Third, add one line of code that **logs the value of your data snapshot to the console.** Take a look -- the object you created should now appear in the console, showing all the information you included about yourself!

  - Finally, take a look at your web page again. You should see something like **[object Object]** appear on the page instead of a name. That's how you'll know it worked!

## Challenge 4:

Now change **one more tiny thing** in your code from challenge 3 so that instead of displaying the *whole object* on your web page, just **display the value of one property that's inside your object.** The value should now appear on your webpage instead of [object Object]!

## Challenge 5:

Displaying one value at a time like that is great, but what if you want to display *all the raw data* inside your object? **Use the `JSON.stringify()` function to convert your entire object into a string**, and then display that string on the web page instead of what you displayed for challenge 4.

  > **Note:** The web browser doesn't know how to display objects automatically if you try to display them using that `textContent` property, so that's why we need to convert our object into a string. Since a Firebase database is just a bunch of JSON (a JavaScript object formatted a certain way), then it's very easy to just use the `JSON.stringify()` function on our data!

### Challenge 6:

Below all the code you wrote for the above challenges, at the very bottom of your file, create a new database reference object that represents a path in the database named **"ourlist"**. (It already exists in our shared database.)

Using that database reference object and Firebase's `push()` function, **add a string to our list!** (The string can be anything you want -- bonus points if it's silly or funny, like "Help I'm trapped in a Firebase database factory!")

:star: **Important thing to avoid:** Again, please *do not* use the `push()` function inside any of your previous functions; make sure it's ***outside*** any functions and just put it at the very bottom of your JavaScript file.

  > **Note:** Every time you refresh your web page, your code will push that same string to the end of our shared list in the database *over and over again.* And since this is a shared list, you'll see *everyone else's values* in the list too, updating in real time!  

### Challenge 7:

Now add **one small change** to your code for challenge 6 to **save the result of executing that `push` function into a new variable**. Name your new variable something like `newItemRef` because it will now contain a database reference object pointing to the new value that you just pushed onto the end of our list!

### Challenge 8:

Next, change **one small thing** in your code from challenge 6 and 7 above to **push an object onto the end of our list**. (The object could represent anything -- a penguin, a wizard, a car... again, bonus points for something silly!)

### Challenge 9:

Next, **display our entire list** on your web page inside the HTML element with the id of **"ourlist"**. You can copy-paste from all your previous code to get this working.

Be sure to use `JSON.stringify()` again to see the actual data instead of `[object Object]`!

### Challenge 10:

Phew! Congrats on making it this far! Now that you've probably messed up our shared app, hide the evidence and remove yourself from the database by **deleting the location specified by the path that contains your first name**. For example, the path for my database location would have been `"liz"`. (This is the section of the database you used for challenges 1 through 5.)

Once you successfully delete it, if you refresh the web page, the second paragraph should now go back to displaying `"... your name from Firebase will appear here ..."`

:trophy: ***Great job! Now you're practically a Firebase database ninja!*** You can already start building database-driven apps with these few functions you just practiced using. :)
