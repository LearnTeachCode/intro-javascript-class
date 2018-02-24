# 8.2: Start using cURL in the command line

In the [previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-8/8-1-network-tab.md), we learned how to use the Network panel in Chrome's built in developer tools to see *all* of the request and response data being sent and received every time you access a web page. Next, let's use an even *more powerful* tool for making HTTP requests: [**cURL**](https://en.wikipedia.org/wiki/CURL)!

**cURL** is a command line tool for accessing and transferring data over the internet. It basically does what your web browser does, but without the graphical user interface, and with a LOT more control over how you send your requests!

![cURL logo](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Curl-logo.svg/320px-Curl-logo.svg.png)

  > **Fun fact:** The name cURL originally was pronounced "C - URL", as in "See URL", to see the data from any URL. But now we just pronounce it "curl" (like the weight lifting term, as in [bicep curls](https://en.wikipedia.org/wiki/Biceps_curl)).

<br/>

## Get your command line tool set up

It should only take a couple minutes to get things set up. :) Follow the instructions below:

<br/>

### Mac users:

If you're on a **Mac**: open the **Terminal** app to access your computer's command line. Easy!

  - You can search for "Terminal" in Finder or in Spotlight, wherever your normally search for things on your computer.

<br/>

### Windows users:

To make this as easy as possible, for now we'll use the command line built into [Glitch](https://glitch.com) (which is a free online tool for writing and sharing code):

<br/>

**1. [Click this link to **create a new project on Glitch**](https://glitch.com/edit/#!/remix/hello-website).**

  > **Note:** You don't need to make an account.

<br/>

**2. Click on the project name in the top left corner.**

The name of your project will be a randomly-generated a pair of words, like "plastic-sardine", "shrouded-oxygen", or something equally silly:

![Glitch project link](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/glitch-1.png)

<br/>

**3. In the drop-down menu, click "Advanced Options" at the very bottom:**

![Glitch advanced options menu](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/glitch-2.png)

<br/>

**4. Then click "Open Console":**
  
![Glitch open console](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/glitch-3.png)

<br/>

**5. A new tab will open with your browser!**

It'll have a black background and some white or green text. You can type in here -- this is your command line for today!

![Using the console in Glitch](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/glitch-4.png)

<br/>

## Make your first cURL request

Copy-paste the code below into your command line, and then press Enter to request `example.com` using cURL:

```bash
curl http://example.com/
```

Compare the response body to the response you saw in the Network tab. ***Are they the same?***

<hr/>

:point_right: **Next up:** [**let's tackle a fun series of practice challenges using cURL to access some fun APIs!**](https://github.com/LearningNerd/intro-apis-workshop/blob/master/api-challenges-1.md)
