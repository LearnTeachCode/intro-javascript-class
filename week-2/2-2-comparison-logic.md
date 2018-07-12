# Section 2.2: Asking questions with comparison and logical operators

At their core, software programs are just a bunch of switches that turn on and off -- ***true*** or ***false***, 1 or 0.

Have you ever played the game "20 questions"? The goal is to guess what someone's thinking of, by asking no more than 20 questions -- *but you can only ask *yes or no* questions.* That's how our code works, too!

<br/>

:star: ***Computers can only ask yes or no questions.*** This is the basic building block of *all* computer programs, no matter how complex.

<br/>

Remember the **"less than"**, **"greater than"**, or **"equal to"** symbols from math class? (We call those the ***comparison operators***.) That's how computers ask questions: by *comparing* one value to another! 

<br/>

So let's start by asking and answering some questions with code!

<hr/>

## Challenge 1:

***Before*** you run any of the code below, take a look at it and discuss whether each line of code will show `true` or `false` in the browser console. After discussing your predictions, then run the code directly in your console to see if you guessed correctly!

```javascript
// For each of the below, guess if the console will show true or false!
console.log(2 === 2);

console.log(5 > 0);

console.log("pizza" !== "salad");

console.log(-17 >= 4);

console.log(9 < 8);
```

<br/>

:star: Just like we can put strings or numbers directly into the `console.log()` function, we can also put ***comparisons*** -- *our questions* -- right in there too!

  > The computer answers your question, ***evaluating*** the comparison and replacing it with either `true` or `false`.

<br/>

## Meet the Booleans

So far we've tinkered with two types of data: ***strings*** (like `"hello"`) and ***numbers*** (like `42`). There's another data type that's equally important -- in fact, it's the foundation of *all of computer science!*

<br/>

:star: ***Booleans*** are another data type that can only have a value of either `true` or `false`.

<br/>

  > **Fun fact:** Booleans are named after "Boolean algebra" (an area of mathematics where variables can only be `true` or `false`), which was named after this awesome guy [George Boole](https://en.wikipedia.org/wiki/George_Boole). Way back in the 1800s, he came up with some of the theories in math and logic that laid the foundation for the information age!


<br/>

## Challenge 2:

There's something wrong with the code below. Run it in the console to see what happens, and then fix the bug!

```
// After running this code, the console should show: true
// ...but it's broken! Can you fix it up?

console.log(2 => 1);
```

<br/>


## Challenge 3:

Here's another little bug to solve. Here we want the computer to answer our question, and it should display `true` in the console. What went wrong, and why?

```
// The console should display: true

console.log("yay === yay");
```

<br/>

## Challenge 4:

We can ask more complex yes/no questions by ***combining multiple comparisons*** together!

***Discuss these questions for each line of code below:***

  1. Do you think the computer will answer `true` or `false`?
  2. Why or why not?
  3. How would you say this question in plain English? (Translate the code!)

```javascript
// Make a prediction and discuss it BEFORE you run this code
console.log( 5 > 0 && 5 < 10 );

console.log( "lol" === "lol" && "omg" === "brb" );

console.log( 3 < 2 || 1 === 1 );

console.log( 10 === 25 || 10 >= 25 );

console.log( true || false );

console.log( true && false );
```

After discussing it, then go ahead and run the code in your browser console to see what happens!

<br/>

## Challenge 5:

You may have noticed in our first challenge that `!==` is the comparison operator for `NOT equal to`. The code below is similar, but not quite the same...

***Discuss these questions for each line of code below:***

  1. Do you think the computer will answer `true` or `false`?
  2. Why or why not?
  3. How would you say this question in plain English? (Translate the code!)

```javascript
// As always, make a prediction and discuss it before you run this code:

console.log(!true);

console.log(!false);

console.log( !false || !true );

console.log(!!true);

console.log(!!!true);
```

<br/>

## Logical operators

Remember the song ["Conjunction Junction, what's your function?" from Schoolhouse Rock](https://www.youtube.com/watch?v=RPoBE-E8VOc)? (If not, click the link and watch that video. It's awesome.) In human languages, we combine words and phrases using *conjunctions* like ***"and"*** and ***"or"*** . Programming languages do the same thing!

<br/>

:star: ***Logical operators* let us combine multiple comparisons to ask more complex questions.**

<br/>

Here's *very* brief summary of how these operators work:

  - ***AND*** ( `&&`) - Answer `true` only if the answer to ***both*** questions is `true`
  - ***OR*** ( `||`) - Answer `true` if the answer to ***either*** question is `true`
  - ***NOT*** ( `!`) - Whatever the answer is here, switch it to the ***opposite*** answer.

<br/>

This is how we can write software programs that can make decisions based on answering questions like the following:

  - Did you type in the correct username ***and also*** the correct password for your account?
  - Does this company have a store in the US ***or*** in Japan ***or*** in Brazil?
  - Did the user push the power button? (If so, switch the state to its opposite: either from ***on*** to ***off***, or from ***off*** to ***on***.

<br/>

## Bonus challenge 1:

First ***make a prediction*** for the following questions, and then create your own code examples and run them to see for yourself!

  1. What happens if you compare a string to a number?
  2. Or a string to a Boolean?
  3. Or a number to a Boolean?

<br/>

## Bonus challenge 2:

You can use the `!` operator (the "NOT" or "negation" operator) on a single value like we saw earlier -- for example, `!true` means "NOT true", which is the same as `false`.

But you can also ***negate an entire expression!*** These can be tricky; it helps to solve these *from the inside first*, replacing each inner part with `true` or `false`, and then working your way out until all you have left is `!true` or `!false`.

<br/>

***Discuss these questions for each line of code below:***

  1. Do you think the computer will answer `true` or `false`?
  2. Why or why not?
  3. How would you say this question in plain English? (Translate the code!)

```javascript
console.log(  !(true && true)  );

console.log(  !( 1 === 1  ||  2 === 2 )  );

console.log(  !( 3 < 1  &&  3 > 5 )  );

console.log(  !( !true && !true)  );
```

<br/>

## Bonus challenge 3:

Here's a Google scavenger hunt challenge: do some research and experimentation to find out what the difference is between JavaScript's ***strict*** type of comparison versus the ***lazy*** type of comparison.

Be sure to test it out for yourself -- do some experiments! And take notes on what you discover.

<br/>
<hr/>

:trophy: ***Great job!*** **[Next up: making decisions with conditional statements!](#)**
