# 2.2: Persistent data: example and discussion

At the end of our previous class ([see section 1.2 on reviewing objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-2-review-objects.md)), we discussed how we might model the data for our click-counting game if we made a multiplayer version. Let's take a quick look at two quick examples building up from where we left off, as we move closer to working with databases!

<hr/>

## Challenge 1:

Here's a working version of the game that also tracks the player's name and email address (well, sort of!): https://dragon-defeater-v1-finished.glitch.me/

**Take a look at the JavaScript code here:** https://glitch.com/edit/#!/dragon-defeater-v1-finished

Notice how instead of only tracking a single number -- the number of clicks -- we're now using an ***object*** to save information about the player along with their clicks. You could even say that the object is basically a miniature database!

**Discuss:**

  1. Why does it make sense to use an object here?
  2. Why not just use several variables that are all completely separate from each other?

<br/>

## Challenge 2:

[**Test out the game**](https://dragon-defeater-v1-finished.glitch.me/) and then **discuss:**
    
  1. What happens if you refresh the page, or if you close it and open it again?
  2. More importantly: *why* does this happen?

<br/>

## Storing data locally with the Web Storage API

When we save data into variables within our code, they're stored in the computer's **memory**. In the case of JavaScript running inside a web browser, that memory only lasts for as long as the web page is open! It's *temporary*, not *persistent*.

:star: **We use the term** ***persistent data*** **to describe information that can still be retrieved after shutting down the program that created it.**

One of the easiest (but most limited) tools for saving persistent data in a web app is the [**Web Storage API**](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API), which is built into most modern web browsers!

:warning: **Important warning:** ***The Web Storage API has many limitations and should not be used in place of a real database!*** So please only use it for prototypes, not for published applications meant to be used by real people -- at least until you understand its pros and cons!

<br/>

## Challenge 3:

**Compare these two versions of our example game:**

  1. The version from above (using only browser memory): https://dragon-defeater-v1-finished.glitch.me/
  2. This new version using the Web Storage API: https://dragon-defeater-v1-localstorage.glitch.me/

Try refreshing the web page for both versions. See the difference? *Pretty cool, isn't it?*

**Discuss:**

  1. Will this new version of the game remember your information if you switch between your computer and your phone, or between different computers? Why or why not?
  2. What if you stay on the same computer but play the game in different web browsers? Will the game still keep track of your data? Why or why not?
  3. How can we make that information available across multiple computers and devices? What extra technologies might we need?

<br/>

<hr/>

:point_right: **Next up:** in [section 2.3, we'll take our first look at JSON data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-3-json-intro.md), which takes us one step closer to our goal of adding persistent data to our web apps!
