## 5.4: Intro to APIs (Application Programming Interfaces) and interfaces in general

You've certainly heard the term ***API*** thrown around a lot -- not just among techies, but also in the news and sometimes even in casual conversation! So what's this all about? ***API*** stands for ***Application Programming Interface***. In this section, we'll look at examples of interfaces and then examples of *application programming* interfaces to get a better sense of the overall picture.

:star: **Read [these notes on APIs in a shared Google Doc](https://docs.google.com/document/d/1HH5ULwRQwbByOVbjRdSqUPIQhZsAqlu7imTeX1AA6n4/edit?usp=sharing)!** The notes below will be formatted and updated here soon, but for right now they aren't formatted yet. (Oops, technical difficulties! :sweat_smile: Sorry bout that!)


<hr/>


## 5.4.1: What is an interface?

Application Programming Interfaces (APIs) are a pretty broad category of things -- as are interfaces in general! The term "API" is used to mean lots of different things, which definitely adds to the confusion. So let's first zoom out and look at what ***interfaces*** are in general:

:star: ***An interface is anything that allows two different entities (people, computers, software programs, etc) to interact or communicate.***

**Some examples of interfaces:**

  - [***User interfaces***](https://en.wikipedia.org/wiki/User_interface) allow humans to interact with anything from toasters to cars to computer programs to space ships! There are **physical** user interfaces like a computer keyboard, or general things like knobs and buttons and switches. There are also abstract **software** user interfaces, like a [command line interface](https://en.wikipedia.org/wiki/Command-line_interface) versus a [graphical user interface](https://en.wikipedia.org/wiki/Graphical_user_interface) that we use to move files around on our computers.

  - ***Hardware interfaces*** are the mechanical/electrical components that allow different pieces of a machine or a computer to interact with each other -- for example, the wires that connect a computer’s hard drive to its motherboard, or the HDMI cable you might use to connect a computer to a TV.

  - [***Application binary interfaces***](https://en.wikipedia.org/wiki/Application_binary_interface) allow code for computer applications to communicate with the operating system and the 1s and 0s, the machine code that the computer understands!

  - And finally, an [***application programming interface***](https://en.wikipedia.org/wiki/Application_programming_interface) or ***API*** is a higher-level software interface that allows different pieces of software to communicate or interact with each other. APIs can take many forms -- there are APIs for everything from web apps and web browsers to operating systems and everything in between! 

 > Curious about interfaces in general? I borrowed most of the above info directly from Wikipedia's page on interfaces, which is a really interesting read: https://en.wikipedia.org/wiki/Interface_(computing) 
 
 
## 5.4.2: What is an Application Programming Interface (API)?

:star: Just as a graphical user interface (GUI) allows users to interact with software programs, ***an API allows one software program to interact with another.***

**Examples:**

  - Microsoft maintains a [Windows API](https://en.wikipedia.org/wiki/Windows_API) for their operating system, to make it easier for developers to build applications that run on Windows!

  - [***Web browser APIs***](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction) are what allow us to use the JavaScript language to interact with a web browser! We've already been using the [**Document Object Model API**](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) to let our JavaScript interact with a web page's HTML or CSS, using built-in API functions like `document.getElementById()`.

  - The [Console API](https://developer.mozilla.org/en-US/docs/Web/API/Console) is another built-in web browser API, which lets us interact with the web browser's console (like `console.log()`!).
  
  - The [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API) lets us use JavaScript to tell the web browser to play sounds!
  
  > And there are *many* other built-in web browser APIs! Take a look through this list from MDN: https://developer.mozilla.org/en-US/docs/WebAPI

  - ***Third party web APIs*** are probably the type of API that you'll hear about the most. These are APIs created by *other companies* that allow your program to communicate with their program *over the internet*. You may have heard of Twitter's API, YouTube's API and plenty of others!
  
  > **Note:** The term ***["third party"](https://en.wikipedia.org/wiki/Third-party_source)*** means that it was created by some other company or organization. If you created *your own* API that lets your own programs talk to each other over the internet, we would still call that a web API, just not a *third party* API. (And it is common for companies to build APIs for themselves!)
  
We'll explore some more examples of third party web APIs further below. But first, a quick vocabulary note:


## 5.4.3: Libraries versus APIs

The way these words are commonly used, software libraries and APIs are closely connected:

  - The ***library*** is ***all the code*** written by someone else to be shared and reused by other programmers. 
  
  - The ***library's API*** (or "the API for this library") is the **interface** that lets programmers ***use*** the library -- the functions/objects/etc that allow us to use the library's features in our own program.

:star: **If the library is a microwave, then the API is the collection of buttons that allow you to cook your food!**

This idea extends to your own code as well: you should be writing your own functions and objects in a way that gives you a convenient interface to use them, without worrying about *all* the details (the guts, the inner workings under the hood).

And yes, software developers do create libraries and APIs for themselves! It helps keep your code [DRY (Don't Repeat Yourself)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and reusable.


<hr/>

:point_right: **Next...**
