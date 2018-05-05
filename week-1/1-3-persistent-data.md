# 1.3: Persistent data: example and discussion

After discussing how to model the data for our click-counting game to work towards turning it into a multiplayer game, we might end up with something like this: https://dragon-defeater-v1-finished.glitch.me/

In that working version of the game, we're now saving more information that could potentially identify each unique user: their name and their email address! This game is *far* from finished, of course, but it's a start.

<hr/>

## Challenge 1:

Take a look at [the JavaScript code for this version of the game](https://glitch.com/edit/#!/dragon-defeater-v1-finished).

Notice how instead of only tracking a single number -- the number of clicks -- we're now using an ***object*** to save information about the player along with their clicks. You could even say that the object is sort of like a miniature database!

**Discuss:**

  - Why does it make sense to use an object here?
  - Why not just use several variables that are all completely separate from each other?

<br/>

## Challenge 2:

Test out [this working version of our click-counting game](https://dragon-defeater-v1-finished.glitch.me/) and discuss:
    
  - What happens if you refresh the page, or if you close and open it again?
  - Why?

<br/>

## Bonus example: storing data locally with the Web Storage API

When we save data into variables within our code, they're stored in the computer's **memory**. In the case of JavaScript running inside a web browser, that memory only lasts for as long as the web page is open! It's *temporary*, not *persistent*.

We use the term ***persistent data*** for information that can still be retrieved *after* shutting down the program that created the data.

One of the easiest (but most limited) tools for saving persistent data in a web app is the [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API), which is built into most modern web browsers!

**Compare these two versions of our example game:**

  - [The version using only browser memory](https://dragon-defeater-v1-finished.glitch.me/)
  - [This new version using the Web Storage API](https://dragon-defeater-v1-localstorage.glitch.me/)

Try refreshing the web page for both versions -- see the difference? Pretty cool, isn't it?

<br/>

## Challenge 3:

**Discuss:**

  - Will this new version of the game remember your information if you switch computers?
  - Why or why not?

<br>
:warning: **Important warning:** This is for demonstration purposes only!

***The Web Storage API is very limited and should not be used in place of a real database!*** So please only use it for prototypes, at least until you understand its pros and cons.

<br/>

<hr/>

:trophy: **Great work!**

:point_right: **Next up:** ...
