# 7.2: Firebase review: Building a collaborative "Dragon Defeater"

Let's review what we've learned so far about Firebase to udpate our first group project, the Dragon Defeater game!

<br/>

:books: **Review materials:**

  - [2.4: Accessing Firebase data with paths](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md)
  - [Section 2.5: Database reference objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md)
  - [Section 3.2: Displaying data using the Firebase `.on` event listener](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-2-firebase-event-listener.md)
  - [Section 3.3: Adding, updating, and deleting data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-3-firebase-set-remove.md)

<hr/>

## Planning our app

:hammer: **What are we building?** Let's add some Firebase magic to make our "dragon defeater" game collaborative, so *anyone* can increase the number of dragons defeated and we can all keep track of the total score!

<br/>

**Feature requirements:**


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
 
  3. Set up a ***Firebase event listener*** so that the web page will always ***display*** the current number of dragons defeated (which is now stored in the database).
 
 <br/>
 
  4. When anybody clicks the button, in addition to increasing the score by one, we should also ***insert*** the new score into the database.

