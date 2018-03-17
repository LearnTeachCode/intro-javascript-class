# 3.5: Intro to data modeling and nested data structures

If you want an extra review in the form of a video (totally optional because it's pretty long!), here's a look at objects inside arrays, arrays inside objects, etc, with a focus on the bigger picture of how code blocks are like Lego pieces, but even more powerful thanks to recursion!

:tv: **Video: Intro to nested data structures and the idea of recursion (30 min): https://youtu.be/YmyROsrVQWI**

  > **Note:** This is an older video, which is why you'll see `var` instead of `let`. Also planning to remake this one later.

**Table of Contents:**  
  - 2.3.1: Data modeling
  - 2.3.2: Nested data structures

<hr/>

## 2.3.1: Data modeling

We've already practiced modeling data with our array vs object discussion exercises. A [***data model***](https://en.wikipedia.org/wiki/Data_model) is just a plan (sort of like a blueprint) that formally describes how different pieces of information relate to one another, to help with deciding how to implement a system that needs to work with that data.

A [***data structure***](https://en.wikipedia.org/wiki/Data_structure), by contrast, is a *specific implementation* for storing and working with data in a computer. So you can think of the data model as the plan (the abstract ideas), and the data structure as the code that lets you start to turn your plan into a working software application.

Let's walk through a simple example of how to turn a data model into actual code that we could use in a database!

**Example data model:**

Imagine that we want to build a database of [fictional penguins](https://en.wikipedia.org/wiki/List_of_fictional_penguins), where each penguin has a name, an origin (which movie or TV show it's from), and whether or not it can fly.

We should probably have some type of object to represent each penguin, and we need a list of all those penguins with a unique ID number assigned to each one (in case two penguins have the same name, for example). The database will contain that list of penguins, and in the future it might contain other lists in the same database (like information about what penguins like to eat).

Here's a drawing of how we might model this database:

![Fictional penguins data model](https://user-images.githubusercontent.com/1555022/27149346-0d6f3012-50f8-11e7-852b-647ebecf3426.jpg)

And here's how that same data is represented in an actual database (in this case a Firebase database, which we'll learn more about later on):

![Fictional penguins Firebase database](https://user-images.githubusercontent.com/1555022/27147872-37732274-50f3-11e7-90f2-70c82e539477.png)

Notice that we haven't written any code yet, and we haven't talked about using objects versus arrays or any of that yet! In this first step, we've just created an abstract **data model** with some specific example data to help us visualize it.



## 2.3.2: Nested data structures

:tv: **Video: Intro to nested data structures and the idea of recursion (30 min): https://youtu.be/YmyROsrVQWI**

Now let's practice creating a nested data structure with our data model for the penguin database, turning that plan into actual code.


**Example code for each penguin object:**

First, let's start with the three individual penguins. It makes sense to structure them as objects, since it doesn't matter what order we list their attributes. Here's the code for our three separate penguin objects:

```javascript
let gunter = {
  "name": "Gunter",
  "origin": "Adventure Time",
  "canFly": false,
};

let ramon = {
  "name": "Ramón",
  "origin": "Happy Feet",
  "canFly": true,
};

let fred = {
  "name": "Fred",
  "origin": "Sitting Ducks",
  "canFly": false,
};
```

  > **Note:** You don't *need* to put quote marks around property names, but it's a format you'll see often when using JSON as a data format, which stands for JavaScript Object Notation. (A topic for a bit later!) But if you're curious, take a look at [this intro to JSON](https://www.w3schools.com/js/js_json_intro.asp) and then [this more detailed intro to JSON](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/JSON).

**Creating our nested data structure:**

Next, let's create an object for the database itself:

```javascript
// Our database, which is empty for now:
let penguinDatabase = {
  
};
```

Just to practice and to make sure we're doing this right, now let's create an array containing our three penguin objects:

```javascript
// This will be the general structure of the penguins array, which contains three empty objects for now:
let penguins = [ { }, { }, { } ];

// Same thing as above, but reformatted to be easier to read:
penguins = [
  { },
  { },
  { }
];

// Now let's put the data for our actual penguins into those three objects:
penguins = [
  {
    "canFly": false,
    "name": "Gunter",
    "origin": "Adventure Time"
  },
  {
    "canFly": true,
    "name": "Ramón",
    "origin": "Happy Feet"
  },
  {
    "canFly": false,
    "name": "Fred",
    "origin": "Sitting Ducks"
  }
];
```

Great! So now we have a *nested* data structure that's two levels deep: an array containing three objects.

Next, let's finish the last level and put all the pieces together. We'll end up with a nested structure that's *three* levels deep: an object at the highest level, which contains one array, which itself contains three objects:

```javascript
// Here's our penguinDatabase with one key-value pair. The key is "penguins" and the value is an empty array for now:
penguinDatabase = { 
  "penguins": [ ]
};

// Now here we put our three penguin objects into that array:
penguinDatabase = {
  "penguins": [
    {
      "canFly": false,
      "name": "Gunter",
      "origin": "Adventure Time"
    },
    {
      "canFly": true,
      "name": "Ramón",
      "origin": "Happy Feet"
    },
    {
      "canFly": false,
      "name": "Fred",
      "origin": "Sitting Ducks"
    }
  ]
};
```

If later on we also wanted to add a list of penguin food to our database, the general structure could look like this:

```javascript
// Now our penguinDatabase object has TWO key-value pairs, one for the penguins and one for penguinFood. Both values are empty arrays in the code below (just to keep it short):
penguinDatabase = { 
  "penguins": [ ],
  "penguinFood": [ ]
};
```

Now, there's one important detail to change for the data above to work in an *actual* Firebase database. **One of the quirks of Firebase is that it actually doesn't support arrays!** It can handle strings, numbers, objects -- but just not arrays.

Why is that? The main reason is because the unique IDs that Firebase generates for items in the database sometimes contain letters, not just numbers! And remember: you can only access elements of an array using an index number. If you want to use a more descriptive label for each piece of data, you'll have to use an object instead!

So next we'll create our final data structure, changed to **an object containing another object**, which itself contains more objects:

```javascript
// Here's our penguinDatabase with one key-value pair.
// The key is still "penguins", but now the value is an empty OBJECT:
penguinDatabase = { 
  "penguins": { }
};

// Next, we'll add three key-value pairs inside the penguins object.
// Notice the KEY or PROPERTY is the unique ID number, and the value
// of each one is an empty object:
penguinDatabase = { 
  "penguins": {

    "1152": { },
    "1153": { },
    "7344": { }

  }
};

// Finally, let's put the data for each penguin into those three objects!
// Here's our final nested structure, three levels deep, all based on objects:
let penguinDatabase = {
  "penguins": {
    "1152": {
      "canFly": false,
      "name": "Gunter",
      "origin": "Adventure Time"
    },
    "1153": {
      "canFly": true,
      "name": "Ramón",
      "origin": "Happy Feet"
    },
      "7344": {
      "canFly": false,
      "name": "Fred",
      "origin": "Sitting Ducks"
    }
  }
};
```

**So that's the gist of modeling and structuring data in JavaScript!** This is just a first introduction of course; as with every topic we're exploring, there's always much more detail under the surface. But this should be enough to get you started towards modeling data for your own projects!
