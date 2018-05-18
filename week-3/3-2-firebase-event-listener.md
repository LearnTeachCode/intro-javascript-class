# 3.2: Intro to Firebase challenges: Displaying data using the Firebase `.on` event listener

Now that we've [reviewed event listeners in the previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-3/3-1-event-listeners-review.md), you'll see that Firebase event listeners will look very familiar!

To recap, there are **four key concepts for accessing data from Firebase:**

  1. [**From section 2.4:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-4-firebase-paths.md) Determining the **path** to your data's location in the database
  2. [**From section 2.5:**](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-5-firebase-reference-objects.md) Creating a **reference object** in your JavaScript code, which represents a database location (a chunk of data)
  3. Setting up Firebase **event listeners** to retrieve the data from your database (which also updates in real time!)
  4. Using the **data snapshot** object to extract the **value** of the data

Let's start by comparing the Firebase `.on()` function to the built-in `addEventListener()` function that we've been using so far.

<hr/>

First, let's review the familiar pattern we've been using so far to respond to user events a web page. Imagine we have the following code in our HTML file:

```html
<button id="win">Click here to win a bazillion dollars!</button>
```





<br/>

<hr/>

:trophy: ***Woohoo!*** ......

**Next up:** ....
