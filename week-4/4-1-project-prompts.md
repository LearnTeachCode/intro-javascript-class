# 4.1: Prompts and challenges for personal projects

Let's start building out our personal projects, with help from our awesome mentors who are volunteering to help us out! The goal is to publish a small but functional web app on GitHub and identify actionable next steps, both for your project and for your general learning goals.

✔️ **To submit this assignment:** Send me a link to your new GitHub repo! (We'll also be presenting these in a future class.)

❓ **If you have any questions**, please ask on the private Slack channel for our class. (See our [quick intro to Slack](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-1-initial-tools-intro.md#111-intro-to-slack) if you need a refresher.)

:books: **Prerequisites:**
  - If you haven't already, be sure to complete [homework 1.2: setting up your personal project](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/homework1-2.md).
  - Remember to use [all the class materials from previous weeks](https://github.com/LearnTeachCode/intro-javascript-class) as reference if you need to review anything!

<hr/>

## 1. Describe your project to our mentors

One of the most important steps in building *anything* is to get feedback on your ideas from other people! Here are some prompts for both students and mentors to consider during these conversations. ***Be sure to take notes and write down your answers!***

**For students to answer / for mentors to ask:**

  1. What's the *one sentence* description of your project idea? (This is your "elevator pitch", how you'd explain it to someone if you met them in an elevator and only had 30 seconds to describe it.)
  
  2. Very briefly, who is this project for? Who's your target audience? How general or specific is your audience?    
  
  3. Now onto some more details, since we are all software developers here: what are some of the implementation details you'll need to figure out how to build?    

**For mentors to give feedback:**

  1. Did you understand the project based on the elevator pitch? What details would help you better understand the goals of the project and how it's different from similar apps?
  
  2. Can you think of any other people that would want to use this app? Are you yourself part of the target audience?
  
  3. How would you rate the difficulty of building this project? How long would you guess it would take to build? Share your guess for *a couple different stages* of the project: how long for a first bare minimum prototype? How long for a more polished version for beta-testing? How long for a finished product? 
  
  4. Do you have any suggestions for how to *narrow down* the scope of the project for the very first prototype, keeping in mind this is a beginer project? Which features do you think are the most important? Which features would be the easiest to implement first?


## 2. Check out our example projects

  - Take a look at [Tinuola's Star Trek themed lorem ipsum (dummy text) generator](https://github.com/tinuola/ferengi-ipsum) -- try the [working demo](https://tinuola.github.io/ferengi-ipsum/) and look at [her HTML file](https://github.com/tinuola/ferengi-ipsum/blob/master/index.html) and [her JavaScript file](https://github.com/tinuola/ferengi-ipsum/blob/master/main.js) (only 38 lines of code). A great beginner project!
  
  - See [Roxana's minimal flowchart](https://github.com/rsgonzal/my-new-unknown-cool-project/blob/master/Screen%20Shot%202018-01-23%20at%208.14.08%20PM.png) for the first step in building her app -- super simple and targeted on just a couple first features, very doable!
  
  - Read over [Aaron's outline of implementation details](https://github.com/aabromowitz/Mindsweep) for his Minesweeper game, as well as [Frances' bullet points for her project](https://github.com/FrancesFisk/recipe-to-list) as examples of how to start planning and documenting your project.
  
  - Remember, you can always make a copy of [our very minimal Hangman game](https://glitch.com/edit/#!/hangman-v0-final) as a template and then modify it step by step to turn it into something for your own project!
  
  - For an example of a slightly more finished prototype that uses Firebase, check out [our Study Buddies web app](https://firebase-social-demo.glitch.me/) (and you can [see the code here](https://glitch.com/edit/#!/firebase-social-demo)).


## 3. Finish homework 1.2 and set up your project on GitHub

Now is the time to finally finish [homework 1.2](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/homework1-2.md) and get some documentation for your project published on GitHub! We're here to help you finish that today if you haven't already.

**Goals to complete (see [detailed instructions here](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/homework1-2.md)):**

  1. Create a GitHub repository for your project
  2. Add your project planning notes (from the prework you completed before our class)
  3. Outline your first implementation details
  4. Sketch a flowchart with implementation details -- this should be *very* minimal, like one tiny thing you'd like to build *today*!
  5. Build a simplified HTML mockup (again, this can be *very* minimal, like [our Hangman game example](https://hangman-v0-starter.glitch.me/))


## 4. Work together to implement the very first functional part of your app

Borrowing off some of the project examples above, let's actually start building our apps! (Or if you've already started, this is the time to work on the *next* feature you'd like to implement.)

**Suggestions for what to implement:**

  - When in doubt, use *comments* and `console.log()` statements in your code as an outline of what needs to happen, before you even write any actual code! This way you're not starting with just a blank page, and you can use comments as reminders for what you'll need to do next.
  
  - Decide on your ***data models*** for the information you need to store or work with in your app. Think in terms of *data types* (strings, numbers, Booleans, objects, etc) and also in terms of *nested objects/arrays* if needed!
    > Remember our object vs array discussion from a previous class? Now's the time to use what you learned!

  - Create some *fake data* or *hard-coded* variables for your app, and make sure they match your data models.
    > Examples: the answer was always the letter "a" for our Hangman game. The Star Trek dummy text generator only had a handful of sentences saved into an array in the JavaScript file.

  - Identify which pieces of your HTML mockup will need to be accessed or modified, and give them all unique IDs in your HTML file. Create JavaScript objects for each of them.
    > Be sure to use descriptive variable names that represent what each thing is. And remember to use camelCase format!
    
  - Interact with the user by implementing an event listener (or several!) and practice responding to the user's input, even if just using a placeholder or fake data at first.
    > Reference the example projects; there's nothing wrong with copy-pasting some code. But make sure you understand how it works! Even better if you do practice typing the code from scratch on your own!
    
  - Implement some basic logic for your app -- think conditional statements and loops! How does your app make decisions?
    > Example: the Hangman game needs to decide if the user won, lost, or can guess again. Feel free to reference that code.


## 5. Set up your own Firebase app and start using a database

If you have time to, this will be a fun next step to practice what we learned about Firebase in our previous class!

  - Identify one small part of your web app that requires (or could benefit from) ***persistent storage*** -- in other words, any data that will be *remembered* even after the user refreshes the page or leaves the website.
  
  - Redraw your flowchart if needed to make sure you know *what* needs to happen in your app to display, add, update, and/or delete data from your database, and *when* that needs to happen!
  
  - Follow [the instructions in section 3.4 to set up your very own Firebase database](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-4-firebase-setup.md) and confirm that it works! 
  
  - Be sure to practice *displaying* some fake data from your database, following [the last part of section 3.4](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-3/3-4-firebase-setup.md#343-displaying-data-from-your-firebase-database).
  
  - Try implementing a feature in your app to add, update, or remove data from your database. Remember to reference your updated flowchart to make sure you're writing this code in the right place / in the right order!
    > Use fake data as a first test! You don't need to worry about actually getting data from the user yet.

  - ... and of course if you still have more time, work on building out these features even further!
  
## 6. Publish your work and host your web app for free with GitHub Pages

Now that you have some progress to share, be sure to upload your code to your GitHub project and then [follow GitHub's instructions here](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/#enabling-github-pages-to-publish-your-site-from-master-or-gh-pages) to publish your app for free using GitHub Pages!


## 7. Share your project and get feedback from beta-testers

Next, be sure to share what you've built so far (even if it's not functional yet) and ask others to test it out for you! Then show them the code and walk them through how it works!

**Discussion prompts:**

  - Is it clear what the app is for, or how the user interacts with it? Could it use some more clear instructions?
  
  - Did it work as expected? Can you identify any bugs?
  
  - What are some ideas for the next features to implement?
  
  - Does the code look organized, well-formatted, and easy to read? Does it have comments to help make the code easier to skim over?
  
  - Are the variable names descriptive and easy to understand at a glance?
  
  - Do you have any suggestions for improving the data model(s) used and how they're implemented in the code?
  
  - Any other suggestions for improving the code?


## 8. Identify actionable next steps

Finally, reflect on what you've learned so far and discuss ideas for what to work on next.

**Discussion prompts:**

  - What areas of JavaScript programming and/or HTML could you use the most practice with?
  
  - What are some new tools, techniques, or topics you'd like to learn next?
  
  - What's the next feature you'd like to add to your app? What would be the most useful for users of your app, and what would be the most interesting for your own learning goals?
  
  - How would you prioritize your list of feature ideas? (First, second, third... etc)
  
  - What are some resources (tutorials, reference pages, videos, books, etc) that would help guide you towards achieving your next learning goals and feature ideas for your app? Discuss this and then if there's time, look things up online and bookmark some resources that look helpful!
  
  - Be sure to ***write down your action plan.*** You can publish this directly in your GitHub project, or anywhere else where you'll remember to find it later.

<hr/>

:star: Congrats! You're well on your way towards building a great portfolio project and learning *so* much more!
