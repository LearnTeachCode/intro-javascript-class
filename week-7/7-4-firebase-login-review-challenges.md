# 7.4: Review challenges: Firebase user login with GitHub

After setting up a login system with your own app in [section 7.3](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-7/7-4-firebase-login-review-challenges.md), you'll test that it works and review what we learned in class with the following review challenges!

<hr/>

## Set up the login/logout buttons and placeholder text

Before jumping into any of the new Firebase stuff, first let's set things up to test your new login system while getting a little extra review with DOM elements and event listeners.

<br/>

## Challenge 1:

In your own Firebase app, add the following elements to your HTML file:

  1. A paragraph with the id `"userinfo"` that displays the text `"Not currently logged in."`
  
  2. An empty paragraph with the id `"username"`.
  
  3. A button with the id `"login"` that displays the text `"Log in with GitHub"`.
  
  4. A button with the id `"logout"` that displays the text `"Log out"`.

<br/>

## Challenge 2:

In your JavaScript file, create a JavaScript object for each of the above elements; we'll need to access all of them with our JavaScript code to create this sample app!

  > Remember, the `document.getElementById()` function is how we take an HTML element and convert it into a JavaScript object!


<br/>

Make sure you test that your code works! Remember that you can `console.log()` each object, and when you run your app, you should see the corresponding HTML code appear in the browser console.

<br/>

## Challenge 3:

Set up an event listener for *both* buttons, so that every time the user clicks one of those buttons, a message should appear in the browser console that says either `"User clicked login button!"` or `"User clicked logout button!"`

  > If you need a refresher, be sure to review [section 3.1 on events and event listeners](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-1-event-listeners-review.md).

<br/>

Again, make sure you test your app to see that your code works correctly!

<br/>

## Add Firebase Authentication functions

Now that your web page is set up with the bare essentials to test out your new login system, let's use those new functions provided by the Firebase Authentication library!

<br/>

## Challenge 4:

Create an instance of Firebase's GitHub Authentication provider object, which we'll need to use later:

```javascript
// Create instance of Firebase's GitHub Authentication provider object
let githubAuth = new firebase.auth.GithubAuthProvider();
```

  > **Note:** To keep things organized, it's probably best to define this object *immediately after* the Firebase app is initialized.

<br/>

## Challenge 5:

Add the following code ***inside*** one of the functions you created earlier, so that this code will run *every time the user clicks the **login** button*.

```javascript
// Use Firebase with GitHub Authentication to log in the user
firebase.auth().signInWithPopup(githubAuth);
```

<br/>

Then be sure to test your app to see if you can indeed log in with GitHub by clicking the login button!
 
The Firebase `signInWithPopup()` function will open another page in a pop-up window, asking the user to grant access to your app. It takes a Firebase Auth provider object as its input, so in this case, we're using the GitHub Auth provider object that we created earlier. That's how it knows to open GitHub's website! (We can also use other providers like Facebook or Google if we want to.)

<br/>

If you like, you can switch out the `signInWithPopup()` function with the `signInWithRedirect()` function instead, which redirects the user to a new page in the same browser window instead of opening up a pop-up window. (This works better on mobile devices!)

<br/>

## Challenge 6:

Add the following code ***inside*** the other function you created earlier, so that it runs *every time the user clicks the **logout** button*:

```javascript
// Use Firebase to log out the current user
firebase.auth().signOut();
```

<br/>

The Firebase `signOut()` function will sign out the current user, regardless of how they signed in (whether we had them log in with GitHub or Facebook or something else).

<br/>

## Challenge 7:

Add the Firebase `onAuthStateChanged()` event listener to run a function named `handleAuthStateChange` -- it will be triggered every time the user opens the page, logs in, or logs out:

```javascript
// When user opens page, logs in, or logs out, then call the function handleAuthStateChange:
firebase.auth().onAuthStateChanged(handleAuthStateChange);
```

<br/>

## Challenge 8:

Define the function named `handleAuthStateChange`. It should take in ***one parameter*** named `currentUser`.

<br/>

Be sure to test your app again to make sure it works! (You can test that the event listener is working by using `console.log()` inside your `handleAuthStateChange` function to show a message any time your function gets called.)

  > If you need to review function parameters, see [section 4.2 from our March class](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-4/4-2-function-input-challenges.md).

<br/>

## Challenge 9:

