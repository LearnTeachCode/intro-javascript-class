# 6.2: GitHub API challenges: Making POST, PUT, and DELETE requests

So far, in our past classes and [in the previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-6/6-1-github-api-group-project.md), we've only used one of the HTTP request methods: GET. (Remember, the GET method is used to ask for some information, *without modifying any of that information.*)

Now let's make use of the other three most common methods to create, modify, and delete data on GitHub's servers using  their API!

:books: **Prerequisites:**
  - [Review APIs and using cURL from week 4 here](https://github.com/LearnTeachCode/intro-javascript-class/tree/may-2018-int/week-4)
  - [Review the four most common HTTP request verbs in section 4.2](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-2-apis-intro-http.md#four-most-common-http-request-methods-or-http-verbs)

<hr/>

## Challenge 1:

The `POST` method is used to ***create*** something new on the server that you're communicating with.

When using `curl`, we use the `--data` flag followed by a string of data (enclosed in quote marks) to send information in the ***body*** of our request. When the `curl` command sees that flag, it sends your data as a `POST` request!

<br/>

**Your challenge:** Using `curl`, try to create a new project (called a *repository*, or *repo* for short) on your own GitHub account using their API:

  1. Search through [**GitHub's API documentation**](https://developer.github.com/v3/) to find the section that explains how to work with *repositories*.

<br/>

  2. Identify the ***endpoint*** that GitHub uses for *creating* new repos on a user's account.

<br/>

  3. Reviewing the input that GitHub requires you to send to them in your API request, which inputs are ***required***? (We'll ignore all the optional ones for now.)

<br/>
 
  4. In your browser console, create a new JavaScript object with *one* property: the required input name from GitHub's documentation. Give it a string as a value (something like `"test123"` is fine).

<br/>
 
  5. Use `JSON.stringify()` with that object to turn it into a string, packaging up your data so you can now send it to GitHub!

<br/>
 
  6. Use `curl` to send a request to GitHub's endpoint for creating new repos, and include the `--d` flag followed by your JSON-formatted string.
  
***Note:*** It's easiest if you copy-paste your string straight from your browser console and then surround your string with single quotes, as in the example below. (Because it uses *double* quotes internally.)
  
```bash
curl https://some_URL_here  --data  'your JSON string "with double quotes" goes in these single quotes'
```

<br/>

*...did it work?* If you got back a message saying that your request requires authentication, then congratulations! You're done with this challenge! Read on for the next steps.

<br/>

## API keys and authentication

So far, we've only used APIs to request *publicly available* information, so we didn't need to do anything other than access a URL -- just like how we can access many websites simply by typing the URL into the browser's navigation bar.

But when you want to access *private* information or change data that *belongs to someone*, it's not that simple! And thank goodness for that; otherwise, any random person could see what's in your bank account, delete your personal Facebook photos, change your name on LinkedIn to "Goofy McGoofyFace", or create all sorts of other chaos!

<br/>

Say you want to publish a new post on Facebook or Twitter or Instagram (or insert your favorite social network here). What's the *very first step* that you need to take?

You need to log into your account and *authenticate* yourself by providing a password that (hopefully) only you know. 

<br/>

:star: ***Authentication is the process of verifying that somebody is who they say they are.***

<br/>

So to create a new GitHub project on your account, you first have to prove that you're *you*! That's one of the primary purposes of an API key.

:star: **An ***API key*** is a unique ID assigned to your application, which you should treat like a password.**

<br/>

To use the API for Twitter, Facebook, and many other web services, you first need to make an account on their website, register your own web app with them with a description of what it does, and then finally they'll issue you an API key. That way, they'll know who you are whenever you use their API within your own programs.

<br/>

## Getting a personal access token from GitHub

When you're simply testing an API with *only your own account* on GitHub, and you're not building an app to be used by other people yet, GitHub offers a convenient alternative to going through the whole process of registering your web app with them and getting an API key.

Instead, you can just use a ***personal access token***, basically a very long password that lets you authenticate (prove that you're you)!




