# 4.4: Intro to API requests via the command line with cURL

In the [previous section](https://github.com/LearningNerd/intro-apis-workshop/blob/master/network-tab.md), we learned how to use the network panel in Chrome's built in developer tools to see *all* of the request and response data being sent and received every time you access a web page. Next, let's use an even *more powerful* tool for making HTTP requests: [**cURL**](https://en.wikipedia.org/wiki/CURL)!

**cURL** is a command line tool for accessing and transferring data over the internet. It basically does what your web browser does, but without the graphical user interface, and with a LOT more control over how you send your requests!

![cURL logo](https://upload.wikimedia.org/wikipedia/commons/thumb/8/8a/Curl-logo.svg/320px-Curl-logo.svg.png)

  > **Fun fact:** The name cURL originally was pronounced "C - URL", as in "See URL", to see the data from any URL. But now we just pronounce it "curl" (like the weight lifting term, as in [bicep curls](https://en.wikipedia.org/wiki/Biceps_curl)).

<hr/>

<br/>

## Opening the command line

It should only take a couple minutes to get set up. :) Follow the instructions below:

### Mac users:

If you're on a **Mac**: open the **Terminal** app to access your computer's command line. Easy!

  > You can search for "Terminal" in Finder or in Spotlight, wherever your normally search for things on your computer.

<br/>

### Windows users:

To make this as easy as possible, for now we'll use the command line built into [Glitch](https://glitch.com) (which is a free online tool for writing and sharing code):

  1. **Remix this Glitch project: https://glitch.com/edit/#!/command-line-practice-1**

  2. On the left-side menu, **click "Logs"** and a window will pop up at the bottom of the screen
  
  3. To the left of the words "Activity Log", **click the "Console" button**
  
  4. A new tab will open with a command line interface that has the `curl` command built-in and ready to use:
  
![Using the console in Glitch](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/glitch-4.png)

<br/>

## Challenge 1:

Copy-paste the code below into your command line, and then press Enter to request `example.com` using cURL:

```bash
curl http://example.com/
```

Compare the response body to the response you saw in the Network tab. ***Are they the same?***

<br/>

## Challenge 2:

....

<br/>
<hr/>

:point_right: **Next up:** [**let's tackle a fun series of practice challenges using cURL to access some fun APIs!**](https://github.com/LearningNerd/intro-apis-workshop/blob/master/api-challenges-1.md)