*Inside* the function that you just defined, add an `if/else` statement that checks if the `currentUser` exists -- remember, `currentUser` is the one parameter that your function takes in. Your code should do the following:

  - If the user does exist, display this message in the console: `"User successfully logged in to Firebase!"`
  - If the user does *not* exist, display this other message in the console: `"User successfully logged OUT from Firebase!!"`

<br/>

**How to easily check if a variable exists:** This is a very helpful trick! You can just type `if (myVariable) { }` to check if `myVariable` exists! (Technically, the condition will be true if the variable conatins any value ***except*** `undefined`, `null`, `false`, or `0`.)

**Example:**

```javascript
// Define a variable with no value, so it will be undefined
let myEmptyVar;

if (myEmptyVar) {
  console.log("It exists! Not empty!");
} else {
  console.log("It doesn't exist. Empty variable!");
}
```

Be sure to test your app to see that it works!

<br/>

## Challenge 10:

Next, add some more code inside those if/else statements to display a message indicating whether the user is logged in or not:

  - If the user is logged in, that paragraph with the id `"userinfo"` should display the text `"Currently logged in!"`
  
  - If the user is *not* logged in, that paragraph with the id `"userinfo"` should again display the text `"Not currently logged in."`

<br/>

  > **Hint:** Remember, since day 1 of our class we've been using a property with a name that starts with the letter **"t"** to change the text that displays on the web page. This is a built-in property that exists for basically every DOM element (a DOM element is a JavaScript object that represents an HTML element on our web page).

<br/>

As always, test it to make sure everything works as expected!

<br/>

## Access and display Firebase user information

For the challenges below, take a look through the official documentation for the [Firebase User object](https://firebase.google.com/docs/reference/js/firebase.User) to get a sense of what information Firebase stores for the currently logged-in user.

<br/>

## Challenge 11:

Looking at the documentation linked to above, identify the name of the ***property*** (which belongs to every Firebase user object) that most likely contains the username.

<br/>

## Challenge 12:

Locate the section of your code that runs *only when the user has **just logged in*** and *only when the `currentUser` object **exists***. Within that section, `console.log()` the user's name.

Then be sure to run your app and look inside the console to make sure it works!

  > **Hint:** Remember that you can use *dot notation* to access properties of JavaScript objects. In this case, the `currentUser` parameter is our object, and we want to access one of its properties.

<br/>

## Challenge 13:

Building on your code from the previous challenge, display a message like `"Welcome, " + userNameGoesHere` inside the paragraph with the id `"username"`. But of course, change `userNameGoesHere` with the code you used in the last challenge to get the actual user's name.

  > Remember that we call `+` the *concatenation operator* and we use it to combine strings.

<br/>

Test your app thoroughly to see how all the pieces work together!

<br/>

## Challenge 14:

You may have noticed that there's a little bug: if the user logs in and then logs out again, their name and the "welcome" message is still on the page! So, let's fix that!

Write one line of code that *erases* that welcome message when the user logs out.

  > **Hint:** There are a few ways to accomplish this! You could change the element's CSS to show and hide itself at the approptiate times, or something even simpler -- you can assign an *empty string* `""` as the new value of that element's text.

<br/>

## Bonus Challenge:

Here's one more small improvement you could make -- notice that when you first open the page, some elements "flicker" very briefly. That's because we can see the result of the original HTML code *before* our JavaScript file downloads and runs our code, which *changes* the HTML to contain some new text.

So instead of relying on *hiding* and *unhiding* elements like we did in our group project ([section 7.1](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-unt/week-7/7-1-group-firebase-github-login.md)), we could instead use JavaScript to ***create*** brand new HTML elements on the fly and insert them into the HTML!

<br/>

**Search online to find the following:**

  1. What built-in JavaScript function lets you create new HTML elements?
  
  2. And what built-in function lets you add your new element into the actual web page?
  
  3. How would you set the `textContent`, the `id`, and/or the `src` properties of your new element?
  
  > **Hint:** It works the same way as before -- we're just accessing and assigning values to properties of objects.

<br/>

After experimenting with those new functions on their own, see how you can use them within this project to create and display elements on the fly, only when they're needed!

<br/>
<hr/>

🏆 ***Congratulations, you built your first web app with a working user login system!*** This is the first step towards turning all your wildest ideas into web applications that could potentially have millions of users! ;)

:point_right: **In our next class:** we'll combine what we learned in these two group challenges to make "Dragon Defeater" into a game that everyone can play individually, with a user login system that syncs up with the database to save each user's progress separately.
