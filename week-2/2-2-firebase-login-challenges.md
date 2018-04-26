# 2.2: Firebase user login challenges

So far we've set up a small but functional Firebase app and practiced using some of the Firebase functions for accessing and displaying data. Next, we'll practice with our shared Firebase app to implement a user login system using Firebase Authentication and the GitHub API!

📚 **Prerequisites and resources:**

  - Make sure you've already completed [section 2.1: Setting up your login system with GitHub and Firebase](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-1-firebase-login-setup.md)!
  - If you need a refresher, take a look at [section 1.1 to review some basic Firebase functions](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-1-firebase-functions.md)
  - As an extra resource, see [Firebase's official documentation on GitHub Auth with JavaScript](https://firebase.google.com/docs/auth/web/github-auth) and their page on [Managing Users in Firebase](https://firebase.google.com/docs/auth/web/manage-users)

**Table of contents:**
  - 2.2.1: Set up your web page
  - 2.2.2: Add Firebase Authentication functions
  - 2.2.3: Access Firebase user profile information

<hr/>

## 2.2.1: Set up your web page

Before jumping into any of the new Firebase stuff, let's first set up our example web app and review how to work with DOM elements and event listeners. **For all of these challenges, you'll need to use your own Firebase app on Glitch.** (Complete both [**section 1.4**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-4-firebase-setup.md) and [**section 2.1**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-1-firebase-login-setup.md) first if you haven't yet!)

:star: ***Important note for getting set up:*** The instructions below will *only* work in **Glitch** (or a similar *online* coding sandbox tool like CodePen or others). To work with the Firebase login system locally on your computer, you'll need to [set up a local web server on your computer (click here for a general guide)](https://gist.github.com/jgravois/5e73b56fa7756fd00b89).

### Challenge 1:

In your own Firebase app on Glitch, add the following elements to your HTML file:

  1. A paragraph with the id `"userinfo"` that displays the text `"Not currently logged in."`
  
  2. An empty paragraph with the id `"username"`.
  
  3. A button with the id `"login"` that displays the text `"Log in with GitHub"`.
  
  4. A button with the id `"logout"` that displays the text `"Log out"`.


### Challenge 2:

In your JavaScript file, create a JavaScript object for each of the above elements; we'll need to access all of them with our JavaScript code to create this sample app!

  > Remember, the `document.getElementById()` function is how we take an HTML element and convert it into a JavaScript object!

Make sure you test that your code works! Remember that you can `console.log()` each object, and when you run your app, you should see the corresponding HTML code appear in the browser console.

### Challenge 3:

Create an event listener for both buttons, so that every time the user clicks one of those buttons, a message should appear in the browser console that says either `"User clicked login button!"` or `"User clicked logout button!"`

  > If you need a refresher, be sure to review events and event listeners.

Again, make sure you test your app to see that your code works correctly!


## 2.2.2: Add Firebase Authentication functions

Now that your web page is set up with the bare essentials to test out your simple login system, let's use the functions provided by the Firebase Authentication library to let users log in or log out with their GitHub account, and display their username on your web page!

:star: ***Before anything else, [add your name to your GitHub account](https://github.com/settings/profile).*** This will make it easier to confirm if your login system is working correctly:

  - In your [GitHub profile settings](https://github.com/settings/profile), write something in the "Name" box at the very top.
  - Then click the green **"Update profile"** button at the bottom to save your changes.
  
### Challenge 1:

Create an instance of Firebase's GitHub Authentication provider object, which we'll need to use later:

```javascript
// Create instance of Firebase's GitHub Authentication provider object
let githubAuth = new firebase.auth.GithubAuthProvider();
```

  > **Note:** To keep things organized, it's probably best to define this object immediately after the Firebase app is initialized.

### Challenge 2:

Add the following code so that it runs *every time the user clicks the login button*. Then be sure to test your app to see if you can indeed log in with GitHub by clicking the login button!

```javascript
// Use Firebase with GitHub Authentication to log in the user
firebase.auth().signInWithPopup(githubAuth).catch(function(error) {
  // Log any errors to the console
  console.log(error);
});
```

  > **Hint:** Remember how event listeners work: they call a function *only* when a certain event happens. So think about *where* you should paste all of the code above. Order matters!

The Firebase `signInWithPopup()` function will open another website in a pop-up window, asking the user to grant access to our app. It takes a Firebase Auth provider object as its input, so in this case, we're using the GitHub Auth provider object that we created earlier. That's how it knows to open GitHub's website! (We can also use other providers like Facebook or Google if we want to.)

If you like, you can switch out the `signInWithPopup()` function with the `signInWithRedirect()` function instead, which redirects the user to a new page in the same browser window instead of opening up a pop-up window. (This works better on mobile devices!)

### Challenge 3:

Add the following code so that it runs *every time the user clicks the logout button*:

```javascript
// Use Firebase to log out the current user
firebase.auth().signOut().catch(function(error) {
  // Log any errors to the console
  console.log(error);
});
```

The Firebase `signOut()` function will sign out the current user, regardless of how they signed in (whether we had them log in with GitHub or Facebook or something else).

### Challenge 4:

Add the Firebase `onAuthStateChanged()` event listener to run a function named `handleAuthStateChange` every time the user either logs in our logs out:

```javascript
// When user logs in or logs out:
firebase.auth().onAuthStateChanged(handleAuthStateChange);
```

The Firebase  `onAuthStateChanged` method is an event listener that is triggered whenever the user's authentication state has changed -- either they've just logged in, or they've just logged out. Its callback function receives a [Firebase User object](https://firebase.google.com/docs/reference/js/firebase.User) as its input (here we named the parameter `user`), which contains a bunch of information about the user!

### Challenge 5:

Define the function named `handleAuthStateChange`. It should take in ***one parameter*** named `user`. Then be sure to test your app again to make sure it works! (You can test that the event listener is working by using `console.log()` to show a message any time your function gets called.)

  > Be sure to review the material from our previous class on how to define functions, how to call functions, and the difference between parameters and arguments.

### Challenge 6:

*Inside* the function that you just defined, add an `if/else` statement that checks if the `user` exists -- remember, `user` is the one parameter that your function takes in. Your code should do the following:

  - If the user does exist, display this message in the console: `"User successfully logged in to Firebase!"`
  - If the user does *not* exist, display this other message in the console: `"User successfully logged OUT from Firebase!!"`

**How to easily check if a variable exists:** This is a very helpful trick! You can just type `if (myVariable) { }` to check if `myVariable` exists! (By "if it exists", we mean if the variable is neither `undefined` nor `null`, the two special data types that can be used to indicate that something doesn't exist.)

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

### Challenge 7:

Next, add some more code inside those if/else statements to display a message indicating whether the user is logged in or not:

  - If the user is logged in, that paragraph with the id `"userinfo"` should display the text `"Currently logged in!"`
  
  - If the user is *not* logged in, that paragraph with the id `"userinfo"` should again display the text `"Not currently logged in."`

  > **Hint:** Remember, since day 1 of our class we've been using a property with a name that starts with the letter **"t"** to change the text that displays on the web page. This is a built-in property that exists for basically every DOM element (a DOM element is a JavaScript object that represents an HTML element on our web page).

As always, test it to make sure everything works as expected!


## 2.2.3: Access and display Firebase user information

For the challenges below, take a look through the official documentation for the [Firebase User object](https://firebase.google.com/docs/reference/js/firebase.User) to get a sense of what information Firebase stores for the currently logged-in user.

### Challenge 1:

Looking at the documentation linked to above, identify the name of the ***property*** (which belongs to every Firebase user object) that most likely contains the username.

### Challenge 2:

Locate the section of your code that runs *only when the user has just logged in* and *only when the user object exists*. Within that section, `console.log()` the user's name.

Then be sure to run your app and look inside the console to make sure it works!

  > **Hint:** Remember that you can use *dot notation* to access properties of JavaScript objects. In this case, the `user` parameter is our object, and we want to access one of its properties.

### Challenge 3:

Building on your code from the previous challenge, display a message like `"Welcome, " + userNameGoesHere + "!"` inside the paragraph with the id `"username"`

  > Remember that we call `+` the *concatenation operator* and we use it to combine strings.

Test your app thoroughly to see how all the pieces work together!

### Challenge 4:

You may have noticed that there's a little bug: if the user logs in and then logs out again, their name and the "welcome" message is still on the page! So, let's fix that!

Write one line of code that *erases* that welcome message when the user logs out.

### Bonus challenge:

Wouldn't it be nice to display the user's name *and* their profile photo when they're logged in, just like most web apps do? See if you can add this feature!

Some things to think about:

  - Which property of the Firebase user object contains the information we need for this feature?
  
  - How can you add an image to your web page? (The easiest way is to change your HTML file, but you can also learn how to dynamically create new elements and add them to your web page using only JavaScript!)
  
  - How can you use JavaScript to access or change the source of an image that appears on your web page? (This is only a Google search away!)
  
  - How would you test this *in isolation* from your Firebase app? What's the *smallest possible example* you can come up with? Make a new Glitch project specifically to test this new stuff! You can use a random image from the internet; it doesn't have to be an actual user's profile photo.
  
  - Once you get that working on its own and you're ready to bring it into your Firebase project, where exactly in your existing code would you you need to handle displaying the image?
  
  - How would you *remove* or *hide* the image once the user logs out?

Food for thought! :)

<hr/>

🏆 ***Congratulations, you built your first web app with a working user login system!*** This is the first step towards turning all your wildest ideas into web applications that could potentially have millions of users!
