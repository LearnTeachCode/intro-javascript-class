# Section 1.6: Intro to data types

So far, we've learned how to display data on the web page and in the browser's console.

Let's take a closer look at two of the main *types* of data that we can work with, and then we'll figure out how to combine our data in more complex ways!

<hr/>

## Review and group discussion:

Let's take a closer look at what we've learned so far, and discuss:

  1. What ***type*** of information have we been using so far? Looking at the data from our previous examples, what did they all have in common?
  
  2. What are some other types of data?
  
  3. How would you define the concept of a ***data type*** in one sentence, in plain-and-simple English with ***no*** technical terms?

<br/>

## Challenge 1:

⭐️ Once again, **make sure you have your personal copy of our HTML mockup on Glitch open in a tab**, or if you lost track of the link, feel free to [**click here and make another remix of it**](https://glitch.com/edit/#!/dragon-defeater-v0-starter).

<br/>

Take a look at the data we're using with the `console.log()` function below. For each example, ***write down your predictions:***

  1. Will it work?
  2. If not, what error will the console display?
  3. Why?

<br/>

```
// Example 1:
console.log('Hello');
```

```
// Example 2:
console.log("1234567");
```

```
// Example 3:
console.log("&:#-{@%?*&.=#,@!^[#{};;*&^[]$%~");
```

```
// Example 4:
console.log("console.log();");
```

```
// Example 5:
console.log('I found a 🐞 in my code! 😝');
```

```
// Example 6:
console.log("");
```

```
// Example 7:
console.log("  ");
```

```
// Example 8:
console.log('  ');
```

```
// Example 9:
console.log("Hi there');
```

```
// Example 10:
console.log("My console said "Error!" so I kicked it.");
```

```
// Example 11:
console.log('My console said "Error!" so I kicked it.');
```

```
// BONUS CHALLENGE: Example 12:
console.log('My friend's console said "Error!" so he punched it.');
```

<br/>

After writing down your predictions, run each line of code ***one at a time*** to check if your predictions were correct. If there are errors, then discuss: how would you fix them?

<br/>

## Strings of characters:

In our previous challenges, we used some data like this:

```javascript
console.log("Some words here.");
console.log("This can say anything we want!");
```

<br/>

In computer science jargon, we use the word ***string*** to refer to any data that should be treated as a word, a label, or literally a bunch of letters and symbols *strung* together like [those alphabet beads that you can *string* together into a necklace](https://www.etsy.com/market/alphabet_beads):

![alphabet beads string](https://user-images.githubusercontent.com/1555022/42394580-747056ae-810f-11e8-8c25-9921dbebb5fc.jpg)

<br/>

:star: So, remember: **a *string* is a data type used for a sequence of characters.**

<br/>

### Rules for using strings:

**1) They must always be surrounded by *matching quote marks***. Either single (`'`) or double (`"`) quotes will work, as long as they match. <br/><br/>We call these ***delimiters***, because they define the *limit* of where the string begins and ends.

<br/>

  > That's the difference between the actual function `console.log()` and the string of literal characters `"console.log()"`, which is `c`-`o`-`n`-`s`-`o`-`l`-`e`-`.`-`l`-`o`-`g`-`(`-`)`!<br/><br/>It's just like how the word `dog` is different from the letters `d`-`o`-`g`, which is an acronym for "Department Of Geography", "Delusions of Grandeur", "Dutch Oven Gathering", or [any of the other DOG acronyms on this funny list](https://acronyms.thefreedictionary.com/DOG)!
 
 <br/>
 
**2) Strings can contain *any character***: letters, numbers, punction marks, and yes, even emojis! 😆
 
 <br/>
 
**3) If you need to use a literal quote mark as a character *inside* a string, you can do this two ways:**

  1. Use the *other* type of quote mark to surround the string, as in `"I'm using an apostrophe!"` or `'Using a "quote" here'`.
  
  2. Or you can tell the computer to treat a quote mark as a literal symbol (*not* as a string delimiter) by putting a backslash `/` in front of it, as in `'Here/'s an apostrophe'` or `"I say /"bah humbug/" to you!"`.

<br/>

  > **Bonus homework:** If you're curious about other special cases, search online for "escape characters" or "escape sequences" -- this is a general term in computing and it's an issue with *all* programming languages.


<br/>

## Challenge 2:

After our very thorough exploration of strings, take a look at some numbers! Once again, ***write down your predictions for each one:***

  1. Will it work? If so, what do you expect to see appear in the console?
  2. If not, what error will the console display?
  3. Why?


```
// Example 1:
console.log(1234567);
```

```
// Example 2:
console.log(-30);
```

```
// Example 3:
console.log(12.3333333333);
```

```
// Example 4:
console.log(12.3333333333333333333333);
```

```
// Example 5:
console.log(0);
```

```
// Example 6:
console.log(1/2);
```

```
// Example 7:
console.log(2/3);
```

```
// Example 8:
console.log(5 + 10);
```

```
// Example 9:
console.log(-5 + 10);
```

```
// Example 10:
console.log(-3 - 7);
```

```
// Example 11:
console.log(-3 + -7);
```

```
// Example 12:
console.log(4 * 4);
```

```
// Example 12:
console.log(2 * 2 * 2);
```

```
// Example 13:
console.log(5 + 2 * 3 + 1/2);
```

```
// Example 14:
console.log( (5 + 2) * 3 + 1/2);
```

```
// Example 15:
console.log( ((5 + 2) * 3 + 1) / 2 );
```

```
// Example 16:
console.log( (4 - 2) * 5) + 3 );
```

```
// Example 17:
console.log(1234567890123456789012);
```

```
// Example 18:
console.log(9.9999999999999999);
```

```
// Example 19:
console.log(9.999999999999999);
```

<br/>

After writing down your predictions, run each line of code ***one at a time*** to check if your predictions were correct. If there are errors, then discuss: how would you fix them?

</br>


<br/>

## Challenge 3:

We've experimented with lots of strings and lots of numbers, and we've seen that JavaScript supports the most common ***arithmetic operators***, as well as the usual order of operations taught in math class.

Now, let's live on the wild side -- we're going to ***combine*** strings with numbers and operators!

<br/>

Once again, ***write down your predictions for each one:***

  1. Will it work? If so, what do you expect to see appear in the console?
  2. If not, what error will the console display?
  3. Why?

```javascript
// Example 1:
console.log("4" + "5");
```

```javascript
// Example 2:
console.log(2 + "2");
```

```javascript
// Example 3:
console.log(2 - "2");
```

```javascript
// Example 4:
console.log("hello" + "world");
```

```javascript
// Example 5:
console.log(  "hello"    +   "world"  );
```

```javascript
// Example 6:
console.log(  "hello   "    +   "world"  );
```

```javascript
// Example 7:
console.log("hello " + "world");
```

```javascript
// Example 8:
console.log("hello" + " world");
```

```javascript
// Example 9:
console.log("hello" - "world");
```

```javascript
// Example 10:
console.log("oranges" + 7);
```

```javascript
// Example 11:
console.log("oranges" - 7);
```

```javascript
// Example 12:
console.log(1/2 + "5");
```

```javascript
// Example 13:
console.log("5" + 1/2);
```

```javascript
// Example 14:
console.log( ("hello" + "world") + "yay" );
```

```javascript
// Example 15:
console.log( ("1" + "2") / 2 );
```

```javascript
// Example 16:
console.log( "1" + ("2" / 2) );
```

<br/>

After writing down your predictions, run each line of code ***one at a time*** to check if your predictions were correct.

Then **discuss:**

  1. What's the difference between numbers and strings? Example: what's the difference between `2` and `"2"`?
  
  2. Which ***operators*** are we allowed to use with both strings *and* numbers? (Operators include addition, subtraction, etc.)
  
  3. Which operators ***don't*** work with strings?
  
  4. Why would we need to make a distinction between numbers and strings? Why is this useful, why is it important?
  
  5. How do you think these data types are stored inside the computer, at the lowest level?

<br/>

## The `+` sign: addition and concatenation!

So it turns out that in JavaScript, the plus sign (`+`) is used for two different things: adding numbers and combining strings!

<br/>

:star: Here's another fancy word that will make you sound like a computer scientist: ***concatenation***.

It means "chaining things together", just like making a necklace from those alphabet beads. So when we write `"hello" + " world!"` in our code, we're *concatenating* the two strings `"hello"` and `" world!"` to create one longer string!

In this context, the plus sign (`+`) is called the ***concatenation operator***. (When we use it to find the sum of two numbers, we just call it the *addition operator* like from math class.)

<br/>

## Applying our new knowldege:

Looking at the flowcharts we made for our Dragon Defeater game, let's discuss:

  1. Which data types will we need to use to create our game?
  
  2. What will we be using each data type for? What information will they each represent?
  
  3. Will we need to use any operators? If so, which ones?

<br/>
<hr/>

:trophy: ***Wonderful!*** Data types are at the very heart of computing, both in theory and in practice. As a programmer, you'll be making use of different types of data *every single day*!

:point_right: **[Next up: ....](#)**
