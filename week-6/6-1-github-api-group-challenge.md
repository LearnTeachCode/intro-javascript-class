# 5.1: API group practice challenge

[Last week](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-5), we practiced using a third party web API in our own web app, displaying a random dad joke on the page every time the user clicks a button. Let's practice some more with a new API and a *slightly* more challenging project!

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
  
  2. What's the web address for the section of GitHub's API documentation that's all about ***users***? <br/><br/> *Hint: look at the right-side navigation menue.*
  
  3. Which HTTP method do you need to use to request a single user's data?
  
  4. What's the ***endpoint*** for requesting the data for ***a single user***? <br/><br/> *Remember: an endpoint is just another word for a URL that belongs to someone's API. More specifically, the endpoint is the LAST portion of the URL -- the part the comes after the API's base URL.*
  
  5. Which part of that endpoint do you think is a ***parameter*** that you'll need to replace with an actual user's name? <br/><br/>*For example: Liz's GitHub username is `LearningNerd`, so to get Liz's data you would need to include `LearningNerd` as part of the endpoint/URL.*
  
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

For example:

```javacsript
let personObject = {
	name: "Liz",
	awesomenessLevel: "infinite"
};

// Convert the object into a string and then save it into a new variable:
let personString = JSON.stringify(personObject);

// See it in the console. Now it's a string!
console.log(personString);
```

When we request data from an API, that's often *exactly* what their servers do -- they take an object that's stored internally in their code (or pull it out of their database), and then they need to ***convert*** that object into a ***string*** before they can send it back to us within their HTTP response.

<br/>

:star: **Remember: turning an object into a string is like *packaging it up* into a standard format that's easy to send over the internet.**

Imagine the JavaScript object as a bunch of separate things that you want to mail to someone else. Turning it into a string is like putting those items into a shipping container -- a standardized way to organize and pack up your stuff so it's easy to transport anywhere in the world!

<br/>

## Challenge 7:

So what's the ***opposite*** of "stringifying" an object -- the opposite of packing something up? Search online to find the JSON equivalent of *unpacking* your data!

  > In other words, find the inverse of the `JSON.stringify()` function.

<br/>

## (Group) Challenge 8:

Now that we've finished our initial planning, research, and testing for our project, we're ready to start coding!

:star: **[Click this link to collaborate on our shared Glitch project!](https://glitch.com/edit/#!/join/826ce4c3-4848-4d3e-b8f0-8633dd4b14d5)**

**Steps to implement our API request:**

  1. Make an empty function to contain our API request code. Give it an appropriate name!
  
  2. In the body of that function, include our working JavaScript code from the previous section.
  
  3. Create a new local variable t
  
  

<br/>

