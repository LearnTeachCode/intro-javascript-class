# 8.3: API practice challenges part 1

In the [previous section](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-8/8-2-curl-intro.md), we used **cURL** to request a website straight from the command line, and saw that it does basically the same thing as going to a website in our web browser -- except it shows the response body as ***code***, rather than rendering it visually the way we're used to looking at websites.

Next, let's practice making requests to some fun APIs to see how the process works!

<hr/>

## Challenge 1: Practice reading API documentation and get a random joke

Somebady made a [**Dad Jokes API**](https://icanhazdadjoke.com/api) just for laughs. It's not a very *useful* API, but it's a nice simple example of how APIs work -- plus, some of the jokes are actually sort of funny! :laughing:

When learning how to work with any API, *most* of your time will be spent just reading their documentation!

  > In fact, if you work in software development, reading documentation takes up a very large percentage -- you spend more time reading than you do writing code!

**Your challenge:** Look through the Dad Jokes API documentation at https://icanhazdadjoke.com/api and then figure out how to use cURL to get a random dad joke formatted as plain text.

<br/>

## Challenge 2: Use cURL's `-i` flag to see the response headers

The `curl` command has an option named `--include` (or `-i` for short) to show you (in other words, to *include*) the ***response headers***, which contain all the meta-information *about* the web page that's being sent back to you.

**Here's an example of what it looks like to use the `-i` flag:**

```bash
curl http://example.com/ -i
```

**Your challenge:** Request another random dad joke, but this time use the `-i` flag!

  - Take a look at the response headers that they sent us. What's the **content type**? 
  
  - Can you spot the **status code** at the very top of their headers? What is it?

<br/>

## Challenge 3: Compare responses in the browser versus command line

**Your challenge:** Use your web browser to access the URL you just used in cURL to get a random dad joke. Use the Network panel in Chrome's developer tools to inspect the request named `icanhazdadjoke.com`.

  > **Remember:** you need to open the developer tools and go to the Network panel, and then **refresh the web page** to record the request/response data.

**Find out and discuss:**

  - Comparing the response info shown in the web browser to the info shown in cURL for the same URL, ***what's different*** in the response headers and the response body?
  
  - Why is it that the web browser sends you HTML, but if you do the same request via command line, their server just sends you a small bit of plain text? How do they know whether you're using a web browser or not?

<br/>

## Challenge 4: Use cURL's `-v` flag to see your request headers

The `-i` flag tells cURL to show the ***response*** headers, but the more powerful `-v` flag will show **both** the response *and* the ***request*** headers!

When you see the data in your command line, the request headers are prefaced with the `>` symbol, and the response headers are prefaced with the `<` symbol (facing the opposite direction).

**Your challenge:** Use cURL to get another random joke, but this time use the `-v` flag to see both the request and the response headers.

  - In the request headers, what's your **user agent** identified as?
  
  > **Hint:** Look at the request headers, which appear *above* the response headers and have the `>` symbol at the beginning of each line. Thie will appearbut *below* the "TLS handshake" stuff (which handles establishing a secure connection because we're using HTTP**S** and not HTTP, where the S stands for a Secure connection).
 
  - Look at the Network tab in your web browser again now, for the same URL you had requested vai cURL. What is your *web browser* sending to their server as the **user agent** header?


## Challenge 5: Send your own headers using cURL's `-H` flag

cURL has *yet another* very useful flag: you can add *your own* information to your request headers with the `-H` flag (note: it *must* be a capital H).

**Your challenge:** Trick the Dad Joke API's server into thinking our that command line is actually the Mozilla Firefox web browser! To do this, we can use the User-Agent header:

```bash
curl "https://icanhazdadjoke.com/search?term=hipster" -H "User-Agent: Mozilla/5.0"
```

What happened? Did we fool them? ;)

<br/>

## Challenge 6: Request data in a particular format

There are several different standard **data formats** used in the software world: [**XML**](https://en.wikipedia.org/wiki/XML) used to be the common standard, but in recent years [**JSON**](https://en.wikipedia.org/wiki/JSON) has become more popular. You can think of these data formats like different file types (`.doc` for Microsoft Word files, `.jpg` or `.png` for images, `.html` for web pages, etc.)

**Your challenge:** Get another random dad joke, but this time get the joke in **JSON format** instead of plain text. Look at their documentation to find out how to do this!

  > **Hint:** You'll need to add another piece of information to your request headers.

<br/>

## Challenge 7: Use query parameters in your API request

**Your challenge:** Find a knock-knock joke from the Dad Jokes API, get the ID of the joke, and then get that joke as an image file. *Use their documentation to figure out these next steps!*
  
  1. First, search the Dad Jokes API for jokes containing the word "knock-knock". 
  
  2. Then copy or write down the ID of the joke that was sent in the body of the response, because you'll be using it in the next step!
  
  3. Use cURL again to request that particular joke as an image file, using its case-sensitive ID.
  
  4. Discuss: What just happened? Why do you think the response body looks like this inside the command line?

  5. Next, use your *web browser* to access that same URL (the URL that you requested to get the image file).
  
  6. Discuss: Now what happened? Why does it work differently?

  7. Last but not least, use the Network panel in your browser to take a look at the response headers for that web page containing the image. What's the **content type** of this response?

<br/>

## Bonus challenges: Try the FOaaS API

:warning: Before looking at the website below, please note that it contains ***adult language*** that is quite inappropriate and possibly offensive. (Only proceed if that fits your sense of humor!)

OK, here we go! [**FOaaS** (F%$# Off as a Service)](http://www.foaas.com/) is another ridiculous API that somebody made as a joke. It just generates insults for you, based on your own custom parameters.

### Bonus challenge 1:

**Your challenge:** Read over the [FOaaS API documentation](http://www.foaas.com/) and try out a couple of their API's endpoints!

Notice that instead of using query parameters in the `?parameter=value` format, they identify parameters in their URLs (also called endpoints) with a different format in their documentation, where each parameter is preceded by a ***colon***.

For example, to access the `/cup/:from` endpoint (as it appears in their documentation), you're expected to replace `:from` with your own name. So I would send my request to `/cup/Liz` and I'd see my name appear in their response, along with the offensive and silly message that their API generates.


### Bonus challenge 2:

The FOaaS API also supports multiple data formats!

**Your challenge:** Try another one of their endpoints, but this time request the data in **JSON format**!

If you like, try requesting **XML format** as well to see how different it looks from JSON.

<hr/>

:point_right: **Next up:** [**let's try some APIs that require an API or a personal access token in order to use them.**](https://github.com/LearnTeachCode/intro-javascript-class/blob/master/week-8/8-4-api-challenges-2.md)
