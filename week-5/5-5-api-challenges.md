## 5.5: Intro to API challenges

Now that you have some [background info on APIs and how they work](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-4-intro-apis-background.md), let's get some hands-on practice using third party web APIs!

:books: **Prerequisites and resources:**
  - Be sure to read [section 5.4: Intro to APIs and interfaces in general](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-4-intro-apis-background.md)
  - You can do some very similar practice challenges following [GitHub's API "Getting Started" guide](https://developer.github.com/v3/guides/getting-started/)

<hr/>

## First, get set up to test out APIs in the command line!

  - If you're on a **Mac**: open the **Terminal** app to access your computer's command line. Easy!
  
  - If you're on **Windows**: for now we'll use the command line built into [Glitch](https://glitch.com). Create a new project on Glitch, then click on the project name in the top left corner, then click "Advanced Options" and then "Open Console".

We'll be using **cURL**, a command line tool for transferring data. We can use it to test APIs before we take the next steps of using them within our JavaScript code. (This is just like testing pieces of code in the console before you integrate them into your project -- always a good idea!)

## Challenge 1

You can use cURL to request any web page and see the actual data that the server sends every time you request a website in your web browser.

**Try this:**

```bash
curl http://example.com/
```

Next, try the above command with some of your favorite websites too!

## Challenge 2

The `curl` command has an option named `--include` (or `-i` for short) to include the ***headers***, which contain all the meta-information *about* the web page:

**Try this:**

```bash
curl --include http://example.com/
```

**Or try this shortcut version that does the same thing:**

```bash
curl -i http://example.com/
```

This shows you the complete response sent back from a server every time you request any web page! Now you can see what's happening behind the scenes -- the *guts* of the World Wide Web! Cool, right?

## Challenge 3

The [GitHub API](https://developer.github.com/v3/guides/getting-started/) has a URL that gives a random quote. **Try it several times to see all the different quotes they have:**

```bash
curl -i https://api.github.com/zen
```

Notice that the headers sent by GitHub include some custom information only used by GitHub's servers, which don't appear in the headers for other websites. (The programmers who wrote the code for GitHub's web servers get to decide what information is sent, what isn't sent, and all the other rules for how their API works.)

:question: **What custom headers do you see GitHub using that weren't used for other websites?**

## Challenge 4

To access your public GitHub profile information, just copy the code below and replace ***YOUR-USERNAME*** with your actual GitHub username:

```bash
curl https://api.github.com/users/YOUR-USERNAME
```

For example, you can request Liz’s GitHub profile with:

```bash
curl https://api.github.com/users/LearningNerd
```

Notice the format of the data you just received -- it’s **JSON (JavaScript Object Notation)**! Later you can use it in your JavaScript code easily enough!

  > **Note:** You can see everything GitHub allows you to do with their API in their official documentation here: https://developer.github.com/v3/ 
  
  > And their API reference page for accessing a user's info is here: https://developer.github.com/v3/users/

## Challenge 5

Say we want to access ***private*** information about our GitHub user account, like whether or not we're paying for GitHub or using their free plan. We can do that, as long as we first log in to our GitHub account. One quick way to do this is using what’s called ***Basic Authentication***, where we give GitHub our username and password to log in before sending our API request.

:star: **Note about GitHub's API:** If you're logged in, the `/user` endpoint (URL) will automatically assume you want *your own* account information. So copy-paste the code below exactly as it is; ***don't*** replace "user" with your username here:

```bash
curl -i -u YOUR-USERNAME https://api.github.com/user
```

It will prompt you for your password. Type it in (you won't see it while you're typing) and then press *Enter* to log in and send your request.

## Challenge 6

Basic authentication won't work if you have [two-factor authentication](https://help.github.com/articles/about-two-factor-authentication/) enabled for your GitHub account -- which you should use on *every* website that offers it, because it's much more secure that way!

If you have two-factor authentication enabled, here's another way to test GitHub's API while logged into your GitHub account: using a ***personal access token***.

  > **Note:** This uses a standard protocol called [OAuth](https://oauth.net/about/introduction/). Something to learn about later on!

Follow these instructions to create your personal access token on GitHub:
https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/

:star: **Treat OAuth tokens like passwords!** Don't share them anywhere or store them in any insecure places!

Now you can access your private GitHub profile info with the command below, replacing ***YOUR-TOKEN-HERE*** by copy-pasting your access token into the command line:

```bash
curl -H  'Authorization: token YOUR-TOKEN-HERE' https://api.github.com/user
```

***Note: If it didn't work, skip down to challenge 7 below.***

The `-H` option specifies a header to send to the server, and in this case we’re using it to send the ***Authorization header*** with your access token. (Just like you can use `-i` to show the headers the server sends to you, you can use `-H` to send your own headers back to the server!)

## Challenge 7

You can do more than just GET data from GitHub’s API; you can also create new data by sending a POST request to the server. (See the section in our notes on HTTP verbs.)

**To create a new project** (called a *repo* or *repository* on GitHub):

```bash
curl -H 'Authorization: token  YOUR-TOKEN-HERE' https://api.github.com/user/repos  --data  '{"name": "test-repo"}'
```

**Check your GitHub profile page to see if it worked** -- you should see your new project(s) in your list of repositories!

You can also use `-d` as a shorthand for the `--data` option, which means "send some data to the server" (using what's called a POST request). Here we sent some JSON data matching GitHub's API rules for how to create a new repository: https://developer.github.com/v3/repos/#create 

The response the server sends back to you is all the information GitHub knows about the newly-created repository, formatted as JSON.

<hr/>

:trophy: ***Congratulations!*** Now you already know the most important basics of using third-party APIs! Next, take a look at our class notes on APIs for suggestions of other APIs to explore and practice using. We'll return to this topic again and again, and later we'll learn how to use APIs from within our JavaScript code.
