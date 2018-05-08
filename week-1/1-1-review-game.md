# 1.1: Let's review by making a game!

Welcome back! :smile: We're about to start on another crazy new adventure in this intermediate class: databases and APIs and JSON, oh my! But before we dive into the new material, let's build a (super tiny) game to review some basics of using JavaScript to interact with a web page. This will also serve as a model for the planning process that you'll use for all your future projects.

❓ **If you have any questions,** please remember to ask on the private Slack channel for our class.

:books: **Prerequisites:**
  - Definitely make some time to review [our beginner class curriculum from March 2018](https://github.com/LearnTeachCode/intro-javascript-class/tree/march-2018) -- not all at once, of course! Just keep that bookmarked and take a look through it little by little whenever you need a refresher.

 <hr/>

## Planning out the game

:hammer: **First, what are we building?** Let's create one of the simplest video games ever invented: **a click-counter game!** Yes, there's an entire genre of games where the sole purpose is to click a button as many times as you can. (Usually there's a time limit, but we'll leave that out for now.)

**Feature requirements:**

  - There should be a button that the user can click on.
  - And there should be a paragraph that says how many times the button was clicked.
  - Every time the user clicks that button, the number of clicks should increase by one, and that new number should be displayed in the paragraph described above.
  - Initially, that paragraph should say that the button was clicked **0** times.
  - ... and that's all!

As with any project, no matter how big or small, we'll begin by making a plan. This means *no coding* and *no computers* needed at all for these first steps!

<br/>

## Challenge 1:

:hourglass_flowing_sand: Get out your pencils and paper! In ***two minutes or less***, draw a quick sketch of the user interface for this application. Keep it simple. (It is a ridiculously simple game, after all!)

<br/>

## Challenge 2:

**Discuss the following, and write down both your answers and your questions:**

  1. How can we use JavaScript variables to keep track of the **state** of this system? (By [*state*](https://en.wikipedia.org/wiki/State_(computer_science)), we mean any piece of information that changes over time and affects what the computer program will do next.)

  2. What **data type(s)** do we need to use in this program?

  > **Refresher:** The phrase "data type" refers to how we want the computer to interpret a piece of information -- for example, there's a difference between the area code **"90017"** (data type: a string!) and **90017** the number; we can do math with numbers, but we can't multiply or divide zip codes. (Well, we could... but that wouldn't make any sense!)

  3. How many **HTML elements** will your JavaScript code need to interact with? What do we need to *access* or *change* for each of these elements?

  4. What **external events** (outside the control of your code) will affect the state of this system?

<br/>

## Challenge 3:

:hourglass_flowing_sand: In ***two minutes or less***, sketch out a quick **flowchart** of the steps required for this game to work. Be as detailed as possible; imagine you're the computer outlining the steps that need to happen in your code!

<br/>

## Challenge 4:

**Write some pseudocode: a list of the steps that your code needs to accomplish** for this game to work. This should be plain English, *not code*, but it should specific enough that you could hand this list to any programmer and they'd be able to understand your intentions and turn it into code.

:question: **Write down any questions you have as well!** It's important to write down your questions as soon as you think of them.

  > We call it ***pseudocode*** because it's halfway between plain English and actual code. This isn't just something that beginners do; most professional software engineers write pseudocode to make sure they didn't skip any details in the planning process before diving into writing the actual code. It's *super* helpful!

<br/>

## Challenge 5:

Time for a little scavenger hunt! **For each step in the pseudocode, make a list of all the JavaScript functions, operators, and general concepts** that you'll need to accomplish that step of the pseudocode.

Be sure to write down all of your questions as well!

**Past coding challenges for hints and review (from our beginner curriculum):**

  - [Creating variables and displaying them in the console (section 1.3, challenge #3 and #4)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-3-variable-challenges.md#challenge-3)

  - [Making text appear in a specific HTML element (section 1.2, challenge #5)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-2-dom-challenges.md#challenge-5)
  
  - [Event listeners example (section 2.2)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-2-event-listener-challenges.md#first-an-example)
  
  - [Reference page on arithmetic operators from MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators)
  
  - [Combining two strings together (section 1.3, challenge #6)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-3-variable-challenges.md#challenge-6)

<br/>

## Challenge 6:

**Now let's finally write the code!** After all our hard work in making sure we understand every piece of this system, writing the code will be *so* much easier than if this were our very first step.

<br/>

:star: **Remix this Glitch project as your starting template,** which has the HTML and CSS completed, but no JavaScript: https://glitch.com/edit/#!/dragon-defeater-v0-starter

:pray: **Only** ***one*** **person in each pair should remix the project on Glitch,** while we're together in person. We'll make use of Glitch's real-time collaboration feature (just like Google Docs), so you can both write code in the same project at the same time on your different computers!

<br/>

**Glitch instructions** (a refresher):

  - First, **log in** to Glitch using your GitHub account if you haven't already. (Or [make a GitHub account](https://github.com/join) first if needed.)

  - To **remix** a project on Glitch, click the project's name in the top left corner, and then click "Remix This" in the dropdown menu to make your own personal copy.
  
  - To **invite collaborators** to write code in your project together, click the "Share" button on the top left (below the project's name). In the menu that appears, copy the link at the bottom under "Invite collaborators to edit". Send that link to whoever you'd like to invite as a collaborator, and they should instantly have access to add/edit/delete the code in that project!
  
  - **To see the live app and test it out**, click "Show Live" on the top left and it'll open the web page in another tab.

  - Remember to check *both* the **live web app** and the **JavaScript console in Chrome's developer tools** to see the results of your code, hunt down any bugs, and check if you've fixed those bugs!

  > If you need a refresher on what Glitch is all about, you can review our [**intro to Glitch video** in section 1.1.3 of our beginner curriculum from March](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#113-intro-to-glitch).

<br/>

<hr/>

:trophy: **Congrats!** It may not seem like much, but building an app from start to finish is a *big* win! No matter how ambitious or complex your project may be, you'll always go through a similar process to break it down into bite-sized pieces with clear, step-by-step instructions that will gradually turn your ideas into a working product.

:point_right: **Next up:** [in section 1.2, we'll review a bit about JavaScript objects and add a new feature to this game](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-2-review-objects.md), leading up to our first look at persistent data and how to get started with the Firebase database library!
