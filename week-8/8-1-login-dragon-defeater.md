# 8.1: Putting it all together: "Dragon Defeater" for multiple users

In [our class last week](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-7), we built two small group projects: a tiny example of a user login system with Firebase and GitHub, and then a collaborative version of our Dragon Defeater game where we had one shared score for everyone.

Today, let's combine the two together!


:books: **Prerequisites:**
  - [Review our group project from week 7 here](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-7)

<hr/>

## Planning our app

:hammer: **What are we building?** We'll create the third version of Dragon Defeater where multiple users can log in and keep track of their own individual scores.

<br/>

**Feature requirements:**

  - Users can log in with their GitHub account

  - When the user logs in:
    - Show the user interface for the game
    - Display their name, email, and profile photo from their GitHub account
    - Display their current score that was saved in the database
    - Create (or update) their account by saving their info to the database

  - When the user clicks the "Defeat a Dragon!" button:
    - Increase their score by 1
    - Insert their new score into the database

  - When the user logs out:
    - Hide the user interface for the game

<br/>

:point_right: **[Take a look at our starter code here](https://dragon-defeater-v3-group.glitch.me/).**

<br/>

Once again, we'll begin by making a plan. Time for sketching! :pencil:

<br/>

## Challenge 1:

Let's split up into two teams for this one! Each team will draw a detailed flowchart for one of the apps we built together last week:

  1. [Last week's version of Dragon Defeater (v2)](https://glitch.com/edit/#!/dragon-defeater-v2-group-finished)
  2. [Last week's login system example using Firebase and GitHub](https://glitch.com/edit/#!/group-firebase-github-login-finished)

In your flowcharts, include the ***names of variables and functions*** associated with each step. You can even include the line numbers if you want.

  > The goal here is to practice mapping steps (from our human brains) to the actual code (the computer's "brains")!

<br/>

## (Group) Challenge 2:

All together now! Let's draw a new flowchart that outlines what we think we need to do to build our new app, combining pieces from both of our previous apps.

The more detail, the better! Let's reuse those function names wherever possible!

<br/>

## Challenge 3....:

Review db structure:

  - make an object representing yourself with 3 properties
  - small example Glitch to remix, identify path (give yourself a unique ID #), make db ref object, and insert object into our Firebase dB
  - set vs update

<br/>

## Challenge NUM:

Let's add the basic template for our login system into our new app! We'll need to do a few steps here:

  1. Set up event listeners for the login and logout buttons
  
  2. Call the appropriate Firebase functions to log the user in and log them out at the right moment
  
  3. Set up the Firebase event listener that handles changes to the user's state (whether they're logged in or out)
  
  4. Check the state of the current user within our function that runs every time the user's state changes (or when the page loads)
  
  5. Use `console.log` statements throughout to help us test that it all works!

<br/>

## Challenge NUM:

Once our users can log in and log out, let's display their profile info from GitHub on the page!

<br/>

  1. First, let's **define a new function** named `displayUserData` to keep our code organized. Let's give it *one parameter* to represent the current user object that Firebase gave us, so we can easily pass that object along from one function to another.

<br/>
  
  2. Next, let's identify **where to call our function** -- remember, order matters! Our flowchart should have the answer. We'll call our function and give it the current user object from Firebase as its argument.

<br/>

  4. Identify the **DOM elements** (parts of the web page) that we'll modify to display the user's info. Each one has already been saved to a JavaScript variable at the top of the page. What are those variables named? 

<br/>  

  5. And for each of those DOM elements, which properties will we modify to display the data?
  
<br/>

  6. Identify the **properties** of the current user object that we need to display on our page.
  
  > We can just `console.log` the object representing the current user and look inside to find the property names! Or we can look at the Firebase documentation.

<br/>

  7. Finally, let's **assign** the data from the current user object as the *new values* that will overwrite the DOM elements' properties.

<br/>

## Challenge NUM:

Let's also save the user's profile information to Firebase! We don't actually *need* to for this very simple app, but this way we'll have their data handy for future features -- like a leaderboard showing the names of every player with the top scores.

<br/>

  1. First, **where** in our code should we be saving the current user's profile info? Our flowchart should have the answer!

<br/>
  
  2. Next, remember how the current user object provided by Firebase contains a **unique ID** that we can use to identify each user in our database? What's the name of the property that contains that data?
  
<br/>
    
  3. What's the **path** to a user, given their ID? Since our code needs to work for *every single user*, that ID will be different every time, so it needs to be a variable!
  
  > We'll have to combine that variable with the rest of the path, which is a static string.
  
<br/>
  
  4. Let's create a **database reference object** for that location in the database. (This essentially converts the path string into an object that let's us run Firebase functions on *only* that one part of the database.)
  
<br/>
  
  5. Finally, let's insert the user's data! Which Firebase function should we use in this case?

<br/>

## Challenge NUM:

Now that we have the user's info being saved *and* displayed on the page, let's turn our attention to the game itself. We'll need to change our existing code so that it will *display* and *insert* the user's current score.

<br/>

  1. Where in our code will we need to set up the Firebase `.on` listener to display the current user's score? Let's move it!
  
  > **Note:** the `displayScore` function from our previous version of Dragon Defeater doesn't need to be change at all! This is one reason why self-contained functions that use parameters are *so incredibly useful* -- we can literally copy-paste them into different projects and they'll still work.
  
<br/>
   
  2. Let's **initialize** an undefined global variable named `currentScoreRef`, which will later be assigned a database reference object that points to the score of the current user.
  
  > This is a simplistic solution (just for the sake of our class) that allows us to access this variable from multiple functions.
  
<br/>
  
  3. Where in our code should we assign a value to `currentScoreRef` so that it will become a database reference object pointing to the current user's score? Again, our flowchart should have the answer for this!
  
<br/>
    
  4. And where in our code should we insert the user's latest score into the database? Let's make it happen!
  
<br/>
  
  5. But there's going to be one last bug to fix... what went wrong? 
  
  > **Hint:** Take a look at our `updateScore` function (which we left unchanged from our previous project).<br/>**Note:**

<br/>

**One last question to discuss:** How is this function different from our `displayScore` function, and why is this function ***not*** reusable?

:bulb: Hopefully these last couple of examples have illustrated the power of ***self-contained*** or ***modular functions*** that use parameters to make themselves more reusable and bug-resistent.

:spaghetti: You can see how relying too much on global variables will to lead to what we call ***spaghetti code*** -- a mess of code that's all stuck together, which you need to first untangle and tease apart before you can reuse it somewhere else (like a separate project).

<br/>

## Challenge NUM:

We're basically done! Just a couple final touches: hiding and showing parts of the user interface as needed! Which parts of the part should the user see when they're logged in or logged out?

Let's use what we learned last week to make for a better ***user experience*** (or **UX** for short).


<br/>
<hr/>

:trophy: **Great work, team!** We've applied our new knowledge to create a web app with that contains some of the most common components that exist in the many applications we use every day (like all social network sites, online shopping sites, productivity tools, games, and more). With more practice, you can expand on this example to create working prototypes for any ideas you can think of!

:point_right: **Next up:** [in section 8.2, we'll ....](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-8/8-2-*************.md)!
