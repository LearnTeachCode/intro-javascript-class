# Seciton 6.3: NASA API challenges

In our [previous section (6.2)](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-6/6-2-api-group-challenge.md), we used JavaScript to display data from the Dad Jokes API, a ***public, open-access API*** that anyone can use for *any* purpose, no questions asked. (Because it was a just-for-laughs API -- *literally!*)
<br/>

:star: But most companies or organizations that provide APIs will require you to *register* with them first, so they can limit and/or monitor how you use their API. Usually they will assign you an ***API key***, which is basically a very long password that *only you* have access to.

<br/>
  
Next up, let's work with a *real-world* API provided by NASA (the National Aeronautics and Space Administration) -- it's *out of this world!* :earth_americas: :rocket:

<hr/>


## Challenge 1:

NASA lets anyone test out their API using what they call a *demo key*, so you can use it a couple times without signing up for an API key first.

Many APIs will let you test out their services like this with a fake/temporary API key; they just limit how often you can use their API while in this "testing" mode. To get full access to their API, you still need to create an account with them and get a real API key.

<br/>

:trophy: **Your challenge:** Request some photos and fun astronomy facts from NASA!

  1. First, try to access NASA's Astronomy Picture of the Day by navigating to this URL in your web browser (just like visiting any normal website): `https://api.nasa.gov/planetary/apod` <br/><br/> ***...Uh oh, it didn’t work! Why not?***

  2. Look at [their API documentation](https://api.nasa.gov/api.html#apod) to figure out how to get this to work.
    
  3. Once you find the correct URL from their documentation link above, test it out by pasting that link into your web browser's address bar (again, here we're accessing their API just like how we visit any normal website).

<br/>

  > ***Yup, web browsers can display JSON data!*** So you *can* access APIs (using a `GET` request) directly in your web browser. You just have less control this way, compared to making API requests via your code or via `curl` in the command line.

<br/>

## Query strings for sending parameters with an HTTP request

For the previous challenge, we needed to use a ***query string*** to send a key-value pair to NASA's server.

<br/>

:star: A ***query string*** is some optional information that can be included at the end of a URL. The query string always begins with a `?` (question mark), followed by a string. It can *only* appear at the ***end*** of a URL.

**Examples:**

  1. **Any URL can have a query string at the end:** <br/> `https://example.com?thisisaquerystring` <br/>If that website's server doesn't make use of query strings, it'll just ignore everything after the `?` in the URL.
  
  2. **When you do a search on Google, they put your search terms in the URL as a query string:** <br/> `https://www.google.com/search?q=What+is+a+query+string`<br/> This lets you bookmark the search results page so you can easily return to it later!

<br/>

**The most common use for query strings: *sending key-value pairs to the server!***

  - The conventional format for sending a key-value pair in the query string is: `?key=value`
  
  - Most API documentation will use the phrase ***query parameters***, rather than "key-value pairs", but they basically mean the same thing.

<br/>

**To provide multiple *query parameters*, the end of the URL will follow this format:**

```
?key1=value1&key2=value2
```

<br/>

## Challenge 2:


<br/>

