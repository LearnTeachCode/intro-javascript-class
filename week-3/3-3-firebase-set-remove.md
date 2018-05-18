# 3.3: Intro to Firebase challenges: Adding, updating, and deleting data

Compared to [displaying data (which we learned about in the previous section)](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-2-firebase-event-listener.md), modifying data in Firebase is *much* easier!

<hr/>

<br/>

## Challenge 1:

Let's start with an internet scavenger hunt for a few minutes! Look around online and see if you can find the names of the Firebase functions that we need for each of the following:

  - Updating a piece of data to a new value
  - Deleting a piece of data
  - Adding a new piece of data

<br/>

## Challenge 2:

For these next challenges, we'll be using a new section of our shared Firebase database that looks something like this:

```javascript
{
  students: {
    studentname1: "This placeholder string for STUDENTNAME1 is stored in Firebase!",
    studentname2: "This placeholder string for STUDENTNAME2 is stored in Firebase!",
    studentname3: "This placeholder string for STUDENTNAME3 is stored in Firebase!"
  }    
}
```

But instead of `"studentname1"` etc, there's a database location where the ***key*** is ***your first name!***

<br/>

**Your challenge:** In the same Glitch project that you used for the previous challenges, change ***one tiny piece*** of your code so that instead of displaying the penguin's name on the web page, it should display `"This placeholder string for **STUDENTNAME1** is stored in Firebase!"` (but instead of `"STUDENTNAME1"` you should see your actual name).

  > **Hint:** in your code, replace the penguin-related path with the path that points to your first name.

  > If you're working in pairs, test this with *both* of your names!

<br/>

## Challenge 3:

Rename your variables so that they actually make sense again -- you're not a penguin! (Or are you?)

  > We call this ***refactoring***: cleaning up your code so that it's more readable and well-organized, *without* changing the functionality.

<br/>

## Challenge 4:

Use the [Firebase `set()` function](https://firebase.google.com/docs/reference/node/firebase.database.Reference#set) to ***change*** the message associated with your name -- make it say something about yourself!

<br/>

⭐️ **Important warning:** Please *do not* put this line of code inside any of your previous functions; make sure it's *outside* any functions, and just put it at the very bottom of your JavaScript file.

  > Why? Because adding/updating/removing data triggers the "value" event that we've been using! So if you were to put the add/update/delete instruction inside the function that's triggered by the "value" event, then you'll create an infinite loop that might seriously slow down or crash our database!

<br/>

**About `set()`:**

This function writes data to the location specified by a database reference object. If the specified location in your database doesn't exist, `set()` will create it; otherwise, if it *does* already exist, `set()` will update (overwrite) the data at that location.

It takes **one input**, which can be a string, number, Boolean, or an entire object!

**Example of updating a piece of data using `set()`:**

```javascript
// Create a database reference object for the canFly property of penguin #1152
let penguinNameRef = firebase.database().ref("penguins/1152/canFly");

// Change its name to the Boolean value of true:
penguinNameRef.set(true);
```

<br/>

## Challenge 5:

Next, use the Firebase [`remove()` function](https://firebase.google.com/docs/reference/node/firebase.database.Reference#remove) to delete yourself from the database!

  > Don't worry, we'll bring you back to life in the next challenge. :)

<br/>

**About `remove()`:**

 This function does exactly what you'd expect: it removes data from a location specified by a database reference object.

**Example of removing a piece of data with `remove()`:**

```javascript
// Create a database reference object for the name of penguin #1152
let penguinNameRef = firebase.database().ref("penguins/1152/name");

// Remove this penguin's name entirely:
penguinNameRef.remove();
```

Refresh the page, and see what happens -- your message should now be gone from the page.

<br/>

## Challenge 6:

Use the `set()` function again to add yourself back to the database!

  > **Hint:** The code will be exactly the same as how you *changed* the message associated with your name.

<br/>

## Group coding challenge:



<br/>

## Bonus challenge 1:

Create a JavaScript object that represents some information about yourself, and then use `set()` to assign *that entire object* into the database location for your name. 

Be sure to use `console.log()` to inspect the value of the data -- you should see your object!

And when you try to display that entire object on the web page, you'll see something that came up in our previous class: the web page will show `[Object object]` again.

<br/>

## Bonus challenge 2:

Using what we learned in our last class, fix your code so that the web page will display *all the data inside your object* instead of `[Object object]`.


<br/>

<hr/>

:trophy: ***Woohoo!*** ......

**Next up:** ....
