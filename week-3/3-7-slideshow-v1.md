# Section 3.7: Simple slideshow version 1

Now that we've learned the basics of working with objects, let's put them to use in a new feature for our simple slideshow app!

As with every project, we can only build it *one step at a time*. And as you'll see, combining two data structures together definitely takes some practice!

<hr/>

## The new-and-improved slideshow:

<br/>

:hammer: **Here's our *one* new feature:** Each image will now have a *caption*, not just its URL!

<br/>

Before we build the new feature as a group, here are a couple quick practice problems -- because you can never get too much practice!

<br/>

## Challenge 1:

Since now *each image* has *two* pieces of information instead of just one, it makes sense for each image to be an *object.* So, we have a *list of objects* -- an *array of objects!*

**Here's the structure of our data:**

```javascript
let imageDataList = [
  {
    url: "url here",
    caption: "caption here"
  },
  {
    url: "2nd url",
    caption: "2nd caption"
  }
];
```

<br/>

But let's work through this structure one step at a time.

**Review challenge:** How would you access the ***first*** element in the array below? Log it to the console!

```javascript
let testArray = [
  "string one",
  "string two"
];
```

<br/>

## Challenge 2:

Great! Here's another quick review challenge: how would you create a *new* variable named `myNewVar` and assign it the value of the first element of the array?

<br/>

## Challenge 3:

OK, now how would you access the `color` property of `weirdAlien` as it's defined below? Log it to the console to check if it works!

```javascript
let weirdAlien = {
  color: "purple",
  eyes: 12 
};
```

<br/>

## Challenge 4:

Time to put the pieces together! How would access the `color` property of the ***first*** element in the array below? Log it to the console!

```javascript
let allTheAliens = [
  {
    color: "purple",
    eyes: 12 
  },
  {
    color: "green",
    eyes: 7
  }
];
```

<br/>

You can always create a separate variable like you did in challenge #3 above, to break this up into separate steps: access the element of the array, save it to a variable, and then treat that new variable as your object.

<br/>

## Now let's build our app:

<br/>

:star: [**Open our shared project on Glitch again**](https://glitch.com/edit/#!/join/8ec55652-0822-4cf3-acef-b601d1a3585d) and let's write the code!

<br/>

A recap of the steps we'll need to accomplish here:

  1. Now that we have an *array of objects* instead of an *array of strings*, we need to modify *every place* in our code where we access the image URL.

  2. We also need to access the HTML element for the caption, and change its text to display the value of the current image's caption. 

  3. ... actually, that's all we need to do! Well, aside from coming up with funny captions for the rest of the images. :) 

<br/>

## Bonus challenge 1 from version 0:

If we didn't already solve it before, let's make sure that if the user gets to the end of the slideshow, it will wrap around to start over again at the beginning!

<br/>

  > **Hint:** There are a few ways to solve this! We could use conditional logic, or we could use a little bit of math.

<br/>

## Bonus challenge 2 from version 0:

See how repetitive our code is with responding to these two buttons? We can *refactor* this code -- in other words, clean it up so it's simpler and better organized!

  1. Identify which parts of our functions are *the same* across both of them.

  2. And then identify which parts are *different*.

  3. What's one way we could *identify* which of the two buttons the user clicked on?

  > **Hint:** We've been using this piece of data since our first day of class -- we've just been using it in a *different way*. But you can access it the same we we've been accessing `textContent` to check what its value is!


<br/>
<hr/>

🏆 ***Woohoo!*** We've made use of our first *nested data structure*! Any project you build in the future will most definitely need to use arrays and objects to keep your data organized, so you're well on your way towards data mastery!

:point_right: **Next up:** [in section 3.8, we'll take our first look at using a command line interface!](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-3/3-8-command-line-intro.md)

