# Section 3.8: First look at the command line

They may seem old-fashioned, but [command line interfaces](https://en.wikipedia.org/wiki/Command-line_interface) are still the most powerful and flexible way to control a computer. Let's try it out!

<br/>

:star: **As you'll see, files and folders in our computers are organized just like *nested objects***! With JavaScript objects, we use a dot (`.`) to look inside an object; with file systems, we use a slash (`/`) to look inside a folder!

<br/>

  > **Fun fact:** The whole idea of a GUI or Graphical User Interface (moving a mouse around the screen, clicking on icons for files, etc) came about very gradually over the span of ***almost five decades!*** Take a look at [Wikipedia's History of the Graphical User Interface](https://en.wikipedia.org/wiki/History_of_the_graphical_user_interface) for some fascinating trivia.

<hr/>

## Setup

  1. **Remix this Glitch project: https://glitch.com/edit/#!/command-line-practice-1**

  2. On the left-side menu, **click "Logs"** and a window will pop up at the bottom of the screen
  
  3. To the right of where it says "Activity Log", **click the "Console" button**
  
  4. A new tab will open with a command line interface that lets us access all the files and folders inside our Glitch project!

<br/>

**Important note for Mac vs Windows users:**
  - Mac users can use the *Terminal* app built into their computers, and the commands we're learning will work the same way there!
  - Windows users will need to download a separate program to be able to use the same commands. For later on, I recommend [installing Git](https://git-scm.com/downloads) and using the "Git Bash" program that comes with it. But we'll return to this topic later! No need to do this right now.

<br/>

## Challenge 1:

You wake up in a dark room. It's pitch black. You seem to have found yourself inside some kind of command line tutorial that's also a text-based role-playing game -- actually, a [MUD (Multi-User Dungeon)](https://en.wikipedia.org/wiki/MUD), like the precursors to *World of Warcraft* and similar games!

You find a torch that you can use to see your surroundings

<br/>

:fire: To light the torch, type this command and then press Enter:

```bash
ls
```

<br/>

Actually, `ls` (lower-case of LS) is short for **L**-i-**S**-t. It ***lists*** the files and folders in your proximity!

<br/>

## Challenge 2:

After looking around, using your torch to light the way, you spot a door! It has a word engraved on it: `users`. How cryptic! What could be in there?!

<br/>

:door: To move from one folder/directory to another, type the `cd` command followed by the name of where you want to go:

```bash
cd users
```

<br/>

The `cd` command stands for **C**hange **D**irectory! It literally lets you change the directory that you're inside, so you can move from one place to another (sort of like navigating the rooms of a dungeon-crawler video game).

<br/>

## Challenge 3:

There are several treasures hidden in this dungeon, one for each person exploring its dark halls.

<br/>

:crown: **Your challenge:** What treasure awaits you? Use those two new commands to find out!

<br/>

## Challenge 4:

After grabbing your treasure, you realize that there seems to be no way out of this room! Even after shining your torch over every wall, you don't see any doors. Time to use some magic...

<br/>

:point_up: To move **up one level** from where you are in the tree/hierarchy of the file system, type the following command:

```bash
cd ..
```

<br/>

The `..` (two periods) is an old convention for representing the ***parent directory***, one level up in the hierarchy from where you currently are.

<br/>

:eye: To **see where you currently are**, use the `pwd` command:

```bash
pwd
```

<br/>

The `pwd` commands stands for **P**rint **W**orking **D**irectory -- show (or "print") the current (the "working") folder (also called a "directory"). 

<br/>

Use `cd ..` followed by `pwd` to move up a level and confirm where you are.

<br/>

## Challenge 5:

Using your newfound knowledge of these magical commands, enter the `easy-maze` directory and find your way out of the dungeon using this map that represents the files and folders of the maze as a JavaScript object:

```javascript
let easyMazeDirectory = {
  purpleDoor: {
    "deadEnd.txt": "No luck."
  },
  redDoor: {
    "bottomlessPit.txt": "Game over!",
    "trapDoor.txt": "You fall into the lava!"
  },
  yellowDoor: {
    "monster.txt": "Rooaaar! Better run fast!",
    greenDoor: {
      "dungeonExit.txt": "If you find this file, you win! Freedom!"
    }
  },
  blueDoor: {
    "monster.txt": "Yumm, I see food!",
  }
};
```

After escaping from the dungeon, you live to code another day! You win the game!

<br/>

## Bonus challenge:

Haven't had enough? Well, there's an even bigger, scarier maze in these dark halls! Practice what you've learned about nested objects to enter the `scarier-maze` directory and try to escape from the dungeon!
 
The following JavaScript object will serve as your map:

```javascript
let scarierMazeDirectory = {
  
  redDoor: {
    greenDoor: {
        "deadEnd.txt": "No luck."
    },
    blueDoor: {
      "monster.txt": "Roar!",
      greenDoor: {
        "deadEnd.txt": "Still no luck."
      }
    },
    blueDoor: {
      redDoor: {
        "bottomlessPit.txt": "Game over!"
      },
      greenDoor: {
        "dungeonExit.txt": "If you find this file, you win! Freedom!"
      },
      "monster.txt": "Rawr!!"
    }
  },
  blueDoor: {
    "monster.txt": "Yumm, I see food!",
    greenDoor: {
      "deadEnd.txt": "No luck here either."
    },
    redDoor: {
      "bottomlessPit.txt": "Game over!"
    },
  }
};
```

If you managed to escape from this dunegon, you're a true nested-data navigator! A treasure chest full of gold awaits you on the other side of the exit -- try not to spend it all in once place!

<br/>
<hr/>

:trophy: **Level up!** This is just a *tiny* first step, but learning how to control computers via the command line will grow your superpowers exponentially! (In other words: *"You're a wizard, Harry!"*)

:point_right: **Next up:** We'll end the day by discussing our personal project ideas as a group, to help each other get started with modeling our data!


