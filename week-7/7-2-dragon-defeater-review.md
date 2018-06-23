# 7.2: Firebase review: Building a collaborative "Dragon Defeater"

Let's review what we've learned so far about Firebase to update our first group project, the Dragon Defeater game!

<br/>

:books: **Review materials:**

  - [Section 2.4: Accessing Firebase data with paths](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md)
  - [Section 2.5: Database reference objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md)
  - [Section 3.2: Displaying data using the Firebase `.on` event listener](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-2-firebase-event-listener.md)
  - [Section 3.3: Adding, updating, and deleting data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-3-firebase-set-remove.md)

<hr/>

## What are we building?

:hammer: Let's add some Firebase magic to make our "dragon defeater" game collaborative, so *anyone* can increase the number of dragons defeated and we can all keep track of the total score!

<br/>

:star: **[Click here to edit our project on Glitch and code with us!](https://glitch.com/edit/#!/join/ba450900-3285-4094-b8d7-a337c8421e4b)**

<br/>


## Let's build it!

We already have our code from the previous version of our game, which lets us click the button and increment the score. Let's add a couple Firebase functions to make it collaborative!

<br/>

  :heavy_check_mark: 1.  *Already finished:* Link our web app to our Firebase database (see [section 2.7: setting up your own Firebase database](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-7-firebase-setup.md)).

<br/>

  :heavy_check_mark: 2. *Already finished:* Set up our shared Firebase database with a location containing the initial score.
 
 <br/>
 
  3. Identify the ***path*** in the database for our score.
  
  <br/>
  
  4. Create a ***database reference object*** using that path, and save it to a new variable.
  
  <br/>
  
  5. Set up a ***Firebase event listener*** that calls a function (which we'll create later), triggered by the `"value"` event which happens when the page loads *and also* any time the value of our score in the database changes.
  
  <br/>
  
  6. Define a new function that handles the updated value from Firebase -- give it a descriptive name!
  
  <br/>
  
  7. Give that function definition ***one parameter*** named `dataSnapshot`, which is a placeholder for the messy data that Firebase sends us in an object full of all sorts of weird stuff. (lol)
  
  <br/>
  
  8. Inside our new event handler function, call the Firebase function `dataSnapshot.val()` to convert the messy data object into the actual value we want from our database -- in this case, just a number representing our current score!
  
  <br/>
  
  9. Call `console.log()` inside our event handler function to display our updated score in the browser console.
  
  <br/>
  
  10. Test that the event listener works by manually changing the data in the Firebase console, and see if the new data instantly appears in the browser console -- for *everyone*, in real time!
  
  <br/>
  
  11. Inside our event handler function, update our `dragonsDefeated` variable, assigning it a new value: the ***output*** of calling `dataSnapshot.val()`! This way, our game's ***local state*** will always stay in sync with the database -- *for everyone who plays the game!*
  
  <br/>
  
  12. Modify our *other* event handler function so that whenever *anybody* clicks the button, in addition to increasing the score by one, we should also ***insert*** the new score into the database.


<br/>
<hr/>

:trophy: **Fantastic!** We've built a collaborative, real-time game that anybody on the internet can play together. It's all of humanity versus the dragons! (I think we'll win.) This was a warmup exercise to prepare for our next challenge: allowing each user to log into the app and save *their own separate score*.

:point_right: **Next up:** we'll combine what we learned in these two group challenges to make "Dragon Defeater" into a game that everyone can play individually, with a user login system that syncs up with the database to save each user's progress separately.
