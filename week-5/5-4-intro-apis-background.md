## 5.4: Intro to APIs (Application Programming Interfaces) and interfaces in general

You've certainly heard the term ***API*** thrown around a lot -- not just among techies, but also in the news and sometimes even in casual conversation! So what's this all about? ***API*** stands for ***Application Programming Interface***. In this section, we'll look at examples of interfaces and then examples of *application programming* interfaces to get a better sense of the overall picture.

:star: **Read [these notes on APIs in a shared Google Doc](https://docs.google.com/document/d/1HH5ULwRQwbByOVbjRdSqUPIQhZsAqlu7imTeX1AA6n4/edit?usp=sharing)!** The notes below will be formatted and updated here soon, but for right now they aren't formatted yet. (Oops, technical difficulties! :sweat_smile: Sorry bout that!)


<hr/>


## 5.4.1: What is an interface?

Application Programming Interfaces (APIs) are a pretty broad category of things -- as are interfaces in general! The term "API" is used to mean lots of different things, which definitely adds to the confusion. So let's first zoom out and look at what ***interfaces*** are in general:

:star: ***An interface allows two different entities (people, computers, software programs, etc) to interact or communicate.*** It's the *connection* and the *set of rules or conventions* that allow the two entities to communicate.

**Some examples of interfaces:**

  - [**User interfaces**](https://en.wikipedia.org/wiki/User_interface) allow humans to interact with anything from toasters to cars to computer programs to space ships! There are **physical** user interfaces like a computer keyboard, or general things like knobs and buttons and switches. There are also abstract **software** user interfaces, like a [command line interface](https://en.wikipedia.org/wiki/Command-line_interface) versus a [graphical user interface](https://en.wikipedia.org/wiki/Graphical_user_interface) that we use to move files around on our computers.

  - **Hardware interfaces** are the mechanical/electrical components that allow different pieces of a machine or a computer to interact with each other -- for example, the wires that connect a computer’s hard drive to its motherboard, or the HDMI cable you might use to connect a computer to a TV.

  - [**Application binary interfaces**](https://en.wikipedia.org/wiki/Application_binary_interface) allow code for computer applications to communicate with the operating system and the 1s and 0s, the machine code that the computer understands!

  - And finally, an [**application programming interface**](https://en.wikipedia.org/wiki/Application_programming_interface) or **API** is a higher-level software interface that allows different pieces of software to communicate or interact with each other. APIs can take many forms -- there are APIs for everything from web apps and web browsers to operating systems and everything in between! 

 > Curious about interfaces in general? I borrowed most of the above info directly from Wikipedia's page on interfaces, which is a really interesting read: https://en.wikipedia.org/wiki/Interface_(computing) 
 
 
## 5.4.2: What is an Application Programming Interface (API)?

Just as a graphical user interface (GUI) allows users to interact with software programs, ***an API allows one software program to interact with another.***

**Examples:**

  - Microsoft maintains a [Windows API](https://en.wikipedia.org/wiki/Windows_API) for their operating system, to make it easier for developers to build applications that run on Windows!

  - [**Web browser APIs**](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Introduction) are what allow us to use the JavaScript language to interact with a web browser! We've already been using the [**Document Object Model API**](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction) to let our JavaScript interact with a web page's HTML or CSS, using built-in API functions like `document.getElementById()`.

  - The [Console API](https://developer.mozilla.org/en-US/docs/Web/API/Console) is another built-in web browser API, which lets us interact with the web browser's console -- like our favorite `console.log()` function!
  
  - The [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API) lets us use JavaScript to create and play sounds (or music) right within the web browser.
  
  > And there are *many* other built-in web browser APIs! Take a look through this list from MDN: https://developer.mozilla.org/en-US/docs/WebAPI

  - **Third party web APIs** are probably the type of API that you'll hear about the most. These are APIs created by *other companies* that allow your program to communicate with their program *over the internet*. You may have heard of Twitter's API, YouTube's API and plenty of others!
  
  > **Note:** The term ***["third party"](https://en.wikipedia.org/wiki/Third-party_source)*** means that it was created by some other company or organization. If you created *your own* API that lets your own programs talk to each other over the internet, we would still call that a web API, just not a *third party* API. (And it is common for companies to build APIs for themselves!)
  
We'll explore some more examples of third party web APIs further below. But first, a quick vocabulary note:


## 5.4.3: Libraries versus APIs

The way these words are commonly used, software libraries and APIs are closely connected:

  - The **library** is ***all the code*** written by someone else to be shared and reused by other programmers. 
  
  - The ***library's API*** (or "the API for this library") is the **interface** that lets programmers ***use*** the library -- the functions/objects/etc that allow us to use the library's features in our own program.

:star: ***If the library is a microwave, then the API is the collection of buttons that allow you to cook your food!***

This idea extends to your own code as well: you should be writing your own functions and objects in a way that gives you a convenient interface to use them, without worrying about *all* the details every single time. (Another metaphor: a car should be easy to drive without understanding all the mechanics hidden away under the hood.)

And yes, software developers do create libraries and APIs for themselves! It helps keep our code [DRY (Don't Repeat Yourself)](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and reusable.


## 5.4.4: The basics of HTTP requests

**HTTP** stands for [***HyperText Transfer Protocol***](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol), and it's the set of rules that allow computers to communicate with each other over the internet -- it's the backbone of the World Wide Web!

  > **Fun fact:** HTTP was initially created by [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee), inventor of the World Wide Web, in 1989 at CERN.

  > ***Bonus fun fact:*** CERN is the home of the [Large Hadron Collider](https://home.cern/topics/large-hadron-collider), the largest single machine in the world, which smashes atoms and even smaller particles together at crazy high speeds in the name of science!

Any time your computer (the ***client***) visits a website, it makes a ***request*** via HTTP, which the web browser sends over the internet to a ***server***. (A server is just another computer that processes those requests, runs some code, and sends a response back to clients with the data they requested.)

Since HTTP is already so widely adopted (used by practically every computer in the world!), it's a convenient way for programmers to build their APIs on top of. That's why so many third-party APIs are based on HTTP.

### The four parts of an HTTP request

The following four things are sent by the client (your computer) every time you visit a web page (in other words, every time you make an HTTP request to some server on the internet):

  1. The **URL** (**U**niform **R**esource **L**ocator), like https://example.com -- this is the unique address for the data or web service you're interacting with.  

  2. The **HTTP request method** (also called the *HTTP verb*), which specifies what type of action is being requested for the server to perform. (See examples in the table below.)

  3. The **headers**, which contain important *meta-information* about the request -- for example, what type of data format the client will accept (examples: plain text, JSON, XML or others), whether the client is a mobile phone or a desktop computer, and lots more!

  4. The **body of the request**, which contains any *actual data* that needs to be sent to the server. For example, if you create a new account on Twitter, the body of the request would include your username, email, and password.


### Four most common HTTP request methods (or HTTP verbs)

| HTTP request method (or "verb") | The action it corresponds to |
| --- | --- |
| GET | Request some data (ex: to view any web page, or to search for something on Google) |
| POST | Submit data to the server, usually to create something new (ex: create a new project on Glitch or GitHub) |
| PUT | Replace existing data with new data (ex: update your relationship status on Facebook) |
| DELETE | Remove a piece of data entirely (ex: delete an embarrassing video that you had uploaded to YouTube) |

The **GET** and **POST** request methods are the most common by far. Most of the time when you're browsing the web, your web browser is just sending a bunch of GET requests. When you submit a form (especially with any private information like a password, bank account info, etc), that's usually sent as a POST request.

:books: **Extra resources:**
  - See GitHub's API documentation on how they use the HTTP verbs (they use some special ones in addition to the main four): https://developer.github.com/v3/#http-verbs 
  
  - You can also explore the HTTP verbs in more depth here: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods


### Example HTTP requests

**Example 1:** You go to https://example.com in your web browser to read what’s on their website:

  1. The URL: https://example.com 
  2. The HTTP request method: GET
  3. The headers probably include things similar to: "Accept: text/html" and "Accept-Language: en-us" and "User-Agent: Mozilla/5.0", etc
  4. The body of a GET request is usually empty

**Example 2:** You create a new GitHub account: 

  1. The URL: https://github.com/join or something similar
  2. The HTTP request method: POST
  3. The headers might be the same, including things similar to: "Accept: text/html" and "Accept-Language: en-us and "User-Agent: Mozilla/5.0", etc
  4. The body of the request: your new username, email, and password


## 5.4.5: Key terms for working with APIs

Here's a preview of some key concepts and terminology that will come up as you learn more about APIs:

### 1. Authentication

To *authenticate* a user means to verify that they are who they say they are. Authentication is an important step in accessing private information or acting on behalf of a user via an API.

For example: you can create a new GitHub repo through GitHub's API, but first you have to authenticate by logging into your user account and verifying that you are who you say you are!

For more on the GitHub API's authentication porcess, see this section of their docs: https://developer.github.com/v3/#authentication 

### 2. API rate limits

Many API providers will *limit* how often you can use their API. Why? Here are two main reasons:

  - Remember, sending things over the web uses up bandwidth, which costs money! API providers will create rate limits to help keep their expenses under control.
  
  - Even more importantly, rate limits also help to prevent abuse of the API -- for example, by overloading the API provider's servers with what's called a [denial-of-service (DoS) attack](https://en.wikipedia.org/wiki/Denial-of-service_attack).

For example, GitHub's API limits you to *60 requests per hour* if your requests are made anonymously. (If you associate your requests with a GitHub account, then you get 5000 requests per hour!)

  > See GitHub's API documentation for more on their rate limiting rules: https://developer.github.com/v3/#rate-limiting 

Another example: Google Maps provides an API for calculating the distance between two places, which is free up to a point, and then they start charging you money after that. You can see all the details here: https://developers.google.com/maps/documentation/distance-matrix/usage-limits 

### 3. API keys

Many APIs don't require authentication -- for example, if all of their data is already publicly available information (like an API that provides a weather report). But many companies that provide APIs still want to track who's using their API, both to prevent abuse/illegal activities and to collect data on who uses their API.

An **API key** is a unique ID assigned to your application.

To use the API for Twitter, Facebook, and many other web services, you to first have to make an account on their website, register your own web app with them with a description of what it does, and then finally they'll issue you an API key. That way, they'll know who you are whenever you use their API within your own programs.

<hr/>

:point_right: **Next...**
