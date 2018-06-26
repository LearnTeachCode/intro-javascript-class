# 7.3: Setting up your login system with Firebase and GitHub

Time to make a user login system for your own project, just like the app we made together in [section 7.1](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-7/7-1-group-firebase-github-login.md)!

<br/>

📚 **Prerequisites:**
  - Make sure you already have a Firebase web app linked to your code. (If you need a refresher, [see the instructions in **section 2.7**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-7-firebase-setup.md).)

<br/>

:star: ***Important note for getting set up:***
  - The instructions below assume you're running your app in **Glitch** (or a similar *online* coding sandbox tool like CodePen or others).
  - To make your app's login system work ***locally***, you'll need to [set up a local web server on your computer](https://gist.github.com/jgravois/5e73b56fa7756fd00b89) -- using [**http-server** with NodeJS](https://gist.github.com/jgravois/5e73b56fa7756fd00b89#http-server-for-node) is recommended! If the instructions at that link didn't work or you need any help, just ask! :)

<br/>

<hr/>

## Register a new GitHub OAuth application:

📑 **Official documentation:** [Firebase Authentication Using GitHub with JavaScript](https://firebase.google.com/docs/auth/web/github-auth) and [Registering OAuth Apps on GitHub](https://developer.github.com/apps/building-integrations/setting-up-and-registering-oauth-apps/registering-oauth-apps/)

<br/>

[**OAuth**](https://oauth.net/) is an open protocol that lets you give certain apps permission to interact with other apps that you use, without needing to enter your password for all of them! We're going to use OAuth to let users log into our web app using their existing GitHub account, so that way our users never need to type their password into our app, and we don't need to store their passwords in our database at all!

<br/>

When we register our OAuth app with GitHub, we get a unique ***Client ID*** and ***Client Secret***. The Client ID is public, sort of like a username but for our application, and the Client Secret is like our password --
 ***never, ever share or publish your Client Secret!*** (Except when we put it into our Firebase console, which will keep it securely stored on Firebase's server.)
 
 <br/>
 
:star: **Follow the steps below to set up your GitHub app:**

  1. First, [click here to register a new OAuth app on GitHub](https://github.com/settings/applications/new) (you may have to log in first)

<br/>

  2. For "Application name", enter the name of your project or just something like `Firebase login with GitHub Test`

<br/>

  3. For both the "Homepage URL" and the "Authorization callback URL", enter ***the URL of your own Firebase project on Glitch***. (For example: `http://myfirebasetest.glitch.me`)

  > **Note:** We're going to change the callback URL later to point to Firebase's server. The callback URL is where GitHub will redirect users after they've given permission for our app to access their GitHub account.

<br/>

  4. Click "Register application" at the bottom to save everything, and ***keep the tab open!*** You'll need to copy-paste your Client ID and Client Secret for the next steps.

<br/>



## Set up GitHub authentication in the Firebase console:

📑 **Official documentation:** [Firebase Authentication Using GitHub with JavaScript](https://firebase.google.com/docs/auth/web/github-auth)

<br/>

Now that we have things mostly set up on the GitHub side of things, we also need to tell ***Firebase*** to allow users to log in to our app using GitHub.

<br/>

:star: **Follow the steps below to set up your Firebase app's login system:**

  1. In the [Firebase console](https://console.firebase.google.com/), go to the "Authentication" page, click on the "Sign-In Method" tab at the top.

  > **Shortcut:** [Click on this link](https://console.firebase.google.com/project/_/authentication/providers) and then choose your project.

<br/>

  2. Under "Authorized domains" towards the bottom of that page, click the blue **"Add Domain"** button. In the little window that pops up, enter ***the URL of your own Firebase project on Glitch***. (For example: `http://myfirebasetest.glitch.me`)

<br/>

  3. On that same page, under the list of "Sign-in providers", click on **"GitHub"** in the list, then click the **"Enable"** switch, and copy-paste your Client ID and Client Secret from GitHub (from that tab you left open earlier). <br/><br/>*Keep the GitHub tab open because we'll need it again in the steps below!*

<br/>

  4. Right underneath where you pasted in your Client ID and Client Secret in the Firebase console, copy the authorization callback URL (it should look similar to `https://fir-test-c7763.firebaseapp.com/__/auth/handler`), and then click the blue **"Save"** button to save your changes in Firebase.

<br/>

  5. Switch back to your GitHub OAuth app page again, paste that new callback URL into the "Authorization callback URL" section at the bottom of the page (it will replace the URL of your Glitch app that was there before), and then click the green **"Update application"** button to save your changes.


<br/>

<hr/>

:trophy: **And that's it!** Your app is now all configured to use both Firebase Authentication with the GitHub API!

:point_right: **Next up**, in [section 7.4, you'll test that the above steps worked and get some extra review of what we learned in class together!](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-7/7-4-firebase-login-review-challenges.md)

