## 5.2: Function practice challenges

Let's have some fun with functions!

:books: **Resources to use in these challenges:**
  - Section 5.1: Overview of functions, variable scope, and the return statement **add link!**
  - Remember, you can also search for stuff online!

<hr/>

## Challenge 1:

What's wrong with the code below? Your challenge is to fix it!

```javascript
function (num) {
  console.log(num * 2);
}
```

## Challenge 2:

The code below should make the number `17` appear in the console. What went wrong? Try to fix it!

```javascript
addTen (num) {
  return num + 10;
console.log( addTen(7) );
```

## Challenge 3:

The code below should display the number `25` in the console, but it doesn't work! How would you fix it?

```javascript
getHalf () {
 return num / 2;
}
let newNum = getHalf(50);
console.log(newNum);
```

## Challenge 4:

We want `"Penguins are the best!"` to display in the console. Why isn't it working? Please fix it! The fate of the universe depends on you!

```javascript
function cheerForPenguins () {
 console.log("Penguins are the best!");
}
cheerForPenguins;
```

## Challenge 5:

Define a function that takes one input, subtracts 10 from it, and `console.log()`s the result. Name it whatever you want -- but best to use a descriptive name, and stick to camel case style formatting.

  > **Note:** You *don't* have to use the function yet -- just define it.

## Challenge 6:

Now write the code that will ***run*** (in other words, *call* or *execute*) the function above with a specific argument. Be sure to look in your console to see the message that was logged.

## Challenge 7:

Rewrite your function from challenge 5 so that *instead* of `console.log()`ing the result, it ***returns*** the result. Then test out your new function along with your other code from challenge 2.

:question: What's the difference between your code from challenge 1 versus this new version? Be sure to look in your console!

## Challenge 8:

Next, using your updated function from challenge 7, ***run*** the function and *save* its output to a new variable. Then `console.log()` that new variable, and check that the result appears in the console as expected.

  > Name the variable anything you like -- but as always, try to be descriptive and stick to came case!

## Challenge 9:

Next, modify your code from challenge 8 so that you still ***run*** the function, but this time you `console.log()` it directly, *without* the extra step of saving it to a variable.

  > **Hint:** Remember from our overview of functions that when a function *returns* an output, the *call* to the function gets replaced with whatever its output is.

## Challenge 10:

Define a function that takes *no inputs* and simply returns the string "This function is useless" as output. Then `console.log()` the result of calling the function, and check the console to make sure it works.

## Challenge 11:

Define a function that takes **three strings** as input and returns an array of those three strings as output.

  > As always, run the function and `console.log()` its output to check that it works!

## Challenge 12:

Define a function that takes **one object** as input, adds to that object a new property named `"newProperty"` with a value of `"test"`, and then returns the updated object as output.

  > **Hint:** Remember, you can always review [section 2.2.3: intro to objects](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-2/2-2-objects-arrays.md#223-intro-to-objects) for example code snippets!

## Challenge 13:

The code below isn't working as expected; we want to see our phrase with a question mark after it appearing in the console. What's wrong, and why? Your challenge is to fix it!

```javascript
function makeQuestion (phrase) {
  let outputQuestion = phrase + "?";
}
let myQuestion = makeQuestion("Dolphins sleep with half of their brain still conscious");
console.log(myQuestion);
```

## Challenge 14:

There's one small bug in the code below -- you only need to change *one* line of code. What's wrong, and why? See if you can fix it:

```javascript
function addNumbers (numOne, numTwo) {
  console.log(numOne + numTwo);
}
let initialCost = addNumbers(8, 12);
let tipAmount = initialCost * 0.15;
let totalCost = initialCost + tipAmount;
console.log("Your restuarant bill: " + totalCost);
```
Remember that the *only* thing `console.log()` does is display the value of something to the console -- nothing else!

## Challenge 15:

Take a look at the function defined below, and ***before you run the code***, **discuss**: What do you think you'll see appear in the console?

Then test it out for yourself in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit) by copy-pasting the function definition and then writing your own code to also ***run*** the function.

```javascript
function uselessFunction () {
  let localTest = 5;
}
console.log(localTest);
```
**Discuss:** why doesn't that code work as expected? What's wrong?

**And then fix the code!** Fix it ***two different ways*** so that the value of `localTest` will appear in the console.

## Challenge 16:

Take a look at the slightly different code below. *Before you run the code*, **discuss**: Which value do you think will appear in the console? 999 or 5?

```javascript
let testNum = 999;
function pointlessFunction () {
  let testNum = 5;
}
console.log(testNum);
```

Then try ***running*** the function defined above. **Discuss:**
- Does running the function change what appears in the console?
- Does it matter *when* you run the function in relation to the code presented above?
- Why or why not?

## Challenge 17:

Next, look at another slightly different example. Again, *before you run the code*, **discuss:**
  - What looks different about this code compared to the previous examples?
  - What will appear in the console?

```javascript
let someNum = 999;
function anotherFunction () {
    someNum = 5;
}
anotherFunction();
console.log(someNum);
```
Run the code above (exactly as it's written) and try it out in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit) and/or try adding more `console.log()` statements to see what's happening at each step.

Then **discuss**: why is this code working differently than the previous example?

## Challenge 18:

Take a look at this other variation of the code, and again, *before you run the code*, **discuss:**
  - What looks different about this code compared to the previous example?
  - What will appear in the console?

```javascript
let exampleNum = 999;
function sillyFunction () {
  let exampleNum = 5;
  console.log(exampleNum);
}
```
Then try ***running*** the function defined above. Even better, test it in [PythonTutor.com](http://pythontutor.com/visualize.html#mode=edit) as well!

**Discuss:** Why does this work differently compared to the previous examples?

<hr/>

:trophy: ***Great job!*** Understanding functions will make all the difference in your programming skills. There's a lot more to learn of course, but knowing the very basics is half the battle!
