# 8.4: API practice challenges part 2

In the [previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-8/8-3-api-challenges-1.md), we tested out a couple of silly APIs to learn about reading API documentation, viewing headers and sending our own, requesting different data formats, and supplying our own query parameters.

So far, we've only tried out ***public APIs*** that don't require you to set anything up to identify *who you are*. But many APIs, if not *most* of them, do require you to identify yourself using an **API key** or a **personal access token**, which is basically a very long password that *only you* have access to.

So next, let's try out a couple other APIs that require API keys or access tokens!

<hr/>

## Challenge 1: Try one of NASA's APIs with their demo API key

Some APIs will let you test out their API using a fake API key; they just limit how often you can use their API while in this "testing" mode. To get full access to their API, you still need to create an account with them and get a real API key. [**NASA's APIs**](https://api.nasa.gov/api.html#apod) are one example of this pattern. Let's try it out!

**Your challenge:** Request some fun astronomy facts from NASA!

  1. First, use cURL to access NASA’s Astronomy Picture of the Day by requesting this URL: `https://api.nasa.gov/planetary/apod` ***Uh oh, it didn’t work!*** Why not?
  
  2. Look at [their API documentation](https://api.nasa.gov/api.html#apod) to figure out how to get this to work. The response body should contain JSON formatted data with some fun astronomy facts!

<br/>

## Challenge 2: Use more than one query parameter

We've used *one* query parameter in our previous API practice challenges, but you'll often need to provide *more than one* parameter to request more specific information.

To provide multiple query parameters in a URL, end of the URL looks like this: `?param1=value1&param2=value2`

**Your challenge:** Look at NASA's API docs again and figure out how to grab the info for NASA's featured picture for **December 31st, 2017**. Do this in cURL

<br/>

## Challenge 3: Look at JSON data in your web browser

As we saw in previous challenges, web browsers know how to display data formatted as HTML -- that's what all websites look like under the hood! Browsers can also show images if you navigate directly to an image file (which cURL doesn't know how to do). Well, it turns out browsers can also display all sorts of other data formats / file types, including JSON data!

**Your challenge:** Use your web browser to access the same URL from the previous challenge. What does it look it?

<br/>

## Challenge 4: Set up an account to use Microsoft's machine learning APIs

Microsoft and several other companies now offer APIs that give you access to their fancy-schmancy machine learning and artificial intelligence software, so that way you can benefit from their magical powers without reinventing the wheel! We're going to try out the [**Face Detection API** from Microsoft Azure Cognitive Services](https://docs.microsoft.com/en-us/azure/cognitive-services/face/overview )

**Your challenge:** Create your own account to get an API key.

  1. Log in or create an account by going to: https://azure.microsoft.com/en-us/try/cognitive-services/my-apis/ 

  2. Add the Face Detection API to your account
  
  3. Open up a plain text editor; it's easier to type long cURL commands here compared to straight into the command line!
 
  > **Windows:** open a plain text editor program like **Notepad**.   

  > **Mac:** open a plain text editor like **TextEdit**. Change the settings to plain text by going to `TextEdit` > `Preferences` in the menu bar, then on the `New Document` tab, select `Plain Text` in the `Format` section.
  
  4. From your account page that you just logged into, copy your **Endpoint** and your **API key**, either "Key 1" or "Key 2" and **save them** into a plain text file, because you'll need them for the next challenges!
  
  > For example, my endpoint was `https://westcentralus.api.cognitive.microsoft.com/face/v1.0` and my API key was similar to `ad20a2123ede4ce0702dc545b2d2d1a`

:star: **Remember: treat your API key like a password!** Don't share them anywhere or store them in any insecure places!


<br/>

## Challenge 5: Look through their API docs

As always, when using a new API, first you need to figure out what rules or standards they're using! Let's look at their documentation a bit.

**Your challenge:** Look through [their Face Detection API documentation here](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) to answer the questions below:

  - Which of the four main HTTP verbs you need to use for Microsoft’s Face Detection API?
  
  - What's the name of the header that we'll need to use in order to include our API key?

<br/>

## Challenge 6: Detect the age and gender of a face

**Your challenge:** Use the Face Detection API!

  1. Go to the [University of Massachusetts “Labeled Faces in the Wild” database](http://vis-www.cs.umass.edu/lfw/alpha_all_0.html)

  2. Get the URL of one of those images by right-clicking on an image (Ctrl+Click on Mac), and then click **"Copy Image URL"** in the drop-down menu. **Paste** that URL into a plain text file, because you'll need it for the next step.

  4. Copy paste the code below into your plain text file:

```bash
curl "YOUR-ENDPOINT/detect?returnFaceAttributes=age,gender" -H "Content-Type: application/json" -H "Ocp-Apim-Subscription-Key: YOUR-API-KEY-HERE" --data-ascii '{"url":"YOUR-API-KEY-HERE"}'
```

  > Be sure to replace **YOUR-ENDPOINT** with your actual endpoint, **YOUR-API-KEY** with your actual API key, and **YOUR-PHOTO-URL** with the URL for the face you chose.

  > Be VERY careful to **keep all the quotation marks exactly as they are**.

  5. Finally, after pasting in the above information into the cURL command, **run it* in your command line! Look at the response they send back: *how accurate is their face detection algorithm?*
  
<br/>

## Bonus challenges: 

### Bonus challenge 1:

Try adding more face attributes aside from just age and gender. They're all listed in [their Face Detection API documentation here](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236).

### Bonus challenge 2:

Try using the URL for an image of ***your own face***, just for fun!

<br/>

## Challenge 7: Use the `POST` HTTP method to create a repo on GitHub

We've mostly been sending `GET` requests to these APIs. Remember, the `GET` method is used to ask for some information, *without modifying any of that information.* The `POST` method, on the other hand, is used to ***create*** something new on the server that you're communicating with.

In cURL, we use the `--data` flag followed by a string of data (enclosed in quote marks) to send information in the ***body*** of our request. When cURL sees that flag, it automatically sends this as a `POST` request!

  > **Vocabulary note:** GitHub uses the word "repository" or "repo" for short to refer to your projects hosted on their website. Each project is a collection of files, which would normally be the code for a software application (or something else like a book of poems or whatever you want!)

**Your challenge:** Create a project on GitHub with their API by following the steps below:

   1. First, you need to create a free GitHub account.
   
   > GitHub is a social network for programmers and also the world's largest collection of source code! It's used for collaboration not just for code, but also for writing fiction, sharing open data, and getting feedback on legislation for local government, among other cool things!
   
  2. Request a ***personal access token*** by [following GitHub's instructions here](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/).
  
  > **Remember: treat your personal access tokens like passwords!** Don't share them anywhere or store them in any insecure places!
  
  3. Copy the cURL command below into your plain text file, and replace **YOUR-TOKEN-HERE** with your actual personal access token:
  
```bash
curl -H 'Authorization: token  YOUR-TOKEN-HERE' https://api.github.com/user/repos  --data  '{"name": "test-repo"}'
```

  4. Finally, copy and paste that command into your command line and run it!
  
  5. Check your GitHub profile page to see if it worked! You should see your new repository (in other words, your project) appear in your list of repositories!
  
  > To get to your GitHub profile page quickly, go to `https://github.com/YOUR-USERNAME-HERE` and replace **YOUR-USERNAME-HERE** with your actual GitHub username.

<br/>

## Bonus challenges: 

### Bonus challenge 1:

Look at [GitHub's API documentation for working with repositories](https://developer.github.com/v3/repos/) to figure out how to **edit** the name of the repository you created in the previous challenge!

Which *HTTP method* do you need to use here?

### Bonus challenge 2:

Figure out how to **delete** the repository you created in the previous challenge! And which HTTP method do you need for this?

<hr/>

:trophy: ***Congratulations!*** Now you know the most important basics of using third-party APIs! At this point, the sky's the limit as to what you can create using the countless APIs that other software developers are providing!
