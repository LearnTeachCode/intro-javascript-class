## 5.2: Function practice challenges

Let's have fun with functions! Use the notes on functions [add link to 5.1!] as a reference for solving these practice problems.

<hr/>

Add to notes:

Video reviewing basics of functions in 13 min: https://www.youtube.com/watch?v=GX5w-wTK-lU
What functions are all about, why they're useful, the DRY principle, defining vs running functions, and how the computer saves function definitions to memory.

Intro to functions (slide #39 to #51): https://learnteachcode.org/javascript-intro/#/39 
Parts of a function definition: https://learnteachcode.org/javascript-intro/#/47


<hr/>

6) Write a function that takes one input, subtracts 10 from it, and console.log()s the result.

7) Now write the code that will RUN (or CALL or EXECUTE) the function above with a specific argument.

8) Write a function that takes one input, multiplies it by 5, and RETURNS (not console.log()s!) the result as output.

9) Now write the code that will RUN the function above with a specific argument, and then log the final result to the console.

10) Write a function that takes three inputs, adds them all together, and RETURNS the sum as output.

11) Now write the code that will RUN the function above with specific arguments and log the final result to the console.

12) Write a function that takes NO inputs and RETURNS the string "This function is useless" as output.

13) Now write the code that will RUN the function above, and then also console.log() its output:



Local variable (this won’t work):
function pointlessFun (x) {
   var localX = 5;
}
console.log(localX);

Adding a global variable:
var globalX = 999;
function pointlessFun (x) {
   var localX = 5;
}
console.log(globalX);

All functions can access global variables:
var globalX = 999;
function pointlessFun (x) {
   var localX = 5;
   console.log(globalX);
}

Which value will appear in the console?:
var nameTest = 999;
function pointlessFun (x) {
   var nameTest = 5;
}
console.log(nameTest);


Importance of the var keyword:
var nameTest = 999;
function pointlessFun (x) {
    nameTest = 5;
    console.log(nameTest);
}
console.log(nameTest);

