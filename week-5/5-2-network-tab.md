# Section 5.2: Intro to the Chrome DevTools network panel

Web browsers like Chrome have [developer tools built right in](https://developer.chrome.com/devtools), with a **network panel** showing information about all the requests and responses happening under the hood every time you visit a website.

Let's test it out!

<hr/>

### **1. In your browser, go to https://example.com/**

<br/>

### **2. Open Chrome's DevTools**
  - **Mac:** Press `Command + Option + I` (`⌥ + ⌘ + I`)
  - **Windows:** Press the `F12` key OR press `Control + Shift + I`

<br/>

### **3. Open the Network tab by clicking "Network" at the top**

![Chrome Network panel](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel.png)

<br/>

Or if your screen is smaller and you don't see "Network" listed there, click the `>>` on the right, and then click "Network" in the drop-down menu:

![Chrome Network panel from drop-down menu](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel2.png)

<br/>

### **4. Refresh the web page to record the network data**

  - **Mac:** Press `Option + R` (`⌘ + R`)
  - **Windows:** Press the `F5` key or press `Ctrl + R`

<br/>

### **5. Click the name of the request for `example.com` to see more info about the request**

![Example request in Chrome Network panel](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel-examplecom.png)

  > :star: ***Note:*** Instead of seeing the status code `200`, you might see the status code `304`, which stands for "Not Modified". This happens when you've already visited a web page, and it hasn't been updated since your previous visit. <br/><br/> When that's the case, your web browser *does not* download it. Instead, it saves you time (and bandwidth) by opening the files for that website from where they're saved on your computer's hard drive! (Yes, your computer saves a lot of files from websites right onto your hard drive. We call that "caching" the files.)
  
<br/>

### **6. After you click on the name of the request, look in the right-side panel.**

This is where you can see *all* the information that was sent and received by your web browser when you asked it to communicate with `example.com`

![Response tab in Network panel](https://github.com/LearningNerd/intro-apis-workshop/blob/master/images/chrome-network-panel-response.png)

<br/>

## Challenge 1:

Looking in the network tab for `example.com`, identify the following:

  1. Which HTTP request method did your web browser send to the server? (Take a look to double check!)  

  2. What did the server send back to your computer as the response?
  
  > **Hint:** Click on the "Response" tab (which is to the right of the "Headers" and "Preview" labels), and you'll see the entire response body -- everything that the example.com servers sent to your web browser.
  
<br/>

## Challenge 2:

Open up the web page for our shared Glitch project from before https://reviewgroup2.glitch.me/ and then open up the network tab to inspect the information being sent to and from Glitch's servers when you visit that page!

**Identify the following:**

  1. Which request methods did your browser send to Glitch's server?
  
  2. How many requests did your web browser send? (How many files did it request for the server to send to your computer?)
  
  3. For each of those requests, what did the server send back as the response?

<br/>
<hr/>

:point_right: **Next up:** [in section 5.3, we'll use the command line to try out a much more powerful tool for making HTTP requests (for API calls)](#)!
