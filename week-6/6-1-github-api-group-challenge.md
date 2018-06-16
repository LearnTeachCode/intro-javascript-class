# 5.1: API group practice challenge

[Last week](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-5), we practiced using a third party web API in our own little app, displaying a random dad joke on the page every time the user clicks a button. Let's practice some more with a new API and a *slightly* more challenging project!

:books: **Prerequisites:**
  - [Review APIs and using cURL from week 4 here](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-4)

<hr/>

## Planning our app

:hammer: **What are we building this time?** Let's use the GitHub API to display the name and profile photo of any GitHub user!

**Feature requirements:**

  - The user can type the username of any GitHub user into a text input box.
  - Every time the user clicks the button, make an API call to request the GitHub data about the requested user.
  - Once GitHub's response has successfully downloaded, display:
    - Display the user's name in a paragraph
    - Display the user's profile photo in an image element

:point_right: **[Take a look at our HTML mockup here](https://group-github-api.glitch.me/).**

As always, we'll begin by making a plan. Get out your sketchbooks! :pencil:

<br/>

## Challenge 1:

:hourglass_flowing_sand: In two minutes or less, sketch a quick flowchart from the ***user's perspective***, outlining how the user would use this app step by step.

<br/>

## Challenge 2:

Spend a couple more minutes sketching *another* flowchart, this time from the ***computer's perspective***. Show what our code needs to do step by step. (This will be more detailed than how the user perceives our app.)

<br/>

## Challenge 3:

Before we write any code, we'll first need to figure out how to use GitHub's API to request a user's information!

**Search through [GitHub's API documentation](https://developer.github.com/v3/) to find the following:**

  1. What is the ***base URL*** for all of GitHub's API endpoints?

<br/>

  2. What's the web address for the section of GitHub's API documentation that's all about ***users***?
  
  > **Hint:** look at the right-side navigation menu.

<br/>
  
  3. Which HTTP method do you need to use to request a single user's data?
 
<br/>
 
  4. What's the ***endpoint*** for requesting the data for ***a single user***?
  
  > **Remember:** an endpoint is just another word for a URL that's part of an API. More specifically, the endpoint is the ***last*** portion of the URL -- the part the comes after the API's base URL.
  
<br/>

  5. Which part of that endpoint do you think is a ***parameter*** that you'll need to replace with an actual user's name? 
  
  > **For example:** Liz's GitHub username is `LearningNerd`, so to get Liz's data you would need to include `LearningNerd` as part of the endpoint/URL.
  
<br/>

## Challenge 4:
  
Once you've found all the information you need, try accessing the data for *your own* GitHub account by accessing the appropriate endpoint ***directly in your web browser.***

  > Remember: Visiting a website and making an API request are basically the same thing! For many APIs, you can access them by typing the URL right into your browser's navigation bar.

<br/>

## Challenge 5:

Next, practice accessing this API using `curl` via the command line!

  :books: For a **review of using `curl`**, [see the instructions in section 4.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-4-curl-intro.md).

<br/>

**Bonus:** Try using the `-i` flag with your `curl` command to see the ***response headers***, and identify the data format that GitHub's servers used to send you the data you requested.

<br/>

The `-i` flag is short for `--include` (both versions of that command will work, but note that the longer version has *two* hyphens in front of it).

**Here's an example of what it looks like to use the `-i` flag:**

```bash
curl http://example.com/ -i
```

<br/>

## Challenge 6:

Remember the JavaScript code we used in our previous classes to make an API request? Here's *part* of that example code. **Fill in the blanks to make your API request to GitHub.** Then test it directly in your browser console.

```javascript
// This code isn't complete. Fill in the blanks!
var requestObject = new XMLHttpRequest();
requestObject.addEventListener(            );
requestObject.open(                 );
requestObject.      ;

function handleResponse () {
  console.log(requestObject.responseText);
}
```

<br/>

## Quick review of JSON and "stringifying" objects:

Back in [section 2.3](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-3-json-intro.md) we started learning about the JSON data format and how to use the built-in `JSON.stringify()` function to convert a JavaScript object into a big ol' string!


**An example of `JSON.stringify`:**

```javascript
let personObject = {
	name: "Liz",
	awesomenessLevel: "infinite"
};

// Convert the object into a string and then save it into a new variable:
let personString = JSON.stringify(personObject);

// See it in the console. Now it's a string!
console.log(personString);
```

When we request data from an API, that's often *exactly* what their servers do -- they take an object from their code, ***convert*** it into a string, and then ***send*** that string to us over the internet. (The string is the *body* of their *HTTP response*.)

<br/>

:star: **So turning an object into a string is essentially *packaging it up* into a standard format that's easy to send over the internet.**

Imagine the JavaScript object as a bunch of physical things (maybe a set of furniture? a bunch of bowling balls?) that you want to ship to someone else. Converting an object into a JSON-formatted string is like putting those items into a shipping container -- a standardized way to organize and pack up your stuff so it's easy to transport anywhere in the world!

  > *Big thanks to Barry for this metaphor!* :)

<br/>

## Challenge 7:

So what's the ***inverse** or the *opposite* of "stringifying" an object? Search online to find the JavaScript equivalent of *unpacking* the data!

Then test out the function that you found by giving it the example string below as its *input*. Then display the *output* of your function call in the console.

```javascript
let dataStringToUnpack = ' {"name": "Liz", "awesomenessLevel" : "infinite"} ';

// Call the function you found to UNPACK the data above.

// Then test your code directly in the browser console!
```

<br/>

## (Group) Challenge 8:

Now that we've finished our initial planning, research, and testing for our project, we're ready to start coding!

:star: **[Click this link to collaborate on our shared Glitch project!](https://glitch.com/edit/#!/join/826ce4c3-4848-4d3e-b8f0-8633dd4b14d5)**

<br/>

**Steps to implement our first feature: requesting example data from GitHub's API:**

  1. Make an empty function to contain our API request code. Give it an appropriate name!
  
<br/>

  2. In the body of that function, include our working JavaScript code from the previous section.
  
  > We'll just use a *hard-coded* username as an example for now. (Hard-coded in the sense that it's *not* a variable; it'll be the same username every time. We'll fix that later.
  
<br/>

  3. In the section of our code where we know that we've successfully received the response from GitHub, *unpack* the string of data that they sent us and save the result to a new local variable.

  > Display it in the console to make sure it works!

<br/>

  4. Identify the ***keys*** (or properties) that contain the user's name and profile photo URL, then access them from our newly-created object and display each one in the console.
  
<br/>
  
  5. Create two local variables for the DOM elements that we'll use to display the user's data.

<br/>

  6. Display the user's name on the page.

<br/>

  7. Finally, change the placeholder image so it will instead display the user's profile photo.
  
  > We can inspect all the properties of a DOM element with the `console.dir()` function, look at all its properties to find the name of the property that contains the location of the image, and use JavaScript to *change* the value of that property!
  
<br/>

## (Group) Challenge 9:

We've finished the most important part of our project: retrieving the data and displaying it on the page! But we want the data to only appear *after* the user has click the button. Let's take care of that next.

<br/>

**Steps to implement our second feature: triggering the API request after a button click:**

 1. Set up an event listener for our button. Test that it works by using `console.log()` to display a message only when the button is clicked.
  
<br/>

  2. Referencing our flowcharts, identify the section of our code where we should call the API-requesting function we defined earlier. Then call it!

<br/>

  3. That's all we need! :) It's easier sometimes to start at the end and work our way backwards, don't you think?
  

<br/>

## (Group) Challenge 10:

Almost there! The only thing missing now is to let the user decide *which* GitHub user's data they want to see.

<br/>

**Steps to implement our last feature: making the API request based on the user's input:**

 1. Referencing our flowcharts again, identify the section of our code where we should access the user's input from the text input box.
  
<br/>

  2. Access the user's input and display it in the console to make sure it works.

<br/>

  3. Pass the user's input as an ***argument*** to our API-requesting function.
  
  > Whenever you have a function calling another function, it's usually best to pass your variables directly between them this way -- like passing the baton! :runner: <br/><br/> This makes your code more organized and easier to debug, compared to relying on global variables for everything.

<br/>

  4. Update the *definition* of our API-requesting function so that it takes one *parameter* (the *placeholder* variable that will get replaced with the user's input). Give it a descriptive name for what this parameter will represent.

<br/>

  5. Inside the definition of our API-requesting function, create a local variable that contains the URL we're using for our API request, and *replace* the hard-coded username with the *parameter* that represents the user's input.
  
  > Remember ***concatentation***, combining strings? This is what it's meant for -- combining strings with variables.

<br/>

  6. Finally, in the `.open()` function call where we pass in the URL as an argument, *replace* that URL string with the name of our new variable.

<br/>

  7. Test it with a few different inputs. If all went according to plan, our app is now complete!
  
<br/>
<hr/>

:trophy: **Woohoo!** We built our second web app that makes use of a third-party web API!

:point_right: **Next up:** [in section 6.2, we'll finally make our own POST requests to create new data with the GitHub API, and we'll need to use an API key to do it](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-6/6-2-github-challenges-continued.md)!
