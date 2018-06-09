# 5.2: NASA API challenges

In our [previous section (5.1)](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-5/5-1-api-group-challenge.md), we used JavaScript to display data from the Dad Jokes API, a ***public, open-access API*** that anyone can use for *any* purpose, no questions asked. (Because it was a just-for-laughs API -- *literally!*)
<br/>

:star: But most companies or organizations that provide APIs will require you to *register* with them first, so they can limit and/or monitor how you use their API. Usually they will assign you an ***API key***, which is basically a very long password that *only you* have access to.

<br/>
  
Next up, let's work with a *real-world* API provided by NASA (the National Aeronautics and Space Administration) -- it's *out of this world!* :earth_americas: :rocket:

<hr/>


## Challenge 1:

NASA lets anyone test out their API using what they call a *demo key*, so you can use it a couple times without signing up for an API key first.

Many APIs will let you test out their services like this with a fake/temporary API key; they just limit how often you can use their API while in this "testing" mode. To get full access to their API, you still need to create an account with them and get a real API key.

<br/>

:trophy: **Your challenge:** Request some fun astronomy facts from NASA!

  1. First, try to access NASA's Astronomy Picture of the Day by requesting this URL: `https://api.nasa.gov/planetary/apod` <br/><br/> ***...Uh oh, it didn’t work! Why not?***

  2. Look at [their API documentation](https://api.nasa.gov/api.html#apod) to figure out how to get this to work.
    
  3. Test it out by entering the correct URL into your web browser's address bar (just like how you visit any normal website)/

<br/>

  > ***Yup, web browsers can display JSON data!*** So you *can* access APIs (using a `GET` request) directly in your web browser. You just have less control this way, compared to making API requests using `curl` via command line or using code.

<br/>

## Challenge 2:

We used *one* query parameter in our previous challenge, but you'll often need to provide *more than one* parameter to request more specific information.

<br/>

**To provide multiple query parameters in a URL, the end of the URL will follow this format:**

```
?param1=value1&param2=value2
```

<br/>

:trophy: **Your challenge:** Figure out how to request NASA's featured picture for **December 31st, 2017**! Look at [NASA's API docs](https://api.nasa.gov/api.html#apod) again to identify how to add the appropriate query parameter.

  > You can test this directly in your web browser as well. Feel free to try it out using `curl` via command line too!

<br/>

## API rate limits

Many API providers will *limit* how often you can use their API. Why? Here are two main reasons:

  - Sending data over the web uses up bandwidth, which costs money! API providers will create rate limits to help keep their expenses under control.
  
  - Even more importantly, rate limits also help to prevent abuse of the API -- for example, by overloading the API provider's servers with what's called a [denial-of-service (DoS) attack](https://en.wikipedia.org/wiki/Denial-of-service_attack).

  > One example: Google Maps provides an API for calculating the distance between two places, which is free up to a point, and then they start charging you money after that. You can see all their details here: https://developers.google.com/maps/documentation/distance-matrix/usage-limits 

<br/>

## Challenge 3:

How many API requests can you make to NASA's API each hour? Read [their documentation on rate limits here](https://api.nasa.gov/api.html#web-service-rate-limits) to find out.

<br/>

## Challenge 4:

We've already sent NASA a few API requests today, so let's find out how many more requests we have left before they temporarily block us from using their API!

**Your challenge:**

  1. What's the name of the special key word we need to look for to find out how many API requests we have remaining? [Find it in NASA's API documentation here](https://api.nasa.gov/api.html#web-service-rate-limits).
  
  2. What is that thing? (***Hint:*** the answer is in [section 4.4 from last week, underneath challenge #2](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-4-curl-intro.md#challenge-2))!
  
  3. In your web browser, go to this URL: https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY and ***open Chrome's network tab*** to inspect the requests/responses being sent.
  
  > If you need a refresher, [review the instructions on using Chrome's network tab in section 4.3](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-3-chrome-network-tab.md).
  
  4. In the network tab's list of files that were downloaded, click the one named `apod?api_key=DEMO_KEY` and look under the *response headers* to find out how many API calls you have remaining.
  
<br/>

## Challenge 5:

Next, identify that same exact information (how many API requests you have remaining), but this time make your API request using `curl` via the command line!
  
  > For instructions on how to use `curl`, see [the instructions in section 4.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-4-curl-intro.md).


<br/>

## Challenge 6:

OK, let's stop using the demo key so we won't be blocked for the rest of the hour. [**Sign up for your own API key from NASA**](https://api.nasa.gov/index.html#apply-for-an-api-key) -- it should only take a moment!

<br/>

## Challenge 7:

Using Chrome or `curl` via command line, request another random photo from NASA, ***but this time use your own API key*** instead of the demo key.

Check the response headers (using `curl` or Chrome's network tab) to confirm how many API requests you're now allowed to make each hour! *The difference is astronomical!*

<br/>

## Challenge 8:

Borrowing from the example code below, make ***one small change*** to request NASA's random photo data and show their server's response in the browser console.

```javascript
var requestObject = new XMLHttpRequest();
requestObject.addEventListener("load", handleResponse);
requestObject.open("GET", "https://icanhazdadjoke.com/");
requestObject.send();

function handleResponse () {
  console.log(requestObject.responseText);
}
```

<br/>

## Group challenge:

:star: **[Click this link to collaborate on our shared Glitch project!](https://glitch.com/edit/#!/join/d41c9162-9467-47ea-839d-80d5e994cfdf)**

<br/>

:hammer: **What are we building?** An app that lets the user retrieve NASA's Astronomy Picture of the Day for any date of their choosing.

**Feature requirements:**

  - HTML elements needed:    
    - A text input box that the user can type a date into
    - A paragraph with instructions to tell the user what date format they need to use
    - A button that the user can click on
    - A heading (let's use the `<h2>` tag) to show the title of NASA's photo
    - An image to display NASA's photo itself
    
  - When the user clicks the button, save their input to a variable.
  
  - Make an API call to NASA with the required parameters (get their photo for the date chosen by the user)
  
  - When NASA's response has finished downloading:
    - Display the title inside our heading element
    - Display the image inside our image element

<br/>

  > Notice how the flowcharts we sketched for our previous app *almost perfectly match* the steps required for this new app! The only change here is that now the user types into a box, and we need to take that data and use it to make our API request.


<br/>
<hr/>

:trophy: **Great work!** We built our first application that makes use of a third-party web API!

:point_right: **In our next class:** we'll work with other interesting APIs and do more complex actions via API requests, like *creating* new data instead of simply *requesting* it. In the next class or two, we'll also start setting up a user login system with Firebase, which you'll integrate into your own project!
