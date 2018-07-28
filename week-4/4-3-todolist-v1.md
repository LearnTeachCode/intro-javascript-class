# Section 4.3: Group project: Simple to-do list version 1

Now that we have the core functionality of our front-end interface working (at least for this first prototype), let's add just a little bit more.

<hr/>

## What shall we build next?

:hammer: **New feature for version 1:** Pretend that our app stores the user's data in a database. Let's **display their previous to-do items** as soon as they open the web page!

<br/>

## Challenge 1:

Imagine that the last time the user visited our to-do list app, they added the following tasks to their list:

  1. Review arrays
  2. Learn about loops
  3. Finish building this to-do list app

<br/>

**Your challenge:** Using [Python Tutor](http://pythontutor.com/javascript.html#mode=edit), initialize the computer's memory so that the data listed above will be available as soon as the web page loads. 

<br/>

## Challenge 2:

The newer version of JavaScript has a very useful way to repeat an action once for every element in an array: the [`for...of` loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)!

**First, make a prediction:** what do you think the code below will do?

```javascript
let favoriteMovies = ["Forrest Gump", "Blade Runner", "Titanic", "Toy Story"];

for (let movie of favoriteMovies) {
  console.log(movie);
}
```
<br/>

Next, run the code in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit) to see if your prediction was right!

<br/>

## Challenge 3:

Make a prediction about the code below -- compared to the example given in challenge #2 above, will this code still work? Why or why not?

```javascript
let favoriteMovies = ["Forrest Gump", "Blade Runner", "Titanic", "Toy Story"];

for (let appleSauce of favoriteMovies) {
  console.log(appleSauce);
}
```

<br/>

Run the code to see if you're prediction was correct. Did it do what you expected? Why do you think it worked that way?

<br/>

## Challenge 4:

There's something wrong with the code below. See if you can identify it first, ***before*** you run the code.

```javascript
let moreGoodMovies = ["Inception", "Jaws", "One Flew Over the Cuckoo's Nest"];

for (m of moreGoodMovies) {
  console.log(m);
}
```

<br/>

## Challenge 5:

Here's another bug to fix! Again, see if you can identify the bug ***before*** you run the code:

```javascript
let evenMoreMovies = ["Rocky", "2001: A Space Odyssey", "Die Hard"];

for (let eachMovie of evenMoreMovies) {
  console.log(eachmovie);
}
```

<br/>

## Challenge 6:

Now that you're starting to get the hang of it, write your own `for...each` loop using the data listed in challenge #1 at the top of this page. Display each task in the console!

<br/>

## Let's build version 1 of our to-do list app!

:hammer: **Recap of our new feature:** Pretend that our app stores the user's data in a database. Let's **display their previous to-do items** as soon as they open the web page!

<br/>

:star: [**Click here to open our shared Glitch project**](https://glitch.com/edit/#!/join/0ea3b592-0e27-44ef-be20-eb5f1fae2df0)

<br/>

Our next steps:

  1. Add the sample data from challenge #1 into our app.

  2. Add our `for...of` loop code.

  3. Instead of simply displaying each task in the console, let's reuse some of our previous code to add every task as an element on the web page! We want to see all the tasks appear on the web page as soon as it loads.

<br/>

**Bonus:** Our code is getting a bit repetitive now! How could we *refactor* it -- in other words, clean it up? You could create a separate function that contains the repetitive lines of code. 

<br/>
<hr/>


🏆 ***Yay, we did it!*** This is how real projects are built: one tiny step at a time, learning what we need *just in time* for when we need it. Combining that with general learning (from books, tutorials, etc) is the key to mastering these new skills!

:point_right: ***Next up:*** [in section 4.4, we'll experiment with drawing and animating some random shapes using the p5js library!](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-4/4-4-drawing-p5js.md)
