# Homework: Class 1, part 1

:star: *I will be adding more homework and materials by the weekend, but wanted to share this first section with you ASAP so you can get started!*

✔️ **To submit this assignment:** Create a new Google doc, share it with me, and for each prompt below where it says `your answer here`, copy both the prompt and your answer into that Google doc.

❓ **If you have any questions**, please ask on the private Slack channel for our class. (See our [quick intro to Slack](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-1/1-1-initial-tools-intro.md#111-intro-to-slack) if you need a refresher.)

:clock2: **Time to complete: 1 to 2 hours.** Aim to spend 15 to 30 min on background reading, and 30 to 60 minutes on debugging.

  > **Note:** You're welcome to spend much more time on this if you're enjoying it!</br>
  Or if you don't find this assignment helpful, **please ask me if you'd like recommendations** for other practice challenges, recommended tutorials, etc.

**Table of contents:**
  1. Background reading: Bugs, debugging, and bug reports
  2. Make your own personal copy of our Hangman game 
  3. Document your debugging process

## 1. Background reading: Bugs, debugging, and bug reports

First, a couple quick definitions:

  - A **bug** is "an error, flaw, failure or fault in a computer program or system that causes it to produce an incorrect or unexpected result, or to behave in unintended ways." (via [Wikipedia](https://en.wikipedia.org/wiki/Software_bug))

  - **Debugging** is the process of finding, understanding, and (hopefully!) fixing a bug. (See [Wikipedia's page on debugging](https://en.wikipedia.org/wiki/Debugging) for many more details on the topic.)

  - A **bug report** is a document containing everything someone would need to know in order to identify a bug, replicate it, and fix it (or at least *help* fix it or *start* to fix it).

We won't be writing traditional bug reports for this assignment; we'll also borrow from the **[scientific method](https://www.khanacademy.org/science/biology/intro-to-biology/science-of-biology/a/the-science-of-biology)**:

  1. Make an observation.
  2. Ask a question.
  3. Form a hypothesis, or testable explanation.
  4. Make a prediction based on the hypothesis.
  5. Test the prediction.
  6. Iterate: use the results to make new hypotheses or predictions.

:microscope: If you aren't already familiar with it, **be sure to [read about the scientific method here](https://www.khanacademy.org/science/biology/intro-to-biology/science-of-biology/a/the-science-of-biology)**.

It takes a lot of practice to get good at debugging, but it's well worth it! The most important thing to keep in mind is: *be strategic!* Don't fall into the trap of ["shotgun debugging"](https://en.wikipedia.org/wiki/Shotgun_debugging), where you just make random changes to the code in the hope of fixing it! The resources below share some helpful wisdom on debugging and writing good bug reports.

:books: **Recommended resources:**

  - My personal favorite: StackOverflow's guide on ["How to create a Minimal, Complete, and Verifiable example (MCVE)](https://stackoverflow.com/help/mcve)
  
  - A much longer, more detailed article worth skimming over: [Mozilla Developer Network's "Bug writing guidelines"](https://developer.mozilla.org/en-US/docs/Mozilla/QA/Bug_writing_guidelines)

  - A short article with some excellent advice: ["How to Debug Small Programs"](https://ericlippert.com/2014/03/05/how-to-debug-small-programs/) by Eric Lippert
  
  - [Rubber duck debugging](https://en.wikipedia.org/wiki/Rubber_duck_debugging) is an actual thing, and a very effective technique!
  
  - Just for fun, read about [the history of the term "bug" in computing](https://en.wikipedia.org/wiki/Software_bug#Etymology) on Wikipedia (just a couple paragraphs), with a photo of the famous moth that caused a malfunction in one of the early computers -- in 1947!

:point_right: Next, let's dive into the code and practice debugging!


## 2. Make your own personal copy of our Hangman game

You can work directly inside Glitch, locally on your computer, or use any other tools that you prefer (like [CodePen](https://codepen.io/) or others). See the instructions below for setting up your personal copy of the project, either using Glitch or VS Code:


### Using Glitch:

📺 **[Video: Intro to Glitch](https://youtu.be/juqFTEoHN2Q) (6 min) - *This video covers the steps below:***

1. Go to this version of our project: https://glitch.com/edit/#!/hangman-v0-broken

2. Click the project title at the top left of the page.

3. Click "Remix This" in the drop-down menu.

4. After a moment, you should see a randomly-generated silly name at the top left. That's how you'll know it worked -- you now have your own personal copy! Feel free to rename the project to something like "yourname-hangman-test".

5. Remember to bookmark the page so you can easily get back to editing it later!

6. **To view and test your app:** click "Show Live" at the top left to open the live app in another browser tab.


### Using Visual Studio Code:

1. To quickly get all the starter code, download a .zip file of the project directly from GitHub here: https://github.com/LearnTeachCode/hangman-game/archive/master.zip

    > **Note:** If you're already comfortable using Git, feel free to clone the project from this GitHub repo: https://github.com/LearnTeachCode/hangman-game

2. Open the .zip file and you'll see a folder inside of it. Move that folder ***outside*** of the .zip file, and put it somewhere easy to find.

    > Personally, I like to keep all coding project folders inside one master folder, so they're all in one place. For example, on my computer I would put the hangman game folder into "C:\Users\Liz\Documents\Code-Projects".

3. To open the project, first open Visual Studio Code, and then go to File > Open Folder. Locate and click on your project folder, then click "Select Folder".

4. To open the files, double-click their names in VS Code's explorer view on the left. (Open that by going to View > Explorer, or click the Explorer icon at the top left.)

5. **To view and test the app in your web browser:** Using Finder on Mac or File Explorer on Windows, navigate to your project folder and then double-click the HTML file icon; it should open with your default web browser.

   > **Shortcut:** to quickly open your project folder from within VS Code, you can right-click any file name (or Ctrl + click on Mac) and then click "Reveal in Explorer" in the context menu.

💡 Remember to save your changes early and often with File > Save. Or even better, turn on the Autosave feature with File > Auto Save. Then you won't have to remember to click Save every time!


## 3. Document your debugging process

:trophy: **The challenge:** Following the prompts below, try to figure out what's wrong with our app and how to fix it, documenting each step as you go. *We'll share our bug reports in our next class, so be ready!*

It's OK if you don't actually solve it; the point here is just to come up with some ideas, practice debugging with a strategic and scientific approach, and share your process with the rest of our class.

:beetle: **The bug:** Remember where we left off at the end of class? Our super minimal Hangman game is basically finished, but there's one problem: **if the user enters the correct answer, the game still says "you lose!"** What went wrong?

:clock2: **Time to complete:** Aim to spend 30 to 60 minutes on this section. (But do more if you're having fun!)

  > Note: If you've *already* solved this bug, then please follow the prompts below to document *at least **two*** different ways to discover, confirm, or fix the bug.)

### Prompts for your debugging science experiment:

Taking inspiration from the scientific method as outlined in section 1 above, go through the following steps and write up *at least **two*** reports on your experiments, answering all the prompts below for *each* of your reports.

  > **Note:** We've already finished step 1 and 2 of [the scientific method](https://www.khanacademy.org/science/biology/intro-to-biology/science-of-biology/a/the-science-of-biology) as a group: we've *observed* the specific bug (you can't win the game!), and our questions are: *why* is this bug happening, and *how* can we fix it? So now you'll complete the next steps.

### 1. Your hypothesis: what do you think is causing the bug?

Even if you feel like you have *no idea*, take a guess! What are some possible issues that might cause our bug (and that, if fixed, would lead to our game working correctly)?

**Example:** *"It could be a typo in the line of code (line #28) that displays the "you win!" message."*

```
Your answer here...
```


### 2. Log your questions: what do you need to find out?

Write down a list of questions that you have related to your specific hypothesis above.

**Example:** *"What is this textContent thing? Is the C supposed to be capitalized? Is it missing a letter?"*

```
Your list of questions here....
```


### 3. Research and review: what answers can you find?

Next, do a little research on your questions, and write down a list of ***what** you found* and ***how** you found it* -- for example, what was the phrase you searched for on Google or StackOverflow? Did you ask on Slack or ask a friend? What did you discover?

**Example:** *"I searched for "textContent" on Google and found out from a page on MDN that it's a "property" that contains the text of an HTML element. That confirmed for me that it is indeed spelled that way.*

```
Your list of findings here...
```


### 4. Run your experiment: what are the exact steps you'll take to test your prediction?

For most hypotheses, research won't be enough; you'll need to test out some changes to the code! A real experiment!

If applicable to your hypothesis, write a **list of steps** for how you checked if your hypothesis is correct. These steps should be specific enough that somebody else can *replicate* them, like following a recipe.

**Example** (for a different example hypotheses): *"Because I thought maybe my JavaScript file wasn't loading, I added console.log("test") on line #1. Then I refreshed the page for the app and opened the browser console to see if it appeared."*

```
Your list of steps to run your experiment...
```

### 5. Report your results: what happened?

What was the result of your experiment? Did it solve the bug or not? Did it create a *new* bug? Were there any error messages in the browser console? Did the app behave incorrectly (not as expected)? Write down your findings.

**Example:** *"I saw "test" appear in the browser console."*

```
Your results here...
```

### 6. Conclusion: what did you learn?

Did this experiment *confirm* your hypothesis? Or would you say this result is inconclusive and you still don't know if your hypothesis is correct? Did this experiment bring up any followup questions or ideas for new hypotheses?

**Example:** *"This experiment confirmed that my JavaScript file is loading, without a doubt! My next hypothesis that I'd like to test later on is this: maybe I forgot to initialize the guessesRemaining variable."*

```
Your conclusion here...
```


#### 7. Iterate: Repeat the steps above!

This will be a familiar mantra when designing *anything*, software apps included: Iterate, iterate, iterate! Think of another hypothesis and/or another way to research or test it, and see what happens. (You don't need to do this whole process for *every tiny thing* you try, but do it at least a couple times, especially for anything that surprised you or led to you learning something new.)

:checkered_flag: ***Woohoo, you've reached the finish line for part 1 of this week's homework!*** Remember to write all your debugging experiment reports in a Google doc and share it with me.

:point_right: ***Stay tuned for part 2!** I will be adding more homework and materials by the weekend.*
