# 6.1: Setting up your login system with GitHub and Firebase

So far we've set up a small but functional Firebase app and practiced using some of the Firebase functions for accessing and displaying data. Next, we'll set up our app to enable Firebase Authentication using the GitHub API!

📚 **Prerequisite:** You'll first need to set up your own personal Firebase app by following [the instructions in **section 3.4**](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-4-firebase-setup.md)!

**Table of Contents:**

  - 6:1.1: Register a new GitHub OAuth application
  - 6.1.2: Set up GitHub authentication in the Firebase console

:star: ***Important note for getting set up:*** The instructions below will *only* work in **Glitch** (or a similar *online* coding sandbox tool like CodePen or others). To work with the Firebase login system locally on your computer, you'll need to [set up a local web server on your computer (click here for a general guide)](https://gist.github.com/jgravois/5e73b56fa7756fd00b89). Let us know if you need help setting it up locally; that's what we're here for!

<hr/>

## 6.1.1: Register a new GitHub OAuth application

📑 **Official documentation:** [Firebase Authentication Using GitHub with JavaScript](https://firebase.google.com/docs/auth/web/github-auth) and [Registering OAuth Apps on GitHub](https://developer.github.com/apps/building-integrations/setting-up-and-registering-oauth-apps/registering-oauth-apps/)

[**OAuth**](https://oauth.net/) is an open protocol that lets you give certain apps permission to interact with other apps that you use, without needing to enter your password for all of them! We're going to use OAuth to let users log into our web app using their existing GitHub account, so that way our users never need to type their password into our app, and we don't need to store their passwords in our database at all!

When we register our OAuth app with GitHub, we get a unique ***Client ID*** and ***Client Secret***. The Client ID is public, sort of like a username but for our application, and the Client Secret is like our password --
 ***never, ever share or publish your Client Secret!*** (Except when we put it into our Firebase console, which will keep it securely stored on Firebase's server.)

**Follow the steps below to set up your app:**

  1. First, [click here to register a new OAuth app on GitHub](https://github.com/settings/applications/new) (you may have to log in first).

  2. For "Application name", enter something like `Firebase login with GitHub Test`

  3. For both the "Homepage URL" and the "Authorization callback URL", enter ***the URL of your own Firebase project on Glitch***. (For example: `http://myfirebasetest.glitch.me`)

  > **Note:** We're going to change the callback URL later to point to Firebase's server. The callback URL is where GitHub will redirect users after they've successfully logged into GitHub and given permission for our app to access their GitHub account.

  4. Click "Register application" at the bottom to save everything, and ***keep the tab open!*** You'll need to copy-paste your Client ID and Client Secret for the next steps.


## 6.1.2: Set up GitHub authentication in the Firebase console

📑 **Official documentation:** [Firebase Authentication Using GitHub with JavaScript](https://firebase.google.com/docs/auth/web/github-auth)

Now that we have things mostly set up on the GitHub side of things, we also need to tell *Firebase* to allow users to log in to our app using GitHub.

  1. In the [Firebase console](https://console.firebase.google.com/), go to the "Authentication" page and click on the "Sign-In Method" tab.

  > **Shortcut:** [Click on this link](https://console.firebase.google.com/project/_/authentication/providers) and then choose your project.

  2. Click on "GitHub" in the list, click the **"Enable"** switch, and then copy-paste your Client ID and Client Secret from GitHub (from that tab you left open earlier). *Keep the GitHub tab open because we'll need it again in the steps below!*

  3. Right underneath where you pasted in your Client ID and Client Secret in the Firebase console, copy the authorization callback URL (it should look similar to `https://fir-test-c7763.firebaseapp.com/__/auth/handler`), and then click the blue **"Save"** button to save your changes in Firebase.

  4. Switch back to your GitHub OAuth app page again, paste that new callback URL into the "Authorization callback URL" section at the bottom of the page (it will replace the URL of your Glitch app that was there before), and then click the green **"Update application"** button to save your changes.

<hr/>

:trophy: **And that's it!** Your app is now all configured to use both the GitHub API and Firebase Authentication!

:point_right: **Next up**, we'll write some code to implement a very basic user login system.
