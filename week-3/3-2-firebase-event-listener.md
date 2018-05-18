# 3.2: Intro to Firebase challenges: Displaying data using the Firebase `.on` event listener

Now that we've [reviewed event listeners in the previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-1-event-listeners-review.md), you'll see that Firebase event listeners will look very familiar!

To read data from our database, we need to use a special **event listener** provided by Firebase. Why an event listener and not just a simple function? Because Firebase updates the data ***in real time***, which means that if the data changes, Firebase can instantly update that data on your web page! (This makes it pretty easy to make apps like chat rooms and multiplayer games!)

:star: **The main Firebase event listener we'll be using has a very short name: `on()`. So when working with Firebase events, we use `.on()` instead of `.addEventListener()`.**

<br/>

To recap, there are **four key concepts for accessing data from Firebase:**

  1. [**From section 2.4:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md) Determining the **path** to your data's location in the database
  2. [**From section 2.5:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md) Creating a **reference object** in your JavaScript code, which represents a database location (a chunk of data)
  3. Setting up Firebase **event listeners** to retrieve the data from your database (which also updates in real time!)
  4. Using the **data snapshot** object to extract the **value** of the data

Last week we covered the first two steps, so now let's work on the last two steps!

<hr/>

## Challenge 1:

**Remix this Glitch project: https://glitch.com/edit/#!/firebase-practice-3**

First, take a look at the JavaScript code: lines 16 to 18 should look familiar from last week, where we create a *database reference object* the represents the part of our database with the path `"penguins/7344/name"`.

Lines 26 to 30 should *also* look familiar -- that's the exact same code we've been using to set up an event listener!

<br/>

**Your challenge: replace the code in lines 26 to 30, turning it into a Firebase event listener piece by piece:**

  1. Replace `document` on line 26 with the name of our database reference object.
  
  2. Replace `addEventListener` with `on`, which is the name of Firebase's event listener function.
  
  3. Replace the type of event with the string `"value"` -- this is the name of the main Firebase event that we need to access our data!
  
  4. This part is optional, but to make our code easier to read, rename the `event` parameter to instead be called `dataSnapshot`.

<br/>

**The end result:** If you open the live web page and then open your browser console, you should see an object appear -- it's probably just named `t` -- and if you expand it, you'll see lots of other information inside! If you dig deep enough, you'll find the actual penguin's name, which in this case is "Fred".

<br/>

## Challenge 2:

For this challenge, you'll need two sheets of paper and four colored markers!

**Part A:**

  1. One person will write (on paper, in ***large letters!***): the original code we've been using to set up an event listener (using `addEventListener`).
  
  2. The other person will write (also on paper, also in large letters!): the *new* code we just created in the previous challenge, using Firebase's `on` event listener funtion to access data from our database.
  
**Part B:**

Answer the following questions by circling pieces of the code on ***both sheets of paper***:

  1. **Circle in red:** Where is the event happening? (Which part of the web page, or which part of the *database*?)
  
  2. **Circle in blue:** Which event are we listening for? (What's the string that contains the type of event?)
  
  3. **Circle in green:** What should happen when the event occurs? (What function gets triggered by this event?)
  
  4. **Circle in black:** What is the function parameter that represents information about the event?

Your circled answers should be mirrored on both pieces of paper, showing how both code examples follow the same overall pattern!

<br/>

## Extracting the value of our data with the `dataSnapshot.val()` function:

We still have one very important little problem to solve in our code for displaying Firebase data: the object containing information about the event -- which we represent with the parameter `dataSnapshot` -- is *kind of a mess!*

Most of the time, we don't want all the other information contained inside that object; we usually just want ***the value*** of our data, nothing else! In this case, we just want the name of the penguin, which is `"Fred"`.

:star: **Firebase requires *one extra step* compared to our previous event listener example: we need to *extract the value* out of the `dataSnapshot` object.**

To do that, we need to use Firebase's `.val()` function like this: `dataSnapshot.val()`

```javascript
// This function will run any time the Firebase "value" event is triggered
// for our particular reference object (the name of penguin #1152):
function logSomeData (dataSnapshot) {

  // EXTRA STEP: Extract the actual data and save it to a local variable
  let penguinName = dataSnapshot.val();
  
  // Display the VALUE itself in the console:
  console.log(penguinName);
}
```

<br/>

## Challenge 3: 

Fix the code in your Glitch project from the previous challenges so that ***only the penguin's name*** appears in the console. (So you should see `"Fred"` appear in the console.)

<br/>

## Challenge 4: 

Now, let's finally display the penguin's name on the web page itself! Follow the steps below if you need some hints:

  1. What's the ID of the paragraph that should display our data?
  
  2. Create a JavaScript object to represent that paragraph.
  
  3. In the same section of code where we were using `console.log()`, change the text inside that paragraph so that its new value becomes the name of our penguin!

<br/>

## Recap:

So now we've covered those **four key concepts for accessing data from Firebase:**

  1. [**From section 2.4:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md) Determining the **path** to your data's location in the database
  2. [**From section 2.5:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md) Creating a **reference object** in your JavaScript code, which represents a database location (a chunk of data)
  3. **Today:** Setting up Firebase **event listeners** to retrieve the data from your database (which also updates in real time!)
  4. **Today:** Using the **data snapshot** object to extract the **value** of the data

<br/>

<hr/>

:trophy: ***Great work!*** Working with event listeners *is not easy*, so congratulations on digging into a challenging topic! Good news is, modifying data in our Firebase database is *much* easier than what we've just been working on.

**Next up:** [in section 3.3, we'll learn how to add, update, and delete data from our Firebase database](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-3-firebase-set-remove.md)!
