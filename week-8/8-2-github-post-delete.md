# 8.2: GitHub API challenges: Making POST and DELETE requests

So far, in our past classes and [in the previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-8/8-1-github-api-project.md), we've only used one of the HTTP request methods: GET. (Remember, the GET method is used to ask for some information, *without modifying any of that information.*)

Now let's use a couple of the other most common HTTP request methods to create, modify, and delete data on GitHub's servers using  their API!

:books: **Prerequisites:**
  - [Review APIs and using cURL from week 5 here](https://github.com/LearnTeachCode/intro-javascript-class/tree/july-aug-2018/week-5)
  - [Review the four most common HTTP request verbs in section 5.1](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-5/5-1-apis-intro.md#four-most-common-http-request-methods-or-http-verbs)

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

<br/>

***Note:*** It's easiest if you copy-paste your string straight from your browser console and then surround your string with single quotes, as in the example below:
  
```bash
curl https://some_URL_here  --data 'your JSON string "with double quotes" goes in these single quotes'
```

<br/>

***...did it work?***

If you got back a message saying that your request requires authentication, then congratulations! You're done with this challenge! Read on for the next steps.

<br/>

## Authentication and personal access tokens

Say you want to publish a new post on Facebook (or your other favorite social network). What's the *very first step* that you need to take?

You need to log into your account by providing a password that (hopefully) only you know! That's how you prove that you're ***you***.

<br/>

:star: ***Authentication is the process of verifying that somebody is who they say they are.***

<br/>

To create a new GitHub project on your account, you can *authenticate* yourself in a couple of different ways:

  1. Go to GitHub's website, type in your username and password, and then [click the "New repository" button](https://github.com/new). 
  
  2. Or you can use GitHub's API -- but instead of sending your username and password, you can send a ***personal access token***, which is essentially just a password, but with a little extra flexibility.

<br/>

Personal access tokens are convenient when you're testing an API or building a tool that's meant to be used *only by you* (you're not building an app to be used by other people).

They grant permissions for only certain tasks -- for example, creating projects but not deleting them. So if somebody else gets hold of your personal access token, the damage they can do is more limited. (If they got hold of your password, there's no restriction to what they can do!)

<br/>

## Challenge 2:

Create your own personal access token by [following GitHub's instructions here](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/).

  > **Remember:** treat your personal access tokens like passwords! Don't share them with anyone or store them in any insecure places!

<br/>

## Challenge 3:

Remember from our previous class when we used `curl` to get a random joke from the Dad Jokes API in a particular data format?

We used the `-H` flag (which stands for Header) to send some extra information as part of our HTTP request. For example, here's how we sent a header named `Accept` with the value of `application/json` to request a joke in JSON format:

```
curl -H "Accept: application/json" https://icanhazdadjoke.com/
```

<br/>

GitHub lets you *authenticate* by sending your personal access token within a header named `Authorization`, with a value of `token YOUR-ACTUAL-TOKEN-HERE`. So your `curl` request would look something like this:

```
curl -H "Authorization: token YOUR-ACTUAL-TOKEN-HERE" https://some_URL_here
```

<br/>

**Your challenge:** Create a new repo on your GitHub account by again making a POST request using `curl` -- but this time include your personal access token in the request headers, copying pieces from the example above.

<br/>

**To see if it worked:** Check your GitHub profile page by going to https://github.com, clicking your profile photo in the top right, and then clicking on "Your profile" in the pop-up menu. You should see your new project appear in your list of repositories!

<br/>

## Challenge 4:

Make another API request using `curl` to ***change*** the name of the GitHub repo that you just created:

<br/>

  1. Look through [GitHub's API documentation for repositories](https://developer.github.com/v3/repos/) and identify the ***endpoint*** for changing a GitHub repo.
  
  <br/>
  
  2. What are the endpoint's two ***parameters*** that you'll need to replace with your own values? Identify what values you'll be using here -- they'll be different for everyone!
  
  > **Hint:** Remember the name that you chose for your new repository.
  
  <br/>
  
  3. Make another `curl` request by copying your previous request and only changing two things: the name of your project, and the API endpoint (in other words, the URL).

<br/>

**To see if it worked:** Go back to your GitHub profile page again -- you should see that your repo now has a new name!

<br/>

## Setting the HTTP request method with the `-X` flag in cURL:

There's one more flag we'll use with `curl` today -- the `-X` flag. This sets the HTTP request method that we want to use. For example, to make a GET request to the Dad Jokes API:

```
curl -X "GET" https://icanhazdadjoke.com/
```

<br/>

If we don't specify which HTTP request method to use and there's no `--data` flag, then `curl` makes a GET request by default. If there *is* data being sent and there *is* a `--data` flag, then `curl` will automatically send it as a POST request.

<br/>

## Challenge 5:

Make one more API request to ***delete*** the repo that you just created.

<br/>

  1. Once again, look through [GitHub's API documentation for repositories](https://developer.github.com/v3/repos/) and identify the ***endpoint*** for deleting a GitHub repo.

  <br/>
  
  2. Identify the HTTP request method -- not GET or POST, but something else!
  
  <br/>
  
  3. Make the request with `curl` and be sure to specify which HTTP request method you want `curl` to use!
  
  > **Hint:** Notice that this endpoint does *not* require you to send any data in the body of your request, so you don't need to use the `--data` flag with `curl` and you don't need to send any JSON data. <br/><br/> But you *do* still need to send your token in an authorization header.
  
<br/>

***...did it work?***

If you got back a message saying that you need to have admin rights to the repository, then congratulations! You've confirmed that your personal access token does *not* include permission to delete repos!

<br/>

## Challenge 6:

Go to [your GitHub personal access tokens](https://github.com/settings/tokens), click on the name of your token, and then scroll down the list of permissions and check the box next to ***"delete_repo"*** to allow this token to delete repositories. Last but not least, click the green ***"Update token"*** button at the very bottom of the page.

Then run your `curl` command from the previous challenge one more time to delete your repo!

<br/>

**To see if it worked:** Go back to your GitHub profile page again -- you should see that your repo now has a new name!


<br/>
<hr/>

:trophy: **Great work!** Now that you've practiced identifying endpoints, sending your own JSON data, and using more of the most common common HTTP request methods, you know just enough to find your way around *any* API!

:point_right: **Next up:** [section 8.3 includes some suggested APIs to experiment with for your next projects!](#)
