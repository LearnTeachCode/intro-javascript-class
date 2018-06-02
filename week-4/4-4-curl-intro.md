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

Copy-paste the code below into your command line, and then press Enter to send a request to the server for `example.com` using cURL:

```bash
curl http://example.com/
```

**Your challenge:** Take a look at the results that appear in the command line, and compare it to the response body that you saw in Chrome's Network tab. ***Are they the same?***

<br/>

## Challenge 2:

Try running the command below, and take a look at the result. For an easier-to-read version of the same results, see [**our example cURL printout**](https://github.com/LearnTeachCode/intro-javascript-class/raw/may-2018-int/week-4/curl-verbose-example.pdf) (links to a PDF file download).

<br/>

Run this command and then press Enter to send the request:

```bash
curl http://example.com/ -v
```

<br/>

The `-v` flag at the end stands for **Verbose** mode, which will show *everything* being sent and received -- not just the body of the response (the web page itself), but also all the *headers* included in the request and the response!

<br/>

:star: **The *headers* contain *extra information* about the client, the server, how they're communicating, and some *meta-data* describing the information being sent and received.**

Note: When you see the data in your command line, the request headers are prefaced with the `>` symbol, and the response headers are prefaced with the `<` symbol (facing the opposite direction).

<br/>

**Discuss:**

  1. Do you see the same information in the command line that appeared in Chrome's network tab?
  
  2. Can you spot where it shows the HTTP request method?
  
  3. What's the value of `User-Agent` and what do you think it represents?
  
  4. Can you find the value of `User-Agent` in Chrome's network tab? Is it the same value in Chrome as it is in the command line using cURL?
  
  > **Hint:** Look at the request headers, which appear *above* the response headers and have the `>` symbol at the beginning of each line. This will appear *below* the "TLS handshake" stuff, which handles establishing a secure connection because we're using HTTP**S** and not HTTP. (The **S** stands for a **S**ecure connection.)
 
<br/>
<hr/>

:point_right: **Next up:** [in section 4.5, we'll get our feet wet by making API calls to a funny example API](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-5-api-challenges-1.md)!
