# Section 4.2: Group project: Simple to-do list version 0

......

<hr/>

## What are we building?

:hammer: **Feature requirements for version 0:**

  1. The web page will have a title, instructions, a text input box, a button, and an empty ordered list (`<ol>`) element.

  1. The user can add an item to the list by typing into the text box and clicking the "Add to list" button.

  1. After the user clicks the button, their new task should appear at the bottom of the page as a list element (`<li>` tag) inside the ordered list.

<br/>

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/0ea3b592-0e27-44ef-be20-eb5f1fae2df0) -- we'll write our notes and code as a group here!

## Challenge 1:

Let's start the planning process by writing some comments in our JavaScript file. You know the drill:

  1. Let's identify and write down the IDs of every HTML element that our code will need to interact with.
  
  1. For each of those elements, let's write a brief description of what we need to do with it or what we need to change about it.
  
  1. Let's write down the details about any event listeners that we'll need to set up: where the event happens, the name of the event, and a name to describe the function that will be triggered by the event.

<br/>

## Challenge 2:

Next, let's write some actual code to create our event listener! We can use the handy-dandy `console.log` function to check that it works.


<br/>

## Challenge 3:

Remember how to access the text that the user types into a text box? Let's access that value and save it to a new variable, so that way we won't have to do so much typing the next time we want to use that data.

Then let's `console.log` the data that we received from the user, to double-check that our code works so far.

<br/>

  > **Hint:** We need to use a property similar to `textContent`, which we learned about in our previous class when we built a super minimal Hangman game together.

<br/>

## Challenge 4:

Now, we need to add each new item onto the web page! How can we accomplish that? Time for a little Googling...

<br/>

**A couple search tips:**

  - Remember to include the word "JavaScript" in your search!

<br/>

  - Try a few different synonyms for the concept you want to learn about, and think in terms of what ***action*** you want to perform.

  > For example, if you want to figure out how to delete something from a web page, you might want to search for: "delete", "remove", "discard", "take out", "detach"... Chances are at least *one* of those words will help you find what you need!

<br/>

  - Remember some of the key vocabulary we learned for talking about things on a web page: "DOM element", "HTML element", or just "element" for short.

<br/>

  - One of the most thorough and most up-to-date reference websites is the [Mozilla Developer Network](), and you can just include **"MDN"** within your Google search query to find results from their website. 

  > Searching directly within the MDN website can sometimes be tricky, because they have *so much information* in there. So that's why sometimes it's better to search for your phrase plus "MDN" on Google instead.

<br/>

## Challenge 5

Let's put our heads together and combine what we've all found through our research! Here's a quick breakdown of what we need to do in order to display new tasks in the to-do list on our web app:

  1. Create a new `<li>` element for the new task

  1. Put the user's text inside that element. (This line of code will look exactly like what we've done many times since the first day of class!)

  1. Add the new element inside our ordered list element.

<br/>

And voila, we have a tiny to-do list!

<br/>
<hr/>


🏆 ***Great job, team!*** Creating version 0 of our to-do list was pretty easy, huh? But in order to build it, we still had to learn a couple of very useful new JavaScript tricks!

