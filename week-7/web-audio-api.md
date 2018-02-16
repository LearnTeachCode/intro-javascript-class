# 7.1: Intro to the Web Audio API

In [section 5.4: Intro to APIs (Application Programming Interfaces) and interfaces in general](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-5/5-4-intro-apis-background.md), we learned that there are built-in web browser APIs that allow us to use JavaScript code to interact with a web page (and the user's computer). The `document.getElementById()` function is one example of this; it's part of the browser's built-in [**Document Object Model API**](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)! Another fun example is the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API), which lets us create and play sounds directly in the web browser using JavaScript. Let's try it out!


**Table of contents:**
  - 7.1.1: Try out some web audio demos
  - 7.1.2: Overview of using the web audio API
  - 7.1.3: Web audio challenges

<hr/>

## 7.1.1: Try out some web audio demos

**1. Simplest example of creating sound in your web browser:**

Copy-paste the code below straight into your web browser's console. Make sure the volume on your computer is ***quiet*** because the sound might be loud!

```javascript
// Initialize the web audio API to work in different web browsers:
let audioContext = new (window.AudioContext || window.webkitAudioContext)();

// Create an oscillator object to start generating sound waves
let oscillator = audioContext.createOscillator();

// Set the type of wave and its frequency
oscillator.type = 'sine';
oscillator.frequency.value = 440;

// Connect the oscillator to your speakers (the default "destination")
oscillator.connect(audioContext.destination);

// Start the oscillator to generate the sound!
oscillator.start();
```

***Wait, how do I turn this thing off?!*** Copy-paste this code next:

```javascript
// Stop the oscillator to turn off this sound
oscillator.stop();
```

<br/>

**2. Demo of the four types of oscillators:** https://musiclab.chromeexperiments.com/Oscillators

  > [Oscillators](http://beausievers.com/synth/synthbasics/) are the building blocks of synthesized sounds; they generates sound waves to make different sounds. There are **four** types of these waves, which are demonstrated in the demo app linked above. The faster and closer together the waves are (faster the vibrations in the air), the higher the pitch or frequency of the sound.

<br/>

**3. Theremin (and drawing) app:** http://mdn.github.io/violent-theremin/

  > A [theremin](https://en.wikipedia.org/wiki/Theremin) is an electronic instrument that you play by moving your hand between two antennas, without actually touching anything! It's named after Léon Theremin, the guy who invented it back in 1928.

<br/>

 **4. More fun web audio demos:** https://musiclab.chromeexperiments.com 

<br/>

Next, let's look at a couple more things we can do using a little bit more code:

## 7.1.2: Overview of using the web audio API

Every time you generate sounds in the web browser using the web audio API, you'll need to do the following steps:

1. Initialize it by creating a Web Audio API context
2. Create an oscillator inside that context
3. Choose the waveform type (sine, square, triangle, or sawtooth)
4. Set the frequency (how high or low the pitch is)
5. Optional: connect the oscillator to other "nodes" to modify the sound (like change the volume, apply sound effects, etc)
6. Connect the oscillator (or the last node from step 5) to the destination (default: your computer's speakers)
7. Start the oscillator (to run continuously, or for a certain amount of time)
8. Optional: Stop the oscillator to turn off the sound

Try out the code samples below to see a couple things you can do, based on the steps above:

### Play a sound for a certain amount of time:

```javascript
// Set everything up just like in the first demo from above:
let audioContext = new (window.AudioContext || window.webkitAudioContext)();
let oscillator = audioContext.createOscillator();
oscillator.type = 'sine';
oscillator.frequency.value = 440;
oscillator.connect(audioContext.destination);

// Start playing the sound right now
oscillator.start();

// Stop playing the sound three seconds after the current time
oscillator.stop(audioContext.currentTime + 3);
```

### Change the volume of a sound:

```javascript
// Set everything up just like in the first demo from above:
let audioContext = new (window.AudioContext || window.webkitAudioContext)();
let oscillator = audioContext.createOscillator();
oscillator.type = 'sine';
oscillator.frequency.value = 440;

// Create a node to control the volume (also called "gain")
let volumeNode = audioContext.createGain();

// Set the volume to a value from 0 to 1 (so 0.5 is 50% of the max volume)
volumeNode.gain.value = 0.5;

// Connect the node to the oscillator
// (so it will modify THIS sound; you can have multiple oscillators and change the volume on each one!)
oscillator.connect(volumeNode);

// Connect the last node to the audio destination (default: your computer's speakers)
volumeNode.connect(audioContext.destination);

// Play the sound for 3 seconds, using code from the sample above:
oscillator.start();
oscillator.stop(audioContext.currentTime + 3);
```


## 7.1.3: Web audio challenges

Now that we've seen what the web audio API can do, let's experiment with writing some code!

### Challenge 1:
 
Create a new Glitch project with two buttons: start and stop. When the user clicks "start", play a sound! When the user clicks "stop", stop playing the sound.

### Challenge 2:

Add an input box to your page, and add a paragraph containing instructions to tell the user to enter a number representing the frequency of the sound to play. Now when the user clicks the "start" button, grab that number that the user typed, and use it to control the actual frequency of the sound that plays!

  > For reference, the frequency of middle C is 261.626 Hz. Take a look at [Wikipedia's list of piano key frequencies](https://en.wikipedia.org/wiki/Piano_key_frequencies#List) to get a sense of the range of this frequency number!

### Challenge 3:

Add four more buttons to the page, one for each of the basic sound waves: sine, square, triangle, and sawtooth. Now whenever the user clicks one of those buttons, immediately change the type of sound being played!

### Challenge 4:

Look up the "mousemove" JavaScript event; read the documentation and find a small working example to test out for yourself, confirming that you understand the basics of how it works. Find out how to access the mouse coordinates at any point in time using that event.

Create a tiny experiment (you can make a new Glitch project for this, or type directly in your browser console) and see if you can `console.log()` the mouse coordinates while the user is moving the mouse!

### Challenge 5:

Then use that "mousemove" event in your web audio API project web page so that as the user moves their mouse higher or lower on the screen, the frequency of the sound changes based on their mouse movement! (A lot like this demo: http://mdn.github.io/violent-theremin/)

### Bonus Challenge 1:

Using multiple computers (or multiple projects opened in multiple tabs in your web browser), make three (or more!) different example apps that use the web audio API to play notes at different frequencies, so that when you play them all at once, they'll play a nice sound like the C Major chord!

  > The frequencies of the C Major chord are **261.626**, **329.628**, and **391.995**.

### Bonus Challenge 2:

Create the same effect as in bonus challenge 1 above, but *all within the same web app!* In other words, you should have *one* JavaScript file that plays three different sounds all at the same time.

  > **Hint:** To play multiple sounds, you'll need to create multiple oscillators! But you only need to initialize the audio context object *once* for your whole project. So most of this challenge will just be copy-pasting your previous code and making a couple small changes to get it to work when it's all in the same file.

<hr/>

:trophy: ***Congrats!*** **You can turn your web browser into a musical instrument, and now you know how to combine multiple built-in web browser APIs together (the Document Object Model API and the Web Audio API) to create all sorts of creative apps!**
