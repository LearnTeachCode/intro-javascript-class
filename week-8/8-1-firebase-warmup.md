# 8.1: Firebase warmup challenges

:weight_lifting_woman: Let's warm up those coding muscles with a few quick review challenges! We'll also take a look at one Firebase function that we've never used before in our class, which will come in handy for our next group project.

<br/>

:star: **For all of these review challenges, *remix this Glitch project:* https://glitch.com/edit/#!/firebase-practice-4**

<hr/>


## Challenge 1:

Remember objects? This should only take a minute then! :)

In your remixed copy of the Glitch project (link above), **create a new object that represents yourself.** Give it ***three*** different key/value pairs.

<br/>

## Challenge 2:

Remember when we added and deleted ourselves (or other students!) from our shared database? All the data is still there! 

First, identify the ***path*** to your own personal location in our database.

Then create a new variable to contain a ***database reference object*** pointing to that path. (And give it a descriptive name, of course!)

<br/>

## Challenge 3:

Using the object you creating for challenge 1 and the database reference object you created for challenge 2, ***insert*** the object containing your data into the database.

Remember the name of the function we were using to do that? If not, look it up real quick! You're a master Googler by now ;)

<br/>

## Challenge 4:

Now that you're an object in a database, what if you want to update yourself? Try adding ***two additional key-value pairs*** to your database object, without deleting the other ones.

<br/>

## Challenge 5:

Now try changing the values of two of those key-value pairs, without deleting any of the others. But this time, use the [Firebase `update()` function](https://firebase.google.com/docs/reference/js/firebase.database.Reference#update)!

See the example code at the very bottom of that page and modify it to work with your own code.

**Discuss:**
  - What's the difference between the two Firebase function's that we've been using so far to add data to the database?
  - What happens if you try to update data at a path in the database that doesn't exist yet? (Try creating an imaginary new student!)

<br/>

## Challenge 6:

There's one major problem with using students' names as the keys or properties in our database... what if two students have the same name?! 

First, **delete** yourself from the database.

Next, change the **path** so that the key/property that represents you is *guaranteed* to be unique. Then add yourself back into the database under that new path.

<br/>

## Bonus challenge 1:

Turn yourself in a ***nested*** object and add this new, more complicated version of yourself into the database!

<br/>

## Bonus challenge 2:

Display a list of every student's information on the web page.

<br/>

## Bonus challenge 3:

For each student in the list, create a new HTML element containing their data, and add it to the web page.

  > Do some Googling to figure out how to do this! You'll also probably find the [Firebase dataSnapshot.forEach() method](https://firebase.google.com/docs/reference/js/firebase.database.DataSnapshot#forEach) useful!

<br/>
<hr/>

:weight_lifting_woman: **Ready for more?** That was just a quick review. Now let's get to the good part!

:point_right: **Next up:** in [section 8.2 we'll put everything together from last week and build a multi-user version of Dragon Defeater!](https://github.com/LearnTeachCode/intro-javascript-class/blob/may-2018-int/week-8/8-2-login-dragon-defeater.md)