:trophy: **Your challenge:** Make a request for NASA's featured picture for **December 31st, 2017**! Look at [NASA's API docs](https://api.nasa.gov/api.html#apod) again to identify how to add the appropriate query parameters.

<br/>

Feel free to test this out using any of the following ways (even better if you practice using all of them!):

  - Navigate to the URL directly in your web browser (like visiting any normal website)
  - Make the request using `curl` via command line too
  - Use JavaScript code to make the request, either from your browser console or in a Glitch project

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
  
  2. What is that thing? (***Hint:*** the answer is in [section 5.3 from last week, underneath challenge #2](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-5/5-3-curl-intro.md#challenge-2))!
  
  3. In your web browser, go to this URL: https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY and ***open Chrome's network tab*** to inspect the requests/responses being sent.
  
  > If you need a refresher, [review the instructions on using Chrome's network tab in section 5.2](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-5/5-2-network-tab.md).
  
  4. In the network tab's list of files that were downloaded, click the one named `apod?api_key=DEMO_KEY` and look under the *response headers* to find out how many API calls you have remaining.
  
<br/>

## Challenge 5:

Next, identify that same exact information (how many API requests you have remaining), but this time make your API request using `curl` via the command line!
  
  > For instructions on how to use `curl`, see [the instructions in section 5.3](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-5/5-3-curl-intro.md).


<br/>

## Challenge 6:

OK, let's stop using the demo key so we won't be blocked for the rest of the hour. [**Sign up for your own API key from NASA**](https://api.nasa.gov/index.html#apply-for-an-api-key) -- it should only take a moment!

<br/>

## Challenge 7:

Using Chrome (navigate to the URL) or using `curl` via command line, request another random photo from NASA, ***but this time use your own API key*** instead of the demo key.

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

## Bonus project challenge:

Let's build a tiny web app to get some more practice using APIs!

<br/>

:hammer: **What are we building?** An app that displays today's NASA's Astronomy Picture of the Day as soon as you open the web page. (Users can visit this app every day to see every new picture.)

<br/>

**Feature requirements:**

  - HTML elements needed:    
    - A heading (let's use the `<h2>` tag) to show the title of NASA's photo
    - An image to display NASA's picture

  - Make an API call to NASA (you can just use their demo API key since this app is just a tiny prototype)
  
  - When NASA's response has finished downloading:
    - Display the title inside our heading element
    - Display the image inside our image element

<br/>

**Suggested steps for building this app:**

  1. Create a new Glitch project by [remixing the official Glitch website starter template](https://glitch.com/edit/#!/hello-webpage).

<br/>

  2. In your HTML file, create the necessary HTML elements (as outlined in the feature requirements above) <br/>  *Feel free to search online for a refresher of how to create these HTML elements.*

<br/>

  3. In your JavaScript file, first create new variables to contain JavaScript objects that represent each of those HTML elements that you just created.

<br/>

  4. Before you worry about the API request, first practice *changing the text* of the heading element using JavaScript code. (Always good to review and double check that it works before moving on.)

<br/>

  5. Next, we'll practice modifying that image element! To do that, first get a URL to a random photo from the internet. <br/> *For example: `https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/Shar_Pei_puppies.jpg/640px-Shar_Pei_puppies.jpg`*

<br/>

  6. Access the `src` property of the JavaScript object representing your image element, and assign it a new value -- the new value will be that URL to a photo (as a string)! <br/><br/> *The `src` property is similar to the `textContent` property that we've been using all along!*

<br/>

  7. Next, make your API request to NASA by reusing and modifying the JavaScript code from our previous project. Display the response in the console first.

<br/>

  8. Remember when we talked about [the JSON data format in section 6.1](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-6/6-1-json-intro.md)? The NASA API sent us back a ***JSON-formatted string***! So instead of using the `JSON.stringify()` function, we'll need to use its polar opposite function named `JSON.parse()`.<br/>*Look up some examples of how it works, and practice parsing the response text that you received from NASA!*

<br/>

  9. After *parsing* the response text and turning it into a usable JavaScript object, practice *accessing its properties* and displaying them in the console!<br/>*What are the names of the **two properties** you'll need to get NASA's title and photo URL?*

<br/>

  10. Change the text of your header element to display the title of NASA's picture.

<br/>

  11. Change the `src` property of your image element, assigning NASA's photo URL as its new value.

<br/>

  12. Don't forget to test the page to make sure that your app works! You should see the title and photo appear on your web page now!

<br/>

:star: ***Extra bonus challenge:*** Add a feature so that the user can type in the date of their choosing into a text box, press a button to submit their choice, and then the web app will make the API rquest and display NASA's photo and title for *that particular date*!

<br/>
<hr/>

:trophy: **Great work!** Now we've worked with *two* different APIs -- are you ready for more? ;)

:point_right: **In our next class:** we'll work with other interesting APIs and do more complex actions via API requests, like *creating* new data instead of simply *requesting* it.
