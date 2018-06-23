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

<br/>

:point_right: **[Take a look at our HTML mockup here](https://group-github-login.glitch.me/).**

<br/>

Once again, we'll begin by making a plan. Time for sketching! :pencil:

<br/>

## Challenge 1:

Spend a few minutes sketching a detailed flowchart from our perspective as ***developers*** (thinking like a computer). Show what you think our code might need to do, step by step.

<br/>

## Challenge 2:

Before we write any code, we'll first need to figure out which Firebase functions we need to set up our user login system!

<br/>

  > **Note:** Our starter code is already linked to a shared Firebase database, which has already been linked to GitHub and registered with an API key (which uniquely identifies our app so that GitHub can track how we use their API).<br/><br/>You'll be doing these setup steps later on your own, when you set up a user login system for your own project.

<br/>

Take a look at the [official Firebase documentation (the JavaScript version)](https://firebase.google.com/docs/reference/js/) and **identify the following by looking in the `firebase.auth` section of the docs:**

  1. What are the properties of the Firebase `User` object, and which of those properties will we need to access in our app when we're ready to display information about the current user?

<br/>

  2. What's the name of the Firebase function that sets up the sign-in process using GitHub?
 
<br/>

  3. What's the difference between the Firebase functions named `signInWithPopup` and `signInWithRedirect`?
  
  > **Hint:** These functions are listed as "methods" within the section describing the `Auth` object.

<br/>

  4. What's the name of the Firebase function that listens for when a user's authentication state has changed?

  > You'll also find this one listed under the `Auth` object's methods.
 
<br/>

  5. What's the name of the Firebase function we'll need to use in order to *log out* the current user?

<br/>

## (Group) Challenge 3:

Let's take the first steps to setting up our app and letting a user log into our app via their GitHub account!

<br/>

  :heavy_check_mark: 1.  *Already finished:* Set up Firebase app with authentication and connect it to a GitHub API key.

<br/>

  :heavy_check_mark: 2. *Already finished:* Create JavaScript objects for each HTML element that we need to access.

<br/>

  :heavy_check_mark: 3. *Already finished:* Set up two event listeners, one to handle when the user clicks on the login/logout buttons (We named these event-handler functions `handleLoginClick()` and `handleLogoutClick`.) 

<br/>

  4. Copying straight from the Firebase documentation, let's tell Firebase to use GitHub for logging in our users. Paste this code somewhere near our other global variables:

```javascript
// Tell Firebase to use GitHub to authenticate and log in our users:
let provider = new firebase.auth.GithubAuthProvider();
```

<br/>

  5. Let's use the `signInWithPopup()` function to prompt the user to login and authorize our app to access their GitHub account. Paste this code in the right location so it only runs *after the user clicks the login button:*

```javascript
// Log in this user with Firebase GitHub Authentication
firebase.auth().signInWithPopup(provider);
```

<br/>

   6. Before moving on, let's test it out! We should see a popup window asking us to authorize this app to access our GitHub account. If we decide to grant those permissions, then we'll be redirected back to our app and the popup window will close. (Nothing else will happen after that, because we've only built the very first step!)
 
<br/>

## Review of API access tokens:

Remember from [section 6.2 in our previous class](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-6/6-2-github-post-delete.md) when we created a ***personal access token*** to grant certain permissions for our GitHub accounts? (That's the only way we could create or delete repositories on our own GitHub accounts.)

<br/>


That's basically what Firebase is doing for us now! Here's what happens under the hood (a bit oversimplified but here's the gist of it):

  1. Firebase makes an API request to GitHub to ask you (the user) to grant certain permissions.
  
  2. If you agree to grant those permissions, then GitHub will send a response to your Firebase app with the requested information (like your username and profile photo).
  
  3. GitHub's response also includes an access token that Firebase saves for you. Once you have this token, you could create and delete repositories on behalf of the logged-in user! (Only if they grant permission.)
  
  4. Firebase also creates its own internal ***unique identifier*** for each user. Later, we'll use this ID to save information about ***each*** user into our Firebase database!

<br/>

## (Group) Challenge 4:

Hurray, we can now log into our app! But the app still doesn't actually ***do*** anything, and we can't even see whether the login process worked or not!

<br/>

Let's fix that:

  1. We'll need to use another one of those Firebase functions that we found earlier: `onAuthStateChanged()`. This is a special ***event listener*** that tells Firebase to call one of our functions when the user opens the web page and when the user logs in or logs out of our app.<br/><br/> Let's set up this event listener to call our own function named `handleAuthStateChange`:

```javascript
firebase.auth().onAuthStateChanged(handleAuthStateChange);
```

<br/>

  2. Let's define that `handleAuthStateChange` function, because it doesn't exist yet! Define it somewhere at the bottom of the page, and give it ***one parameter*** named `currentUser`. The function should log the `currentUser` parameter to the console.

<br/>

  3. Refresh the page and you should see something interesting appear in the console right away. What is it?
  
  <br/>
  
  4. Look inside the data that Firebase gave us, and **identify the properties** that we need to display on our page for the current user once they've logged in.
  
  <br/>
  
  5. Inside our `handleAuthStateChange` function, call `console.log` two more times to display the ***values*** of those two properties.
  

<br/>

## (Group) Challenge 5:

Woohoo, we have user data! But the user still can't *log out* of our app. Let's add that feature and then fix things up a bit:

<br/>

  1. Add this line of code so it will run when the user clicks the "log out" button:

```javascript
firebase.auth().signOut();
```

<br/>

  2. Test it out! What happens when you log out of our app? Check the console.
  
<br/>
  
  3. Right now, our code always does the *same thing* whether the user has just opened the page, logged in, or logged out. But we want to do something ***different*** depending on whether the user has logged in or logged out. How can we tell the difference?

<br/>

  4. Let's create a conditional statement that checks whether there's a user currently logged in or not. If there is a current user logged in, then display `"User is logged in"` to the console; otherwise, display `"User is logged out"`.


<br/>

## Challenge 6:

:pencil: Time for more sketching! **Modify or redraw** your flowchart so that each step in the flowchart also says ***the name of the function*** in which this step occurs (if any), and the name of the function that this step ***calls*** (if any).

So now our flowcharts should match the code we've written so far, and identify *in which functions* our next steps need to be completed!

<br/>

## (Group) Challenge 7:

Now that the core of our login system is working, let's update the user interface! First, let's show/hide the login/logout buttons as needed. We'll need to add ***four lines of code*** to accomplish this, copying from the examples below:

<br/>

**We can hide any element on the web page like this:**

```javascript
// Assuming we already did nameOfElem = document.getElementById("idhere");
nameOfElem.style.display = "none";
```

<br/>

**Then to show an element, we can do this:**

```javascript
// Also assuming we already did nameOfElem = document.getElementById("idhere");
nameOfElem.style.display = "block";
```

<br/>

  > **Note:** There are other values we can use for the CSS `display` property, which affect how elements are included in the layout of the page. That's a topic specific to CSS though, which is outside the scope of our class. A quick Google search will yield plenty of examples and tutorials, though!
  
<br/>

## (Group) Challenge 8:

Finally, let's display the current user's data onto the page when we know without a doubt that they're currently logged in:

<br/>

  1. Change the `textContent` property of the welcome message to say `"Welcome, [user's name here]!"` (where it actually displays the name of the current user).
  
  2. Change the `src` property of the image to show the current user's profile photo.

<br/>

Let's be sure to test the app again, as we do after every new feature we add to our code!

<br/>

## (Group) Challenge 9:

Notice that when we log out of the app, our photo and name are still showing on the page! Any user looking at this would think that the logout button must be broken. Let's fix that!

<br/>

  1. Change the `textContent` of the welcome message to say `"Click login to get started with our awesome app!"` when the user logs out.
  
  2. Hide the image element when the user logs out.
  
  3. Test the app again. Be sure to test logging in, logging out, and refreshing the page in various combinations.
  
<br/>

## (Group) Challenge 10:

Oops! When we added that last feature, we also created a new bug! If the user logs out and then logs back in, their profile photo doesn't show up again. **Fix this bug!**

<br/>

## Bonus Challenge:

Here's one more small improvement you could make to this app. Notice that when you first open the page, some elements "flicker" very briefly. That's because we can see the result of the original HTML code *before* our JavaScript file downloads and runs our code.

So instead of relying on *hiding* and *unhiding* elements, we could instead use JavaScript to ***create*** brand new HTML elements on the fly and insert them into the HTML!

<br/>

:star: ***Before anything else, make a remix of our group project on Glitch so you'll have your own personal copy to work with.*** 

<br/>

**Search online to find the following:**

  1. What built-in JavaScript function lets you create new HTML elements?
  
  2. And what built-in function lets you add your new element into the actual web page?
  
  3. How would you set the `textContent`, the `id`, and/or the `src` properties of your new element?
  
  > **Hint:** It works the same way as before -- we're just accessing and assigning values to properties of objects.

After experimenting with those new functions on their own, see how you can use them within this project to create and display elements on the fly, only when they're needed!

<br/>
<hr/>

:trophy: **We've summoned the spirit of Kenny Loggins, king of logins!** Woohoo! We've implemented our very first user login system with just a handful of new functions, combined with our knowledge of objects, event listeners, and accessing HTML elements with JavaScript.

:point_right: **Next up:** [in section 7.2, .....](#)!
