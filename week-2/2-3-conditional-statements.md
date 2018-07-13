# Section 2.3: Making decisions with conditional statements

***Conditional statements*** are the commands that allow us to tell a computer to ***make a decision*** based on the answer to [our yes-or-no questions (***comparisons***) that we learned about in the previous section](https://github.com/LearnTeachCode/js-intro-logic/blob/master/2-comparison-logic.md).

Let's do some decision-making!

<hr/>

## Challenge 1:

Before you run the code below, make a prediction about what you think will appear in the console! Then test the code:

```javascript
// Make a prediction before you run this code
if ( 3 > 2 ) {
    console.log("This condition is true!");
}
```

**Discuss:**

  1. How would you translate this code into a plain English sentence? What's it saying?
  
  2. What do you think the parentheses `()` mean here?
  
  3. And what do you think the curly brackets `{}` mean here? Why do we need them?
  
  4. Why is the code inside the `if` statement indented further over to the right? Does it *need* to be?

<br/>

## Challenge 2:

Again, make a prediction about what you'll see appear in the console, and then run the code afterwards:

```javascript
// Make a prediction before you run this code
if ( 5 < 4 ) {
    console.log("This condition is true!");
}
```

**Discuss:**

  1. What's different about this code compared to challenge #1 above?
  
  2. How would you translate this code into a plain English sentence?

<br/>

## Challenge 3:

Same for this code -- make a prediction first, and then run the code to see if you were right!

```javascript
// Make a prediction before you run this code
if ( 5 < 4 ) {
    console.log("This condition is true!");
}
console.log("You are AWESOME.");
```

**Discuss:**

  1. What would you see in the console if you replaced `5 < 4` with a *true* condition like `5 === 5`?

  2. What's different about this code compared to challenge #2 above?

<br/>

## The structure of an `if` statement

Translated to plain English, the code in challenge 3 above would read like this: ***Only if*** it's true that 103 is greater than 99, ***then*** display in the console: `"This condition is true!"`

 <br/>
 
:bulb: ***Notice that if the answer (the condition) is false, nothing happens!*** The computer *skips* everything inside the curly brackets if the condition is false, and then it runs any code *after* the curly brackets.

<br/>

**Quick overview of the parts of an `if` statement:**

  1. The keyword `if`
  2. A pair of ***parentheses***, which contain the ***comparison*** or ***condition*** (the question we're asking)
  3. A pair of ***curly brackets***, which contain ***the code to run*** only if the condition is true

<br/>

You can put as much code as you want inside those curly brackets! For example:

```javascript
if ( 103 > 99 ) {
    console.log("This condition is true!");
    console.log("Run some other code here");
    console.log("..and more code... as much as you want!");
}
```

<br/>

Building up from these examples, let's write some `if` statements of our own!

<br/>

## Challenge 4:

Translate the following sentences into code:

  1. First, show this sentence in the console: `"Our code is starting!"`

  2. Next, only if it's true that 55 is less than or equal to 60, then display this phrase in the console: `"Condition true!"`

  3. Finally, regardless of whether the previous condition was true or not, always display this phrase in the console: `"All done!"`


<br/>

## Challenge 5:

Translate the following sentences into code:

  1. If it's true that 6 is less than 7 and it's also true that 7 is less than 8, display this phrase in the console: `"Why is 6 afraid of 7?"`


<br/>

## Challenge 6:

Before you run the code below, make a prediction about what you think will appear in the console! Then run it:

```javascript
// Make a prediction before you run this code
if ( "bla" === "urg" ) {
  console.log("This condition is true");
} else {
  console.log("This condition is false");
}
```

**Discuss:**

  1. How would you translate this code into a plain English sentence?
  
  2. What do you think you'd see in the console if you changed the condition to `"bla" === "bla"`?


<br/>

## Challenge 7:

Translate the following plain-English instructions into code:

  1. If it's true that 7 is less than 9, display in the console: `"Because 7 8 9! Get it? 7 ATE 9!"`
  
  2. Otherwise (if that condition is *not* true), display: `"I don't get the joke."`


<br/>

## Challenge 8:

As always, before you run the code below, predict what you think will appear in the console! Then try it out:

```javascript
// Make a prediction before you run this code
if ( "bla" === "urg" ) {
  console.log("This condition is true");
} else if ("um" === "um") {
  console.log("This second condition is true");
}
```

**Discuss:**

  1. How would you translate this code into a plain English sentence?
  
  2. What do you think you'd see in the console if you changed `"um" === "um"` to a *false* condition like `"um === "oh"`?

<br/>

## Challenge 9:

Write the code to implement the instructions outlined in this flowchart:

![js-workshop-june13-challenge9](https://user-images.githubusercontent.com/1555022/41383956-26a8091a-6f28-11e8-8fa3-c872c269fe31.png)
  
<br/>

## Challenge 10:

Compare this next flowchart to the one in challenge #9 above -- they're *very* similar, but not quite. What's the only difference? Discuss this first, and then write the code to implement it:

![flowchart challenge 10](https://user-images.githubusercontent.com/1555022/41383961-2c591ec6-6f28-11e8-9f5e-0461bbad51fe.png)

<br/>

## Challenge 11:

Time to combine *all* of our powers! ***You can chain together as many `if`, `else if`, and `else` statements as you want!*** 

Take a look at the flowchart below -- notice it has *one more step* than all of our previous examples. Take a shot at writing the code for this one:

![flowchart challenge 11](https://user-images.githubusercontent.com/1555022/41383950-215b84d2-6f28-11e8-85e2-6152d31a9c2a.png)

<br/>

## Challenge 12:

This program is *very similar* to the one in challenge #11 above, but there's one important difference. Discuss your ideas, compare the two diagrams, and then write the code to implement this new version:

![flowchart challenge 12](https://user-images.githubusercontent.com/1555022/41383953-249140e2-6f28-11e8-903b-7f29a8ab2b7d.png)

<br/>
<hr/>

:trophy: ***Super 1337 coding skills!*** **[Next up: let's starting working with functions!](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-2/2-4-function-challenges.md)**
