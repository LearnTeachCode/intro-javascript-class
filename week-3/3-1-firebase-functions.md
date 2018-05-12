# 3.1: Core functions of the Firebase database library

With just a handful of the functions provided by the [Firebase](https://firebase.google.com) database library, we already have everything we need to start prototyping database-driven applications!

❓ **If you have any questions,** please ask on the private Slack channel for our class.

:books: **Prerequisites:**
  - You should be familiar with [everything in section 1](https://github.com/LearnTeachCode/intro-javascript-class/tree/master/week-1), especially the section on [events and event listeners (#1.2.5)](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-2-review-hangman-game.md#125-intro-to-events-and-event-listeners).
  - Definitely review [section 2.2 on objects and arrays](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-2-objects-arrays.md) and [section 2.3 on data modeling](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-3-data-modeling.md).

**Table of Contents:**  
  - 3.1.1: The structure of Firebase databases
  - 3.1.2: Firebase database paths
  - 3.1.3: Firebase database reference objects and the `ref()` function
  - 3.1.4: Reading data with Firebase event listeners
  - 3.1.5: Adding and updating Firebase data with the `set()` function
  - 3.1.6: Removing Firebase data with the `remove()` function
  - 3.1.7: Pushing new Firebase data with the `push()` function
  - 3.1.8: Displaying a list of Firebase data with the `forEach()` function

<hr/>


## 3.1.1: The structure of Firebase databases

Firebase databases store data as a **hierarchy** (also called a *tree*), just like how files and folders are stored on your computer, or how web pages are structured in the Document Object Model (see [section 1 to review the DOM](https://github.com/LearnTeachCode/intro-javascript-class/tree/master/week-1)).

If you're comfortable creating objects in JavaScript using object literal notation, then you already know the basics of JSON (see [section 2.2.5 for notes on JSON](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-2-objects-arrays.md)). And if you know how to work with JavaScript objects and JSON, you pretty much already know how to work with data stored in a Firebase database, because **Firebase stores** ***everything*** **as JSON data**!

  > **Note:** There are many different types of databases, and the Firebase database is an example of what are commonly called **NoSQL databases**. That's a topic to look up if you're curious! (Definitely a more advanced topic though.)

Remember our penguin database example from [section 2.3 on data modeling](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-3-data-modeling.md)? Here's how our penguin data is represented in an actual Firebase database:

![Fictional penguins Firebase database](https://user-images.githubusercontent.com/1555022/27147872-37732274-50f3-11e7-90f2-70c82e539477.png)

**There are four key concepts for getting started with Firebase databases:**

  1. Determining the **path** of the location of your data in the database's hierarchy
  2. Creating a **reference object** in your JavaScript code, which represents a database location
  3. Setting up Firebase **event listeners** to retrieve the data from your database (which also updates in real time!)
  4. Using the **data snapshot** object and extracting the **value** of the data
  5. A handful of other **functions** for adding, updating, and deleting data from Firebase

We'll review these new concepts step by step in the sections below.


## 3.1.2: Firebase database paths

In Firebase, each part of your database is treated as a *location* specified by a ***path***, which is a specially formatted string. We use paths with the same format in many other areas of computing, not just with Firebase!

**Examples of paths:**

  - Paths can refer to files or folders on your computer. For example, you might access the documents folder on your computer with the path `C:/Users/Liz/Documents`

  - Paths can also refer to the part of the URL that specifies the location of a web page. For example: `example.com/events/birthday-party/` or `example.com/login.html`

  - For more than you ever wanted to know about paths, see [Wikipedia's page on Path (computing)](https://en.wikipedia.org/wiki/Path_(computing))

**Looking at [the image of our penguin database]((https://user-images.githubusercontent.com/1555022/27147872-37732274-50f3-11e7-90f2-70c82e539477.png)) as an example, let's identify the path of each location in the database:**

  - Use the path `/` (just a single forward slash) to access the entire database (the ***root*** of the tree or hierarchy). In our case, the root is `test-web-app-4fde9` (which you can see at the top of the penguin database hierarchy in the image).

    > **Note:** It's an old convention in computing to use `/` as the path for the **root** of any system. By root, we mean the top-level element containing the whole tree or hierarchy, continuing the metaphor of a *tree* which has a *root* and *branches*. (Another example: the `document` object is the root of the DOM representing the hierarchy of elements on a web page.)

  - Use the path `penguins` to access the **object** that contains the entire list of penguins. (This is second level in the hierarchy, whereas the *root* or the database itself is the top level).

  - Use the path `penguins/1152` to access the **object** that contains the data for one particular penguin (the one with the unique ID number `1152`). Or replace that number with another ID to access any other penguin.

  - Use the path `penguins/1152/name` to access the **string** that contains that particular penguin's name.

Notice that we access these locations in our database a bit like we access properties (also called keys) in JavaScript objects, just with a different syntax!


## 3.1.3: Firebase database reference objects and the `ref()` function

Now that we know how to format the string for a *path*, how do we actually read data from the specified location in our database? The next step is to create a [***database reference object***](https://firebase.google.com/docs/reference/js/firebase.database.Reference) in our JavaScript code. This step is very similar to how we've been using `document.getElementById()` to convert an element from our web page into a JavaScript object.

**Example of creating a Firebase database reference object:**

```javascript
// Create a JavaScript object named penguinListRef,
// which points to the "penguins" path in the database
let penguinListRef = firebase.database().ref("penguins");
```

The `firebase.database()` code represents an object where all the Firebase database functions are stored, just to keep them organized and all in the same place. One of its functions is `ref()`, which is the one we'll be using. This is just like how `document` contains the `getElementById()` and `addEventListener()` functions, or how `console` contains the `log()` function (among others).

  > **Note:** we're glossing over the fact that `firebase.database()` looks like a function, which is different than just `document` or `console`. But it works because of how functions *return* values, which we'll learn more about later!

Notice that the `ref()` function takes one input, which needs to be a **string** containing the **path** to the location in our database that we want to access.

**Examples of accessing different database locations:**

  - To access the **root** of the database: `firebase.database().ref("/")` (or you can use `ref()` without an input for this special case, and it will still give you a database reference object that represents the root)

  - To access the object containing all the penguin objects: `firebase.database().ref("penguins")`

  - To access one particular penguin object (the one with the unique ID number `1152`): `firebase.database().ref("penguins/1152")`

  - To access the string that contains that particular penguin's name: `firebase.database().ref("penguins/1152/name")`

So you can use `firebase.database().ref()` to access any part of your database, at any level of the hierarchy! Next, let's review the third and final step to actually read data from our Firebase database.


## 3.1.4: Reading data with Firebase event listeners

To recap, we've now covered the first two steps for reading data from Firebase: identifying the *path* for a location in the database, and then creating a *database reference object* to represent that database location. Now, onto the last two steps!

To read data from our database, we need to use a special **event listener** provided by Firebase. Why an event listener and not just a simple function? Because Firebase updates the data *in real time*, which means that if the data changes, Firebase can instantly update that data on your web page! (This makes it pretty easy to make apps like chat rooms and multiplayer games!)

If you know how to use [event listeners in JavaScript (review section 1.2.5 here)](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-2-review-hangman-game.md#125-intro-to-events-and-event-listeners), then you already know how to use event listeners with Firebase! The main Firebase event listener we'll be using has a very short name: `on()`. So when working with Firebase events, we use `on()` instead of `addEventListener`.

**Example of using the Firebase `on` listener:**

```javascript
// Create a database reference object for one penguin's name
let penguinNameRef = firebase.database().ref("penguins/1152/name");

// Set up the Firebase event listener on that reference object
penguinNameRef.on("value", logData);

// This function will run any time the Firebase "value" event is triggered
// for our particular reference object (the name of penguin #1152):
function logData (dataSnapshot) {

  // Extract the value of this penguin's name and show it in the console:
  let penguinName = dataSnapshot.val();
  console.log(penguinName);
}
```

Just like with [regular JavaScript event listeners](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-2-review-hangman-game.md#125-intro-to-events-and-event-listeners), every time you work with Firebase database event listeners, there are **three main questions** you'll need to answer:

  - **Where is the event happening? Which part of our database?** On the `penguinNameRef` object, which points to the name of a particular penguin, located at the path `"penguins/1152/name"` inside Firebase.

  - **Which event are we listening for?** The `"value"` event, which is triggered once when the page loads and again any time a value changes inside this database location.

  - **What should happen when the event occurs?** Run the `logData` function.

So to recap: Firebase uses the `on()` function just like we used `addEventListener()`, except it needs to be attached to a *database reference object* instead of an element of our web page.

We use the `"value"` event, which is triggered *once* when our web page loads and then again whenever the value of that database location changes. And just like with regular event listeners, `on()` will run a custom function that we define ourselves whenever that `"value"` event is triggered.

### Extracting data using `dataSnapshot` and the `val()` function

The `dataSnapshot` object is like a photograph of our data at a certain moment in time. The data snapshot is given to one of our own functions by the Firebase event listener `on()`, whenever it's triggered by that `"value"` event.

The `dataSnapshot` object is similar to the `event` object used in our [second event listener example in section 1.2.5](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-2-review-hangman-game.md#125-intro-to-events-and-event-listeners), so definitely review that section!

With Firebase, when we just want the **value** of our data, we don't need to use the entire `dataSnapshot` object; it contains lots of other things that we don't need. So to extract just the value of our data, we use the built-in `val()` function. When we call `dataSnapshot.val()`, we get *only* the value of our data. 

**Example of reading/accessing an object from Firebase:**

```javascript
// Create a database reference object for penguin with ID 1152
let penguinRef = firebase.database().ref("penguins/1152");

// Set up the Firebase event listener on that reference object
penguinRef.on("value", logPenguinData);

// This function will run once on page load,
// and again any time the data of penguin #1152 changes:
function logPenguinData (dataSnapshot) {

  // Extract the value of this penguin
  // * IMPORTANT: Remember this penguin is an OBJECT!
  let penguinObject = dataSnapshot.val();

  // Show the whole penguin object in the console
  console.log(penguinObject);

  // Value of the penguin's "name" property:
  // * will show in console: "Gunter"
  console.log(penguinObject.name);

  // Value of the penguin's "canFly" property:
  // * will show in console: true
  console.log(penguinObject.canFly);
}
```

**Example of displaying Firebase data on the web page:**

```javascript
// Create a database reference object for name of penguin #1152
let penguinNameRef = firebase.database().ref("penguins/1152/name");

// Set up the Firebase event listener on that reference object
penguinNameRef.on("value", displayName);

// This function will run once on page load,
// and again any time name of penguin #1152 changes:
function displayName (dataSnapshot) {

  // Extract the value of this penguin's name (a STRING)  
  let penguinName = dataSnapshot.val();

  // Display name on the web page:
  document.body.textContent = "Penguin name is: " + penguinName;
}
```

To recap, there are **four steps for reading data from Firebase:**

  1. Determine the **path** of the location of your data in the database's hierarchy.
  2. Create a **reference object** in your JavaScript code, which reperesents that database location.
  3. Set up a Firebase **event listener** to retrieve the data from your database (which also updates in real time!).
  4. Extract the **value** from the data snapshot that Firebase gives to your function.

Next, let's review the most common functions we'll be using to add, update, and delete Firebase data!


## 3.1.5: Adding and updating Firebase data with the `set()` function

The [Firebase `set()` function](https://firebase.google.com/docs/reference/node/firebase.database.Reference#set) writes data to the location specified by a database reference object. If the specified location in your database doesn't exist, `set()` will create it; otherwise, if it *does* already exist, `set()` will update (overwrite) the data at that location.

It takes **one input**, which can be a JavaScript object or simply a string, number, or Boolean (true/false).

**Example of updating a string with `set()`:**

```javascript
// Create a database reference object for name of penguin #1152
let penguinNameRef = firebase.database().ref("penguins/1152/name");

// Change its name to the string "Polly"
penguinNameRef.set("Polly");
```

**Example of updating an object:**

```javascript
// Create a database reference object for penguin #1152 (the whole penguin)
let penguinRef = firebase.database().ref("penguins/1152");

// Make a new object to replace penguing #1152's data
let newObject = {
  "name": "Penguin McPenguinface",
  "origin": "My imagination",
  "canFly": false
}

// Replace/overwrite penguin #1152 with the new object:
penguinRef.set(newObject);
```

**Example of creating a new database location:**

```javascript
// Create a database reference object for a path
// that DOESN'T EXIST YET! (We're allowed to!)
let newPenguinRef = firebase.database().ref("penguins/999");

// Make a new object containing the new penguin's data
let newPenguinObject = {
  "name": "Tux",
  "origin": "Linux mascot",
  "canFly": false
}

// Add the data above to the new location at path "penguins/999"
newPenguinRef.set(newPenguinObject);
```


## 3.1.6: Removing Firebase data with the `remove()` function

Firebase has a built-in [`remove()` function](https://firebase.google.com/docs/reference/node/firebase.database.Reference#remove) that does exactly what you'd expect: it removes data from a location in your database. To use this function, we must first create a database reference object for the part of our database that we want to remove.

**Example of removing a string with `remove()`:**

```javascript
// Create a database reference object for name of penguin #1152
let penguinNameRef = firebase.database().ref("penguins/1152/name");

// Remove this penguin's name entirely:
penguinNameRef.remove();
```

**Example of removing a whole object**

```javascript
// Create a database reference object for one penguin object
let penguinRef = firebase.database().ref("penguins/1152");

// Remove this entire penguin!
penguinRef.remove();
```

Notice that `remove()` doesn't require an input, since it already needs to be attached to a database reference object. That reference object is what gets removed. (A similar example is the `pop()` function built into every array, which removes the last element of whichever array it's attached to.)


## 3.1.7: Pushing new Firebase data with the `push()` function

Just like you can `push()` a new value onto the end of an array, Firebase also provides its own special [`push()` function](https://firebase.google.com/docs/reference/node/firebase.database.Reference#push) to add a new *child* location into the hierarchy of your database!

The special thing about `push()` that's different from `set()` (reviewed above) is that `push()` creates a new database location *with an automatically-generated random ID*. So instead of our example above where we used `set()` to create a new database location by specifying the path `"penguins/999"`, we could have used `push()` instead to generate a random ID number for us!

**Example of creating a new database location with `push()`:**

```javascript
// Create a database reference object for the list of penguins
let penguinListRef = firebase.database().ref("penguins");

// Make a new object containing the new penguin's data
let newPenguin = {
  "name": "Tux",
  "origin": "Linux mascot",
  "canFly": false
}

// Create a NEW location as a child of the penguins list (one level deeper in the hierarchy),
// using a random ID for its property, and add the new penguin object into that location:
penguinListRef.push(newPenguin);

// Now the path to the new penguin might be something like:
// "penguins/abc123"
```

Since the newly-created location in the database has a randomly generated ID, we need to do one more step if we want to access that new location:

```javascript
// ...continuing from previous code example...

// Create a new variable to store a database reference object
// pointing to the new location created by push():
let newPenguinRef = penguinListRef.push(newPenguin);

// Now if we want to CHANGE that newly-created penguin,
// we can use set() on the newPenguinRef database reference object:
let editedPenguin = {
  "name": "Swimmy Bird",
  "origin": "A game",
  "canFly": false
}
newPenguinRef.set(editedPenguin);
```


## 3.1.8: Displaying a list of Firebase data with the `forEach()` function

:star: **Note:** This function is definitely a bit more advanced! You'll need to be very comfortable with functions that run other functions before you *really* learn how to use this one. **So think of this as a bonus challenge!**

The [Firebase `forEach()** function`](https://firebase.google.com/docs/reference/node/firebase.database.DataSnapshot#forEach) is built into every `dataSnapshot` object, and it lets you loop through every item in the data snapshot, running one of your own functions multiple times, once for each item! So if you want to display a list of data, it's very handy!

Using our penguin example again, let's say we want to `console.log()` the name of every penguin in our database. Here's how we could use `forEach()` to make that easier:

```javascript
// Create a database reference object for the list of penguins
let penguinListRef = firebase.database().ref("penguins");

// Set up the Firebase event listener on that reference object
penguinListRef.on("value", logAllPenguins);

// This function will run any time the Firebase "value" event is triggered,
// once on page load and again if any of the data in the penguin list changes
function logAllPenguins (dataSnapshot) {

  // For each penguin in our list of penguins, run the logNameOfPenguin function
  dataSnapshot.forEach(logNameOfPenguin);
}

// This function is run by forEach() above, repeated once for every penguin
function logNameOfPenguin (penguinObject) {

  // Log the value of the "name" property of each penguin object
  console.log(penguinObject.name);
}
```

Notice that we define *two* of our own functions in the code above, since our code is working sort of like a chain reaction! Here's what's happening in the code above:

  1. First, the `on()` event listener starts waiting for the `"value"` event to occur, which gets triggered as soon as the web page loads (and again every time our data changes).
  
  2. Once triggered, `on()` will run our own function named `logAllPenguins()` and give it a `dataSnapshot` object containing all our data.

  3. Then *inside* our `logAllPenguins()` function, we use `dataSnapshot.forEach(logNameOfPenguin)` to run our *section* function named `logNameOfPenguin()` once for every piece of data inside that data snapshot.

  4. Each time our `logNameOfPenguin()` function runs, it's given a single item of data from `dataSnapshot`. In our case, each of those items is a penguin object, so we decided to name that input (also called parameter) `penguinObject`.

  5. Finally, we log each penguin's name to the console with `console.log(penguinObject.name)`. Remember, *each* time our `logNameOfPenguin()` function runs, it receives a new item of data. Since it executes multiple times thanks to the data snapshot's `forEach()` function, it can display *every* penguin's name!
  
<hr/>

:trophy: **Great job if you've made it this far!** This is a *lot* of new material and it *should* be challenging. Don't worry if you don't understand it yet; we will return to these concepts and practice more.

:point_right: **Next:** work on [section 3.3: Firebase practice challenges](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-3-firebase-challenges.md) or complete the steps in [section 3.4: Setting up your own Firebase app](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-4-firebase-setup.md).
