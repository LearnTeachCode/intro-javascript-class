# 2.4: Debugging our Hangman game

:trophy: **The challenge:** Following the provided set of prompts, try to figure out what's wrong with our game and how to fix it, documenting each step as you go.

It's OK if you don't actually solve it; the point here is just to come up with some ideas, practice debugging with a strategic and scientific approach, and share your process with the rest of our class.

<br/>:beetle: **The bug:** Our super minimal Hangman game ([see the app here](https://hangman-v0-broken.glitch.me/)) is basically finished, but there's one problem: **if the user enters the correct answer, the game still says "you lose!"** What went wrong?

<br/>:clock2: **Time to complete:** Try not to spend more than 15 minutes on ***each iteration*** your debugging process. (But try to do the whole process more than once to test a couple different hypotheses.)

  > **Note:** If you've *already* solved this bug, then please use the prompts to document *different* ways to discover, confirm, or fix the bug!

<hr/>

## Instructions:

Taking inspiration from [the scientific method as outlined in section 1.6.1 (debugging overview)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-6-debugging.md#161-background-reading-on-bugs-debugging-and-bug-reports), go through the following steps and write up a report on your debugging experiments, answering all the prompts below for *each* of your hypotheses.

  > **Note:** We've already finished step 1 and 2 of [the scientific method](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-6-debugging.md#161-background-reading-on-bugs-debugging-and-bug-reports) as a group: we've *observed* the specific bug (you can't win the game!), and our questions are: *why* is this bug happening, and *how* can we fix it? So now you'll complete the next steps.

<br/>

### 1. Make your own personal copy of our (broken) Hangman game:

You can work directly inside Glitch, locally on your computer, or use any other tools that you prefer (like [CodePen](https://codepen.io/) or others). See the instructions below for setting up your personal copy of the project, either using Glitch or VS Code:

**Using Glitch:**

  > 📺 [Video: Intro to Glitch](https://youtu.be/juqFTEoHN2Q) (6 min)

:star: **Remix our broken Hangman game on Glitch here: https://glitch.com/edit/#!/hangman-v0-broken**


<br/>**Using Visual Studio Code:**

  >📺 See [section 1.1.5 and 1.1.6 for videos reviewing Visual Studio Code](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-1/1-1-initial-tools-intro.md#115-intro-to-text-editors-visual-studio-code)

1. To quickly get all the starter code, download a .zip file of the project directly from GitHub here: https://github.com/LearnTeachCode/hangman-game/archive/master.zip

    > **Note:** If you're already comfortable using Git, feel free to clone the project from the GitHub repo: https://github.com/LearnTeachCode/hangman-game

2. Open the .zip file and you'll see a folder inside of it. Move that folder ***outside*** of the .zip file, and put it somewhere easy to find.

    > Personally, I like to keep all coding project folders inside one master folder, so they're all in one place. For example, on my computer I would put the hangman game folder into "C:\Users\Liz\Documents\Code-Projects".

3. To open the project, first open Visual Studio Code, and then go to File > Open Folder. Locate and click on your project folder, then click "Select Folder".

4. To open the files, double-click their names in VS Code's explorer view on the left. (Open that by going to View > Explorer, or click the Explorer icon at the top left.)

5. **To view and test the app in your web browser:** Using Finder on Mac or File Explorer on Windows, navigate to your project folder and then double-click the HTML file icon; it should open with your default web browser.

   > **Shortcut:** to quickly open your project folder from within VS Code, you can right-click any file name (or Ctrl + click on Mac) and then click "Reveal in Explorer" in the context menu.

💡 Remember to save your changes early and often with File > Save. Or even better, turn on the Autosave feature with File > Auto Save. Then you won't have to remember to click Save every time!

<br/>

### 3. Write and share your debugging report using GitHub:*

  1. Make a fork of the GitHub repo for this debugging template by clicking the **Fork** button on the top right of the page: https://github.com/LearnTeachCode/debugging-report-template
  
  2. Follow [GitHub's instructions to edit the `README` file](https://help.github.com/articles/create-a-repo/#commit-your-first-change) in that repo and fill out your answers following each prompt there.
  
  3. Follow [GitHub's instructions to share your debugging report by making a ***pull request***](https://help.github.com/articles/creating-a-pull-request-from-a-fork/).
  
  4. You can see a list of everyone's pull requests here: https://github.com/LearnTeachCode/debugging-report-template/pulls

<br/>
<hr/>

:trophy: ***Wonderful!*** If you continue practicing strategic debugging this way, pretty soon you'll be better at debugging than many professional programmers! **Next up:** Repeat the process again (or a few times!) to test your other hypotheses for the bug in our Hangman game.

