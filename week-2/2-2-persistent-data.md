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

## Bonus challenge 1:

Look up how to use the Chrome browser to view all the local storage data associated with a website, and try it out! Take a look at the data associated with [this version of our app (using the Web Storage API)](https://dragon-defeater-v1-localstorage.glitch.me/).

  > **Hint:** So far we've used the "Console" and "Elements" tabs inside Chrome DevTools. For this, we need to use a *new* tab that's available within those developer tool panels!

<br/>

## Bonus challenge 2:

Armed with this new tool, take a look at the local storage data that ***other websites*** are saving onto your hard drive!

Google, Facebook, Amazon, LinkedIn, Twitter, eBay, GitHub ... just about *every website* saves information onto your computer through a variety of tools, with the Web Storage API being just one of them.

<br/>

## Bonus challenge 3:

Once you've found the right section in Chrome's developer tools, try poking around the interface and find out how to reset all the local data?

To test if it worked, you'll need to refresh [the page for our app](https://dragon-defeater-v1-localstorage.glitch.me/). Then it should start the game all over again, with "0 dragons defeated" and empty fields for name and email.

<br/>

## Bonus challenge 4:

How would you use JavaScript code to reset / erase / clear out all the data? You'll need to look it up online!

  > **Hint:** You just need *one* line of code, and you can test it directly inside your browser's console -- again, just be sure to refresh the page afterwards to test if it worked!

<br/>

## Bonus challenge 5:

What data types can you store on a user's computer with the Web Storage API? Look it up online!

  > And feel free to remix [this version of our app (using the Web Storage API)](https://dragon-defeater-v1-localstorage.glitch.me/) and tinker with the code too!

<br/>

## Bonus challenge 6:

How would you store ***an entire object*** using the Web Storage API? 

  > This relates directly to the topic we'll talk about [in the next section](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-3-json-intro.md)!

<br/>

<hr/>

:point_right: **Next up:** in [section 2.3, we'll take our first look at JSON data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-2/2-3-json-intro.md), which takes us one step closer to our goal of adding persistent data to our web apps!
