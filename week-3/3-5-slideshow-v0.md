# Section 3.5: Group project: Simple slideshow version 0

Let's put our new knowledge to use! With arrays, we can now build the core functionality of our image slideshow app. So let's build the first version of our app!

(When we're done, we'll learn more about objects and then use them to build a slightly improved slideshow app.) 

<hr/>

## Recap: what are we building, again?

:hammer: **Feature requirements:**

  1. The app will have a bunch of image URLs saved in memory.
 
  1. The web page will have a title, instructions, an image, and two buttons: "next" and "previous".

  1. When the user clicks "next", show the next image.

  1. When the user clicks "previous", show the previous image.

  1. The images should appear in the same order every time (not randomized).

  1. Once the user reaches the end of the slideshow, it should wrap around and start over again from the beginning. 

<br/>

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/8ec55652-0822-4cf3-acef-b601d1a3585d) that we can all edit together in real time!

<br/>

## Challenge 1:

Sometimes the best way to figure out how to start building a project is to simulate it with the oldest technology: drawing on paper! (Or a whiteboard!)

**Let's draw our way through the following scenarios:**

  1. The user opens the web page. They haven't clicked anything yet. What happens on the web page, and what happens in the computer's memory?

  1. The user clicks the "next" button one time. What happens?

  1. The user opens the page, clicks "next" 4 times, then clicks "prev" two times. Now where are we?

<br/>

## Challenge 2:

Next, let's write some comments in our JavaScript file to help us bridge the gap between our ideas and the actual code:

  1. Let's write down the ***name*** and the ***data type*** for any variables that we'll definitely need. (We can always add more later if needed!)

  1. Next, let's write do the ID names of every HTML element that our code will need to interact with.
  
  1. For each of those elements, let's write a brief description of what we need to do with it or what we need to change about it.
  
  1. Let's write down the details about any event listeners that we'll need to set up: where the event happens, the name of the event, and a name to describe the function that will be triggered by the event.

<br/>

## Challenge 3:

Let's do a little research -- Google challenge! How can we change the URL of an `<img>` element using our JavaScript code? 

Take a look and see what you find. After testing it out to make sure it works, we'll update our notes accordingly.

<br/>

## Challenge 4:

Now that we have our ducks in a row, let's write our first lines of code!

When the page loads, we'll need to do the following:

  1. Initialize the memory with the *initial state* of our app. Note: it's usually best to define our variables *at the top* whenever possible.

  2. Let's change the image element so that as soon as the page loads, it will display the ***first*** image from our array. 

  3. Next, let's set up our event listeners!

<br/>

  > **Remember:** The code that sets up an event listener runs ***once*** as soon as the page loads. But once it's set up, then any time the event happens in the future, it will run our custom function *over and over again.*

<br/>

## Challenge 5:

We're done with everything that needs to happen immediately when the web page loads. Next, let's write the code that ***waits*** until the user clicks one of the buttons.

  > Remember to use `console.log()` to test things easily! We can use it to check the values of our variables, and to see the order in which our code is running.


<br/>

## Bonus challenge 1:

Remember that last feature on the list? We wanted the slideshow to wrap around to the beginning if the user clicks all the way to the end.

How would we solve that?

  > If we don't have time to talk about it now, we'll return to this problem later on.

<br/>

## Bonus challenge 2:

See how repetitive our code is with responding to these two buttons? We can *refactor* this code -- in other words, clean it up so it's simpler and better organized!

  1. Identify which parts of our functions are *the same* across both of them.

  2. And then identify which parts are *different*.

  3. What's one way we could *identify* which of the two buttons the user clicked on?

  > **Hint:** We've been using this piece of data since our first day of class -- we've just been using it in a *different way*. But you can access it the same we we've been accessing `textContent` to check what its value is!


<br/>
<hr/>

🏆 ***Way to go, team!*** We've just opened the door towards *so many* more interesting and complex projects, now that we can start grouping our data in different ways! 

:point_right: **Next up:** [in section 3.6, we'll practice using JavaScript objects so that we can then make this app better!](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-3/3-6-objects.md)

