# 1.2: Reviewing JavaScript objects

Next, let's review objects in some more detail. They're especially important now that we're going to start working with databases and APIs!

:books: **Previous review materials:**

  - [Overview of objects vs arrays (section 3.1 from beginner class)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-3/3-1-overview-objects-versus-arrays.md)
  - [Intro to object practice challenges (section 3.2 from beginner class)](https://github.com/LearnTeachCode/intro-javascript-class/blob/march-2018/week-3/3-2-object-challenges.md)

<br/>

:star: For the following challenges, please run your code ***both*** in [Python Tutor](http://pythontutor.com/javascript.html#mode=edit) and directly in your web browser's console. (They each have their advantages!)

<hr/>

## Challenge 1:

First, some general questions to get the ball rolling. **As a group, let's discuss:**

  1. What is an object?
  
  2. What is an array?
  
  3. At a high level, what's the difference between an object and an array?
  
  4. What's the benefit of using objects? What is their purpose? (In other words, why were objects invented as a feature of programming languages?) 
  
<br/>

## Challenge 2:

Using JavaScript's ***object literal notation***, create an object named `favoriteMovie` that represents one of your favorite movies. (It should include a few pieces of information about the movie -- doesn't matter what, as long as it's a valid JavaScript object!)

  > **Remember:** You can use review materials from our previous classes, and you can also search for examples online!
  
Check that it worked by displaying the entire object in the console, using the built-in `console.log()` function.

<br/>

## Challenge 3:

Next, write a line of code to **access** one property of your favorite movie and **display it in the console**.

<br/>

## Challenge 4:

Without modifying any of the code you wrote previously, now write one new line of code to **add a new property** to your object that specifies the name of that film's director. The property name (also called the **key**) should be `director`.

Be sure to also display the new information in the console to make sure it worked!

<br/>

## Challenge 5:

Next, write *another* line of code (again, don't modify any of the code you wrote before!) and **change** the value of the `director` property to become the following new value: `"This string will be replaced with an object next!"`

Double check that it worked by displaying the new value in the console.

<br/>

## Challenge 6:

Create a second, separate object named `directorData` that contains some information about the director of your favorite movie -- maybe their name, date of birth, favorite food, anything you want! (Yes, you can make it up; we won't be fact-checking.)

Make sure your code works by displaying the entire object in the console.

<br/>

## Challenge 7:

Now, again *without changing any previous lines of code*, write one new line of code that assigns that entire `directorData` object as the new ***value*** of the `director` property of your `favoriteMovie` object. (Whew, try to say that ten times fast!)

Then log (in other words, display) the new information in the console in these two different ways:
  
  1. Log the *entire* `favoriteMovie` object
  2. Log only the value of the `director` property of your `favoriteMovie` object

Hurray! You just created a nested object -- one object inside of another!

<br/>

## Challenge 8:

Display the director's name (or any other piece of information) in the console, using your new nested objects!

<br/>

## Challenge 9:

Copy-paste the code defining the nested object below, and then practice accessing each of its properties!

```javascript
let house = {
  address: "123 Main Street",
  kitchen: {    
      width: 10,
      length: 10,
      fridge: {
          brand: "Samsung",
          model: "RH25H5611SR"
      },
      oven: {
         brand: "KitchenAid",
         model: "KODE300ESS"
      }
  }
};
```

How many levels deep is the data in the nested object above?

<br/>

## Challenge 10:

In the previous section, we created a super simple click-counting game based on [this starter project on Glitch](https://glitch.com/edit/#!/dragon-defeater-v0-starter). Now, imagine that we want to turn this into a ***multiplayer*** game so that users can compete with their friends to find out who can click the button the most times! (Doesn't that sound like the most fun you could ever have?)

**Discuss:** In order to accomplish that, what do we need to change about our **data model** for this game? What new pieces of information would we need to keep track of in addition to the number of clicks that we were tracking before?

<br/>

<hr/>

:trophy: **Great work!** As you develop a solid understanding of objects, you'll be a better software developer in *any* programming language, not just JavaScript.

:point_right: **Next up:** In [section 1.3, we'll take a quick look at one (limited) form of persistent data](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-1/1-3-persistent-data.md) using a new version of our click-counter game.
