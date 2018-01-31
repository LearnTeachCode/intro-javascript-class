## 5.4: Intro to APIs (Application Programming Interfaces) an interfaces in general

You've certainly heard the term ***API*** thrown around a lot -- not just amoung techies, but also in the news and sometimes even in casual conversation! So what's this all about? **API** stands for **A**pplication **P**rogramming **I**nterface. In this section, we'll look at examples of interfaces and then examples of *application programming* interfaces to get a better sense of the overall picture.

:star: **Read [these notes on APIs in a shared Google Doc](https://docs.google.com/document/d/1HH5ULwRQwbByOVbjRdSqUPIQhZsAqlu7imTeX1AA6n4/edit?usp=sharing)!** The notes below will be formatted and updated here soon, but for right now they aren't formatted yet. (Oops, technical difficulties! :sweat_smile: Sorry bout that!)


<hr/>


## 5.4.1: What is an interface?

Application Programming Interfaces (APIs) are a pretty broad category of things -- as are interfaces in general! In fact, it's a hugely overloaded* term; in other words, it's probably used to mean *too many* different things at this point. It's definitely a bit confusing! So let's start with the definition of an interface in general.

***An interface is anything that allows two different entities (people, computers, software programs, etc) to interact or communicate.***

**Some examples of interfaces:**

User interfaces allow humans to interact with anything from toasters to cars to computer programs to space ships! There are physical user interfaces like a computer keyboard, or general things like knobs and buttons and switches. There are also abstract software user interfaces, like a command line interface versus a graphical user interface that we use to move files around on our computers.

Hardware interfaces are the mechanical/electrical components that allow different pieces of a machine or a computer to interact with each other -- for example, the wires that connect a computer’s hard drive to its motherboard, or the HDMI cable you might use to connect a computer to a TV.


Application binary interfaces allow code for computer applications to communicate with the operating system and the 1s and 0s, the machine code that the computer understands!

And finally, an application programming interface or API is a higher-level software interface that allows different pieces of software to communicate or interact with each other. APIs can take many forms -- there are APIs for everything from web apps and web browsers to operating systems and everything in between! 

Just as a Graphical User Interface (GUI) makes it easier for users to interact with software programs, an API makes it easier for programmers to create new computer programs.

Software libraries and APIs are intimately linked! The library is all the code written by someone else to be shared and reused by other programmers. The library’s API is the abstract interface that lets programmers use the library -- the functions/objects/etc that allow you to use the library’s features in your own program.

If the library is a microwave, then the API is the collection of buttons that allow you to cook your food! This idea extends to your own code as well: you should be writing your own functions and objects in a way that gives you a convenient interface to use them, without worrying about the details hidden away inside them (all the guts, the inner workings under the hood).

Example: Microsoft maintains a Windows API for their operating system, to make it easier for developers to build applications that run on Windows!

Web browser APIs are what allow us to use the JavaScript language to interact with a web browser. We’ve been using the Document Object Model API to let our JavaScript interact with a web page’s HTML or CSS with built-in API functions like document.getElementById().

The Console API lets us interact with the web browser’s console (like console.log()!). The Web Audio API lets us use JavaScript to tell the web browser to play sounds! (And there are many more awesome browser APIs!)

Third party web APIs are what you probably hear about the most -- APIs created by companies and organizations to let you create programs that communicate or interact with their programs over the internet. You may have heard of Twitter’s API, YouTube’s API and plenty of others! We’ll explore some more examples of APIs below. :)

Curious about interfaces in general? I borrowed most of the above info directly from Wikipedia’s page below, which is a really interesting read: https://en.wikipedia.org/wiki/Interface_(computing) 

<hr/>

:point_right: **Next, we'll look deeper into how functions work with the `return` statement and the concept of variable scope.**
