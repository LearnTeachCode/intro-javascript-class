# Section 3.2: Planning our group project: Simple slideshow   

To learn about some new topics today, let's kick things off by discussing and planning for a new group project. This time, we'll build a tiny image slideshow! After mapping out our plan, we'll dive into some new topics, and then we'll build it in two phases. 

<hr/>

## So what are we building?

:hammer: **Feature requirements:**

  1. The app will have a bunch of image URLs saved in memory.
 
  1. The web page will have a title, instructions, an image, and two buttons: "next" and "previous".

  1. When the user clicks "next", show the next image.

  1. When the user clicks "previous", show the previous image.

  1. The images should appear in the same order every time (not randomized).

  1. Once the user reaches the end of the slideshow, it should wrap around and start over again from the beginning. 

<br/>

## Structuring our data

Based on what we've learned so far, we could store the data for our images like this, using a bunch of variables that contain strings (one for each URL):

```javascript
let image1 = "http://example.com/url1";
let image2 = "http://example.com/url2";
let image3 = "http://example.com/url3";
let image4 = "http://example.com/url4";
``` 

<br/>

**Let's discuss:**
 
  1. What's wrong with that code?

  1. How would we tell the computer to cycle through each of these variables?

  1. What if instead of using hard-coded images, we used data taken from a database, the user's input, or an API? How would we cycle through *any number* of images?

<br/>

Here's an example of how ***not*** to cycle through a group of data:

```javascript
// Kids, don't try this at home!!

// Start at image #1
let currentImage = 1;

if (currentImage === 1) {

  // Move from image 1 to image 2
  currentImage = 2;

} else if (currentImage === 2) {
 
  // Move from image 2 to image 3
  currentImage = 3;

} else if (currentImage === 3) {
 
  // Move from image 3 to image 4
  currentImage = 4;

}
```

See how clunky that is? It requires a lot of typing, the code is very repetitive, and here's the biggest problem of all: ***this only works if we know exactly how many images we have***. 

<br/>

For more complex apps, we usually don't know how much data we have at any given time, because it's always changing! (Imagine our data is a to-do list where the user can add/remove as many items as they want, or imagine that our images came from an API that could send us *any number* of images.)

So to work with more flexible data, we need more flexible ***data structures*** that allow us to group our data together.


<br/>

### Storing data in memory:

If we tell the computer to create four variables, one for each image URL, then the computer's memory would look like this:

| name   | value |
|--------|-------|
| image1 | `"http://example.com/url1"` |
| image2 | `"http://example.com/url2"` |
| image3 | `"http://example.com/url3"` |
| image4 | `"http://example.com/url4"` |


<br/>

But we want the computer's memory to look something more like this, where all our data is ***grouped together*** and we don't need to manually create a new slot in memory for every new URL:

| name   | value |
|--------|-------|
| imageUrls | `"http://example.com/url1"`<br/><br/>`"http://example.com/url2"`<br/><br/>`"http://example.com/url3"`<br/><br/>`"http://example.com/url4"`<br/><br/> ...as many as we want! |

<br/>

Keeping this difference in mind, let's talk more about structuring groups of data, then dig into some small examples, and finally return to build our image slideshow!


<br/>
<hr/>

:point_right: **Next up:** [....](#)

