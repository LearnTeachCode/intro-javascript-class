# 4.1: Functions review and parameterizing repetitive code

:weight_lifting_man: Let's start with a warm-up exercise! After a quick review of using functions with inputs and outputs, we'll also practice making our code DRY (Don't Repeat Yourself!) with the magic of functions by ***parameterizing*** some examples of repetitive code.

<br/>

:tv: **Video: Review of function basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU**

<br/>

:books: **Review materials:**

  - [Beginner class section 2.3: intro to functions](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-2/2-3-function-intro-challenges.md)
  - [Beginner class section 4.2: functions with inputs](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-4/4-2-function-input-challenges.md)
  - [Beginner class section 4.3: scope, function outputs, and the `return` statement](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-4/4-3-scope-and-function-output-challenges.md)
  - Again, see the video review of function basics (13 min): https://www.youtube.com/watch?v=GX5w-wTK-lU
  
<hr/>

## Group coding challenge: Functions review

:star: ***Open this Glitch project and then *click the link at the top of the page* to code with us: https://reviewgroup2.glitch.me/***

**Our challenges:**
  1. Define a function that does nothing (just the skeleton of a function definition)
  
  2. Modify that function definition to **give it one parameter**. (Now it can take an input!)
  
  3. Next, have that function return the sum of its input plus 10. (And now it gives an output!)
  
  4. Let's rename the function to better describe what it does now. (It adds 10 to any number you give it!)
  
  5. Call the function with one number as its argument. (The output won't go anywhere yet; it's not being saved to memory, displayed in the console, or shown on the web page. It just gets calculated and then immediately forgotten/thrown out.)
  
  6. Call the function again, but this time save its output to a new variable.
  
  7. Display that variable in the console. (So now we can see the output from our function in the console.)
  
  8. Call the function a second time, but with a different argument.
  
  9. Display that new result in the console.
  
  10. Define a new function that can take *two* parameters.
  
  11. Update that function definition so it returns the sum of both parameters as its output.
  
  12. Call that function with two arguments, and then display its output in the console.
  
<br/>

## Parameterizing functions

Remember that one of the most important principles for writing quality code is to keep it ***DRY*** -- Don't Repeat Yourself! Functions allow us to take repetitive code and turn it into a reusable template.

:star: ***Parameterizing*** is the technique of taking your repetitive variables and turning them into the ***parameters*** of a function.

So, buckle up! Let's practice parameterizing!

<br/>

## Challenge 1:

Take a look at the code below, and then ***write out the first four lines on two pieces of paper***, one half on each person's sheet of paper:

```javascript
console.log("Welcome, Abe!");
console.log("What's your last name, Abe?");

console.log("Welcome, Bree!");
console.log("What's your last name, Bree?");

console.log("Welcome, Cliff!");
console.log("What's your last name, Cliff?");
```

<br/>

## Challenge 2:

Let's make some beautiful artwork on that sheet of paper!

Compare the first two lines of code to the next two lines of code:

  1. In **green**, circle all the parts of the code that are repetitive.
  2. In **red**, circle all the parts that are *different*. (These will become variables!)
  
<br/>

## Challenge 3:

:star: *You might find it helpful to use [**Python Tutor**](http://pythontutor.com/javascript.html#mode=edit) for the next challenges, so you can visualize your code and see the order in which it runs!*

<br/>

Define an empty function:
  1. Give it a name that describes the repetitive actions in our example code.
  2. Give it ***one parameter*** that represents the part of the code will ***change*** between each repetitive action.

<br/>

## Challenge 4:

Copy-paste one section of the repetitive code, and put it inside the function -- in other words, make it the ***function body***.

<br/>

## Challenge 5:

Replace the part of the code that changes with the name of your parameter.

  > **Hint:** You'll need to ***concatenate*** the parameter variable to combine it with the rest of the text.

<br/>

## Challenge 6:

Call the function three times with different arguments so that the output in the console will look ***exactly the same*** as the example code given in challenge 1 above.

<br/>

:trophy: *Woohoo! You've parameterized some code to turn it into a reusable function!*

Notice that you can now call the function *as many times as you want* by typing *way less code*. It's also much easier to change how it works, since now you only need to change the code in one place!

<br/>

## Challenge 7:

Test out the following code, and then ***on two more sheets of paper, write out sections 1 and 2***, one half on each person's sheet:

```javascript
// Names of variables we'll be using for all our calculations below
let itemPrice;
let taxAmount;
let totalCost;

// Calculate the total cost of this purchase, including tax
// ***** SECTION 1 BELOW *****
itemPrice = 20;
taxAmount = itemPrice * 0.0725;
totalCost = itemPrice + taxAmount;
console.log("Total amount due: " + totalCost);

// ***** SECTION 2 BELOW *****
itemPrice = 50;
taxAmount = itemPrice * 0.0725;
totalCost = itemPrice + taxAmount;
console.log("Total amount due: " + totalCost);

// Once more for good measure (DON'T BOTHER WRITING THIS ON PAPER)
itemPrice = 5;
taxAmount = itemPrice * 0.0725;
totalCost = itemPrice + taxAmount;
console.log("Total amount due: " + totalCost);
```

<br/>

## Challenge 8:

Compare section 1 to section 2 on paper:

  1. In **green**, circle all the parts of the code that are repetitive.
  2. In **red**, circle all the parts that are *different*.
  
<br/>

## Challenge 9:

All together now! Turn this code into a reusable function that's nice and DRY.

Then call the function 3 times with the appropriate arguments so that the console will display ***exactly the same output*** as the example code from challenge 7.


<br/>

## Challenge 10:

How many lines of code are you saving, if you compare your code from the previous challenge to the repetitive example code from challenge 7?

<br/>

## Bonus callenge:

Given your code for challenge 9, what if you wanted to show the total cost of each purchase in ***different places*** for each of your three function calls?

Change your function definition so that it now returns an ***output***. Then change your three function calls to make use of that ouput in these three different ways:

  1. Display the first result *only* to the console.
  
  2. Display the second result *only* on the web page. (Just replace the text of the entire body of the page with the result of your function call.)
  
  3. Save the result of your function call into a new variable, and don't display it anywhere. (Pretend that later on, you'll save it to Firebase or send it to another server via an API call.)

<br/>

<hr/>

:point_right: **Next up:** [in section 4.2, we'll take our first look at the underlying protocol that allows us to access APIs over the internet](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-4/4-2-apis-intro-http.md)!
