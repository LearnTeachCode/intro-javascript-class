[Firebase](https://firebase.google.com/) is a set of tools (now owned by Google) that help software developers build web and mobile apps more quickly and easily. We'll be using their real-time database platform as the backend for our app, so we don't have to worry about setting up or maintaining our own server! It's a great beginner-friendly way to start learning about databases, and these "Backend as a Service" (BaaS) tools are a huge trend in the tech industry right now!

**Watch this 2-minute video introducing the Firebase database service:** 
https://www.youtube.com/watch?v=U5aeM5dvUpA

**Table of Contents:**  
  - 3.2.1: [Including the Firebase Library in Your Project](#321-including-the-firebase-library-in-your-project)
  - 3.2.2: [Creating a Firebase App](#322-creating-a-firebase-app)

<hr/>

## 3.2.1: Including the Firebase Library in Your Project

First create a new website project in [Glitch](https://glitch.com/) (or feel free to use any other tool, or develop this app locally on your computer if you prefer).
In your HTML file, before your existing <script> tag that imports your JavaScript file, import the Firebase library code by copy-pasting the code below:
```
<script src="https://www.gstatic.com/firebasejs/4.6.2/firebase.js" defer></script>
```
So your HTML page should look like it does in this example: 
https://glitch.com/edit/#!/firebase-starter1?path=index.html:1:0

## 3.2.2 Creating a Firebase App

1) Open the Firebase console (which is just a web page that lets you manage your app) and login using your Google account.
 
2) Click "Add New Project" and give your project a name like "First Firebase Test" or similar:
![add project](https://github.com/edselhans/intro-javascript-class/blob/master/week-3/img/addproject.png)
 
3) Click "Add Firebase to your web app"
 
4) Copy ONLY the JavaScript code from their pop-up window (only the part outlined in red in the screenshot below, NOT the <script> tags). Then paste that code into your JavaScript file.
![add firebase](https://github.com/edselhans/intro-javascript-class/blob/master/week-3/img/addfirebase.png)

So your JavaScript file should now look very similar to this:
https://glitch.com/edit/#!/firebase-starter1?path=script.js:12:31

**Don’t copy-paste my code from the Glitch project above,**
you need to use your own database name, API key etc for your Firebase app, not mine!

5) In the Firebase console, navigate to the "Database" page and then to the "Rules" tab.
Shortcut: [Click on this link](https://console.firebase.google.com/project/_/database/rules) and then choose your project to get to the page quickly!

Then double-click the code where it says ```"auth !== null"``` and type to replace it with ```true``` so that the code says ```".read": true, ".write": true``` for the rules.

*Note: **Don't** use quote marks around ```true```! So it should look like this:*
![database rules](https://github.com/edselhans/intro-javascript-class/blob/master/week-3/img/rules.png)

6) Click the **Publish** button right above the rules to save your changes.
You should now see a warning like in the image below, saying that your security rules are defined as public and anyone can read or write to your database:
![database rules warning](https://github.com/edselhans/intro-javascript-class/blob/master/week-3/img/rulewarning.png)

That's exactly what we want right now; while we're testing this first version of our app, we want it to work without requiring users to sign in first. Later on you can change the rules to add security as needed, once you’re ready to share your app with the world.

Congrats, you now have a Firebase app! :) To recap, your project should look similar to this:
https://glitch.com/edit/#!/firebase-starter1 
