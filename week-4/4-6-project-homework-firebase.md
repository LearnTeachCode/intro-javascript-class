# 4.6: Adding Firebase to your own project

After experimenting with Firebase in our previous classes, it's time to start using Firebase in your own project to persistently store some data! 

  > **Note:** If you've already successfully integrated Firebase with your personal project, feel free to skip this assignment and focus on other parts of your project. (As always, we're here to help!)

<br/>

:books: **Review materials:**

  - [Section 2.5: Database reference objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md)
  - [Section 3.2: Displaying data using the Firebase `.on` event listener](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-2-firebase-event-listener.md)
  - [Section 3.3: Adding, updating, and deleting data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-3-firebase-set-remove.md)

<hr/>

## Setting up Firebase

If you haven't already, **refer to the steps in [section 2.7: setting up your own Firebase app](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-7-firebase-setup.md)**

**Recap:**

  - Make sure you have a project set up in the Firebase console with the security permissions set to "developer mode" (so anyone can read/write to your database).
  
  - In your HTML file, you'll need to include the `<script>` tag pointing to the JavaScript file for the Firebase library.
  
  - At the top of your JavaScript file, include the Firebase initialization code.

<br/>

## Challenge 1:

Identify ***one user input*** from your project. If you don't have any user inputs yet, create one just to test this out! For example: the user's name.

Create an HTML input box (and give it an `id`!) for the user to type their input.

<br/>

## Challenge 2:

Identify the event that you'll need to access that user input, and identify your function that will be triggered by that event. (If you don't already have this, create it now!)

For example: set up an event listener that calls a function when the user clicks a button on your page to indicate that they've finished entering their input.

<br/>

## Challenge 3:

Decide on a location in your Firebase database to store this user input. For now, just pretend that you're the *only* user of your app. You can store this piece of information anywhere you want; just make sure the ***key*** is descriptive of the data that will be stored there.

Create a ***database reference object*** that represents that location in your database. 

  > Just make this a global variable for now.

<br/>

:books: **Review:** [Section 2.5: Database reference objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md)

<br/>

## Challenge 4:

Inside your function that's triggered by the event, add one more line of code (in addition to your line using `console.log`) to ***save the user's input value into Firebase!***

  > **Hint:** Use the Firebase `.set()` function on your database reference object.

<br/>

:books: **Review:** [Section 3.3: Adding, updating, and deleting data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-3-firebase-set-remove.md)

<br/>

## Challenge 5:

Set up a Firebase event listener so that whenever the value of your data is updated, display the value of that data in the console.

  > You can just put this code at the very bottom of your file, outside of any other functions.

<br/>

:books: **Review:**
  - Feel free to copy from the working code provided at the end of [section 2.7: setting up your own Firebase app](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-7-firebase-setup.md)!
  
  - See also: [section 3.2: Displaying data using the Firebase `.on` event listener](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-2-firebase-event-listener.md)

<br/>

## Challenge 6:

Test it out! Try typing in some new user input while you have the browser console open on that page, click the button, and it should save the new data to Firebase which will then trigger your Firebase event listener to display the new value in the console!

<br/>

## Challenge 7:

Finally, you can sync the user input box with the latest data from your Firebase database! 

Inside the function triggered by your Firebase event listener, where you're using `console.log` to display the data, ***add one more line of code to change the `.value` property of the input box HTML element, and assign it the value from Firebase.***

<br/>

  > **Hint:** So whatever you used as *input* for your call to `console.log`, that should be the exact same value on the *right* side of the equal sign in your next line of code.

<br/>
<hr/>

:trophy: ***Great work!*** Keep tinkering with your project, and reuse these building blocks in different ways to save and display *more* data to your Firebase database.

**In our next class:** we'll take a closer look at APIs and if we have time, we'll also work on setting up a user login system with Firebase.
