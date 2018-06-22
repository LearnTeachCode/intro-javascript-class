# 7.1: Building a user login system with Firebase and GitHub

[Last week](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-6), we built a small web app that lets you type in a GitHub username and see that user's name and profile photo. Next, we'll repurpose that code to create the very first step required for any multi-user web app: a user login system!


:books: **Prerequisites:**
  - [Review our group project from week 6 here](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-6)

<hr/>

## Planning our app

:hammer: **What are we building now?** Let's make a tiny app where users can log in with their GitHub account and see a welcome message and their own GitHub profile photo.

**Feature requirements:**

  - By default (if no user is logged in), the page will display "Click login to get started with our awesome app!"
  - When the user clicks the login button, Firebase will log them in using their GitHub account credentials
  - After they've given permission for the app to access their GitHub account, they'll return to our web page.
  - Any time the web page opens, we'll check if there's a user currently logged in. If so, then do the following:
    - Display "Welcome, [user's name here]!" in a paragraph
    - Display the user's profile photo in an image element
    - Hide the login button and instead show the logout button
  - When the user clicks the logout button, Firebase will log them out and our page will do the following:
    - Replace the text of the paragraph so it will show the "Click login to..." message instead of the welcome message
    - Hide the user's profile photo
    - Hide the logout button and instead show the login button

:point_right: **[Take a look at our HTML mockup here](https://group-github-login.glitch.me/).**

Once again, we'll begin by making a plan. Time for sketching! :pencil:

<br/>

## Challenge 1:

Spend a few minutes sketching a detailed flowchart from our perspective as ***developers*** (thinking like a computer). Show what you think our code might need to do, step by step.

<br/>

## Challenge 2:

Before we write any code, we'll first need to figure out which Firebase functions we need to set up our user login system!

  > **Note:** Our starter code is already linked to a shared Firebase database, which has already been linked to GitHub and registered with an API key (which uniquely identifies our app so that GitHub can track how we use their API).<br/><br/>You'll be doing these setup steps later on your own, when you set up a user login system for your own project.
  
Take a look at the [official Firebase documentation for their JavaScript library](https://firebase.google.com/docs/reference/js/). We'll be using the `Firebase.auth` functions and objects.

**Identify the following:**

  1. What's the name of the Firebase function that sets up the sign-in process using GitHub?
  
  2. What are the properties of the Firebase `User` object, and which of those properties will we need to access in our app when we're ready to display information about the current user?
  
  3. What's the difference between the Firebase functions named `signInWithPopup` and `signInWithRedirect`?
  
  > **Hint:** These functions are listed as "methods" within the section describing the `Auth` object.

  4. What's the name of the Firebase function we'll need to use in order to *log out* the current user?



