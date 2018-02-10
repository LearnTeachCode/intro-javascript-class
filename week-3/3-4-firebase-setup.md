# 3.4: Setting up your own Firebase app

[Firebase](https://firebase.google.com/) is a set of tools (now owned by Google) that help software developers build web and mobile apps more quickly and easily. We'll be using their real-time database platform as the backend for our app, so we don't have to worry about setting up or maintaining our own server! It's a great beginner-friendly way to start learning about databases, and these "Backend as a Service" (BaaS) tools are a huge trend in the tech industry right now!

:tv: **Watch [this 2-minute video introducing the Firebase database service](https://youtube.com/watch?v=U5aeM5dvUpA)**

**Table of Contents:**  
  - 3.4.1: [Including the Firebase Library in Your Project](#321-including-the-firebase-library-in-your-project)
  - 3.4.2: [Creating a Firebase App](#322-creating-a-firebase-app)
  - 3.4.3: [Displaying Data from Your Firebase Database](#323-displaying-data-from-your-firebase-database)

<hr/>

## 3.4.1: Including the Firebase library in your project

First create a new website project in [Glitch](https://glitch.com/) (or feel free to use any other tool, or develop this app locally on your computer if you prefer).
In your HTML file, *before your existing `<script>` tag that imports your JavaScript file*, import the Firebase library by copy-pasting the code below:
```
<script src="https://www.gstatic.com/firebasejs/4.8.2/firebase.js" defer></script>
```
So your HTML page should look like it does in this example: 
https://glitch.com/edit/#!/firebase-starter1?path=index.html:1:0

  > Again, remember that you need to include the Firebase library ***before*** you include your own JavaScript file!


## 3.4.2: Creating a Firebase app

**1. [Click here to open the Firebase console](https://console.firebase.google.com/)** (which is just a web page that lets you manage your app), and log in using your Google account if you haven't already.
 
**2. Click "Add New Project"** and give your project a name like "First Firebase Test" or similar:  

  ![Add New Firebase Project](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/addproject.png)
 
**3. Click "Add Firebase to your web app":**
  
  ![Add Firebase to your web app](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/add-firebase-to-web-app.png)
 
**4. Copy ONLY the JavaScript code from their pop-up window** -- only the part ***outlined in pink*** in the screenshot below, NOT the <script> tags. Then paste that code into your JavaScript file:  

  ![Copy Firebase initialization code](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/addfirebase.png)

So your JavaScript file should now look very similar to this:
https://glitch.com/edit/#!/firebase-starter1?path=script.js:12:31

  > **Don't copy-paste my code from the Glitch project above!** You need to use your own database name, API key, etc for your Firebase app, *not mine!*

**5. In the Firebase console, navigate to the "Database" page and then to the "Rules" tab.**

  > Shortcut: [Click on this link](https://console.firebase.google.com/project/_/database/rules) and then choose your project to get to the page quickly!

Then double-click the code where it says `"auth !== null"` and type to replace it with ```true``` so that the code says `".read": true, ".write": true` for the rules.

Note: **Don't** use quote marks around `true`! So it should look like this:  

![database rules](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/rules.png)

**6. Click the Publish button right above the rules to save your changes.** You should now see a warning like in the image below, saying that your security rules are defined as public and anyone can read or write to your database:  

![database rules warning](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/rulewarning.png)

That's exactly what we want right now; while we're testing this first version of our app, we want it to work without requiring users to sign in first. Later on you can change the rules to add security as needed, once you’re ready to share your app with the world.

:trophy: **Congrats, you now have a Firebase app!** :) To recap, your project should look similar to this:  
https://glitch.com/edit/#!/firebase-starter1 


## 3.4.3: Displaying data from your Firebase database

Now let's make sure our Firebase app is working! First we'll add some sample data directly in the Firebase console, and then we'll test it out by displaying that data on a web page.

**1. In the Firebase Console (the website you logged into earlier), click "Develop" on the left menu, then "Database", and then to the "Data" tab.**

  > **Shortcut:** [Click on this link](https://console.firebase.google.com/project/_/database/data) and then choose your project.

**2. Hover your mouse over the name of your database (in my example below, it’s called `fir-test-c7763`) and then click on the plus sign that appears:**  

![hover data](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/hoverrule.png)

**3. In the two text boxes that pop up, type "greeting" for the name and "Hi from Firebase!" for the value.**

Then click the blue **"Add"** button when you're ready to save your new data:  

![add data](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/adddata.png)

Great, we have some data to tinker with! :) In the next several steps, we'll write some code to display that data on our web page and make sure our Firebase app is working.

**4. In your HTML file, create an HTML element like a paragraph, and give it an id of `"firebase-greeting"`.**

**5. Then in your JavaScript file, create an object named `firebaseGreetElem` that represents the paragraph you just created above.**

  > Remember, the `document.getElementById()` function is how we take an HTML element and convert it into a JavaScript object!

**6. Create another JavaScript object called `dbGreetingRef`.** This object will be our reference to the location in our database with the path of `"greeting"`. Use this code below:

```javascript
// Create a database reference object for the location in our database with the path "greeting"
let dbGreetingRef = firebase.database().ref("greeting");
```

  > Be sure to review [section 3.1.3 on Firebase database reference objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md#313-firebase-database-reference-objects-and-the-ref-function)!

**7. Next, we'll use another built-in Firebase function to create an event listener.** We always need to use events to access data from our Firebase database. See [section 3.1.4: Reading data with Firebase event listeners](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md#314-reading-data-with-firebase-event-listeners) to review!

```javascript
// Set up the Firebase event listener on our database reference object
// Any time the "value" event is triggered (when the page loads or when the data changes),
// then our code will run the function named displayFirebaseGreeting
dbGreetingRef.on("value", displayFirebaseGreeting);

// Define the function named displayFirebaseGreeting,
function displayFirebaseGreeting(dataSnapshot) {
  firebaseGreetElem.textContent = dataSnapshot.val();
}
```

**8. After that, define the `displayFirebaseGreeting` function.** It takes a special `dataSnapshot` object as input, then uses the Firebase `val()` function to extract the value of our actual data, and finally displays it on our web page by setting the `textContent` property of our paragraph to equal the value of our data.

```javascript
// Define the function named displayFirebaseGreeting,
function displayFirebaseGreeting(dataSnapshot) {
  firebaseGreetElem.textContent = dataSnapshot.val();
}
```

  > Lots of new concepts here! The topics above are also covered in [section 3.1.4: Reading data with Firebase event listeners](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-1-firebase-functions.md#314-reading-data-with-firebase-event-listeners), so be sure to read those notes.

**9. Now let's test our new app!**

Open up your web page, and you should now see your message "Hi from Firebase!" appear on the page! :)

**10. While the web page is open in your web browser -- leave it open, no need to refresh the page! -- open another tab and change the message in your Firebase console.**

To get back to editing the data in your Firebase console, you can click "Develop" on the left menu of the Firebase console website, then click "Database", and then go to the "Data" tab.

  > **Shortcut:** [Click on this link](https://console.firebase.google.com/project/_/database/data) and then choose your project.

Click on your `"Hi from Firebase!"` message, and type in the box to change the value to something else like `"I changed this data in Firebase!"` Then press the **Enter key** to save your changes:

![change data](https://raw.githubusercontent.com/LearnTeachCode/intro-javascript-class/master/week-3/img/changeddata.png)

Now look at your web page again. If it worked, you'll see the data change *in real time*, instantly, without ever refreshing the web page! Cool, right?

<hr/>

:trophy: ***Congratulations!*** **You now have your very own Firebase app to practice with and help you build prototypes for any database-driven applications you can think of!**
