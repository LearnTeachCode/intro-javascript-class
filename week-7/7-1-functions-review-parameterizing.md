# 7.1: Functions review and parameterizing repetitive code

:weight_lifting_man: Let's practice making our code DRY (Don't Repeat Yourself!) with the magic of functions by ***parameterizing*** some examples of repetitive code.

:books: **Reveiw:** [Section 2.4: intro to functions with parameters and arguments](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-2/2-4-function-challenges.md)

<hr/>

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

:point_right: **Next up:** [in seciton 7.2, we'll start learning about variable scope and why functions are so much more useful when they return an output](https://github.com/LearnTeachCode/intro-javascript-class/blob/july-aug-2018/week-7/7-2-scope-and-function-output.md)!
