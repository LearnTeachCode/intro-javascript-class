## 3.3: Practice challenges: Intro to arrays

An array is an *ordered list* of things. Just like other objects, they can contain any type of data: numbers, strings, Booleans, objects, other arrays, etc. But as we discussed earlier, arrays and objects have different pros and cons.

:tv: **Video: Intro to arrays (6 min): https://youtu.be/QlfR6ICa3gQ**

  > **Note:** This is also an older video, which is why you'll see `var` instead of `let`. Planning to remake this one later too.

<br/>

In these next challenges, let's start creating and working with our own arrays!

<hr/>


## Challenge 1:

First, a Google challenge! Look up how to create an array in JavaScript. (There's always more than one way to do something, but use whichever example looks the most simple and straightforward.)

As always, for any code snippets you find online, test them out to make sure that you understand how they work!

<br/>

## Challenge 2:

First, create an array containing a list of some of your favorite movies of all time.

Then find at least three ways to *break* your code! See how many error messages you can get to show up in the console. ;)


<br/>

## Challenge 3:

Can you store values of different data types all within the same array? Try it out in your browser console to find out!

<br/>


## Array elements and indexes:

The things inside an array are called ***elements***, and they each have a number assigned to them, called the ***index***.

Computers start counting at zero, not at one! (This goes *way* back to the early days of computing.

  > **Fun tangent:** [See this forum discussion for some interesting reasons why!](https://superuser.com/questions/578292/why-do-computers-count-from-zero)
  
Long story short, we'll have to remember that the **first** element in an array is located at **index 0**:

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/b/bf/CPT-programming-array.svg" width=240/></p>

<br/>

You'll get used to it with practice, but this is one of the reasons that [off-by-one errors are one of the most common bugs](https://twitter.com/codinghorror/status/506010907021828096) you'll ever see!


<br/>

## Challenge 4:

Using one of the arrays you just created, write a line of code to tell the console to display the value of the *second* element in your array.

<br/>

## Challenge 5:

Next, see what happens if you try to display the value of the array at **index 57**, which I'm sure doesn't exist in your array, unless you *really* enjoy typing! Will it cause an error? Why do you think it did or did not?

<br/>

## Challenge 6:

Given the code below, create an array that contains a list of all of these bad puns -- ***without*** rewriting the puns themselves! Make use of variables, they're there to save you from too much typing! (Good programmers are lazy programmers, right?)

```javascript
let pun = "Looks like I lost an electron, I should keep a better ion them.";
let punny = "Where does a general keep his armies? In his sleevies!";
let puntastic = "I don't trust stairs. They're always up to something.";
let punneriffic = "What did the grape say when it got crushed? Nothing, it just let out a little wine.";
let justPunMore = "My sister bet that I couldn’t build a car out of spaghetti. You should've seen her face when I drove pasta.";
```

<br/>

## Challenge 7:

Anywhere you can put a literal value (like `3` or `"hi"`), you can replace it with the name of a variable that contains that value! This will be *super important* when you're working with arrays in more advanced ways later on.

**Your challenge:** Create a variable named `myIndex` that contains a number. Then access an element from your array of bad puns using `myIndex` *instead* of directly using a number.

<br/>

## Challenge 7:

To find out how many elements are inside an array, just type the name of the array followed by `.length`! Test this out by telling the console to display the length of your array of of puns.

  > **Note:** You may have noticed the *dot syntax* here works the same way as with our objects! That's because arrays are also objects -- just a special type of object with its own special syntax! Under the hood, arrays have lots of built-in variables (like the `length` property) as well as built-in functions, as we'll see next!

<br/>

## Challenge 8:

Time for another Google challenge! How do you add a new item onto the end of an array? Find some sample code, test it out, and then test it with one of your own arrays!

Remember to use the console to check if it worked! You can display arrays using `console.log()` just like you can with any other data type.

<br/>

## Challenge 9:

Followup Google challenge: how to you *remove* an item from the end of the array? Look it up and try it out! Be sure to test it in the console to make sure that it worked.

  > **Hint:** This built-in function has a silly name. :)

<br/>

## Challenge 10:

In the practice challenges introducing objects, we create a *nested* object: an object inside another object! Let's continue with this *Inception* theme and create an ***array inside an array***!

  > **Hint:** Make use of variables here too if it helps make your code easier to read. You can always break things up into smaller steps; *you're* the programmer so you can do things any way you like!
  
Once you've created your nested data structure, how would you access an element from the *inner* array? Try it out!

  > **Hint:** You can make it easier for yourself by breaking things up into variables here too. Or you can write it a shorter way -- think *Inception*!

<br/>

## Bonus challenge 1:

Pretend you have an array that contains a list of all the users in your social network site. At any point in time, new users can sign up and be automatically added to the end of that array. So the length of this array is constantly changing!

**Your challenge:** How would you access the most recent user who signed up for your social network site?

<br/>

## Bonus challenge 2:

Create an example of an ***object inside an array*** and then practice accessing that object from *inside* the array!

Then do the reverse: create an ***array inside an object*** and then access the array from *inside* the object.

<br/>

## Bonus challenge 3:

Watch [this famous talk named "Wat", presented by Gary Bernhardt](https://www.destroyallsoftware.com/talks/wat). It's a very famous 5-minute talk that takes a hilarious look at the quirks of two popular programming languages: Ruby and JavaScript.

The JavaScript part is at the end. Bonus points if you try running some of his code examples in your browser console!

<br/>

<hr/>

🏆 ***Wonderful!*** You can now work with lists of data like a pro!
