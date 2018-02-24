# 8.1: Let's try out the Network panel in Chrome's Developer Tools!

Web browsers like Chrome have [developer tools built right in](https://developer.chrome.com/devtools), with a **network panel** showing information about all the requests and responses happening under the hood every time you visit a website! Let's test it out:

:books: **Prerequisites and resources:**
  - Be sure to read [section 5.4: Intro to APIs and interfaces in general](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-4-intro-apis-background.md)

<hr/>

**1. In your browser, go to https://example.com/**

<br/>

**2. Open Chrome's DevTools**
  - Mac: Press `Command + Option + I` (`⌥ + ⌘ + I`)
  - Windows: Press the `F12` key OR press `Control + Shift + I`

<br/>

**3. Open the Network tab by clicking "Network" at the top:**

![Chrome Network panel](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel.png)

Or if your screen is smaller and you don't see "Network" listed there, click the `>>` on the right, and then click "Network" in the drop-down menu:

![Chrome Network panel from drop-down menu](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel2.png)

<br/>

**4. Refresh the web page to record the network data.**

  - Mac: Press `Option + R` (`⌘ + R`)
  - Windows: Press the `F5` key or press `Ctrl + R`

<br/>

**5. Click the name of the request for `example.com` to see more info about the request:**

![Example request in Chrome Network panel](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel-examplecom.png)

After you click on the name of the request, a right-side panel will open up showing all the information that was sent and received by your web browser when you asked it to take you to example.com:

![Response tab in Network panel](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel-response.png)

<br/>

### Scavenger hunt time! Identify the following:

  1. What is the request method?
  
  2. What is the status code?
  
  3. What is the content type?
  
  > **Hint:** Scroll down in the "Headers" tab to see the response headers
  
  3. What is the body of the response?
  
  > **Hint:** Click on the "Response" tab (which is to the right of the "Headers" and "Preview" labels), and you'll see the entire rsponse body -- everything that the example.com servers sent to your web browser.
  

<hr/>

:point_right: **Next up:** [**let's test this out in the command line!**](https://github.com/LearningNerd/intro-apis-workshop/blob/master/curl-intro.md)
