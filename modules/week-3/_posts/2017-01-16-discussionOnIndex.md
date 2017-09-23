---
title: About index.html
module: 3
---

# About the `index.html` File

As you duplicate your `empty-example/` directory you will create a lot of `index.html` files. I feel it is necessary for just a moment to discuss what this file does, and why it is so critical to p5. You are going to create a lot of files labeled `index.html`.

`index.html` is a _very_ common file, used extensively on the internet. Of course it's contents are always different, and site specific, but typically, this is the file used for the homepage on websites. When you go to some website that terminates in a `.com`, `.org`, etc. the browser requests the `index.html` file from the websites server.

Likewise, when a URL is passed to a browser that does not specify a file, the browser automatically requests `index.html` from the host server.

This means something like `http://baseurl.com` and `http://baseurl.com/index.html` are the same. This means that something like `http://baseurl.com/about/` and `http://baseurl.com/about/index.html` are also the same. (This is not true for all websites, but for many.)


## File vs Directory based URLs

This assumption allows for the publication of "clean URL’s", as we do not need to explicitly include the `index.html` at the end of the URL. This is not to say that we could not have additional pages that we explicitly address. For example we could have additional html pages at the same directory level, such as an `about.html`. In which case the URL would look like `baseurl.com/about.html`.

However, if you wished to have a “cleaner” looking URL, you could create an additional child directory labeled `/about` and place an `index.html` within that directory. The URL for this case would look like `baseurl.com/about/`. Notice how we do not use the `.html` and instead the URL ends with a directory slash.


## Why is this important?

This discussion was had so that you could understand that when we provide a URL that ends in a directory (i.e. `....com/hw-3/`) the browser is actually requesting `.com/hw-3/index.html`.

Eventually, this means your file will live at a URL that looks something like `baseurl.github.io/120-work/hw-3/`.


## { TODO: }

Please read the following from the Mozilla Developer Network on [Dealing with Files](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files) to understand more about this topic.


# Contents of the `index.html` File

Please open the `index.html` file from `hw-3/` in Atom. It should look like the following;


{% highlight html linenos %}
<!DOCTYPE html>
<html>
  <head>
    <script src="p5_lib/p5.min.js"></script>
    <!-- <script src="p5_lib/p5.dom.min.js"></script> -->
    <!-- <script src="p5_lib/p5.sound.min.js"></script> -->
    <script src="sketch.js"></script>
    <style> body {padding: 0; margin: 0;} </style>
  </head>
  <body>
  </body>
</html>
{% endhighlight %}




Let's briefly discuss what this file does, line-by-line.

#### Line 1

This declares to the browser opening this file, that it is an "HTML5" file type. This simply means that the file uses the most recent version of the HTML specification.

#### Line 2

Line 2 simply declares everything between lines 2 and the closing `</html>` tag as the "HTML" element.

#### Line 3

Line 3 declares everything between lines 3 and 9 as belonging to the "head" element. In HTML, the head element is where developers typically put;

- metadata
    - such as the page title
    - who wrote it
    - what type of character encoding is used
- style or CSS information or links
- JavaScript code or JavaScript file links

This is the type of information that we see the current `index.html` "head" element.

#### Line 4

Line 4 is where the `index.html` document tells the browser to load the p5.js library file. A `<script>` tag is used to write JavaScript within or tell a browser to load a JavaScript file. In this case, this line tells the browser to load `p5.min.js` which, is the main p5 library file. As we can see from the `src=""` tag URL, this file is located in the child `p5_lib/` directory.

This line has to come early in our `index.html` document, as we need the p5 library loaded before we can start using p5.

#### Line's 5 & 6

Line no.s 5 & 6 are currently commented out. In HTML, comments are written with a proceeding `<!--` and followed with `-->`. Anything in-between those two symbols is ignored by a browser.

```html
<!-- This is a comment in HTML. -->
```

> HTML Style comments can also be used in markdown documents. I.E. If you have something that you want in your markdown document, but do not want it displayed when rendered, wrap it in a HTML style comment.

These lines are commented out because we do not yet need the additional p5 JavaScript libraries that would tell the browser to load. Later in the semester we will come back to these lines.

#### Line 7

This is a crucial line. This is where we tell the browser to load our p5 code sketch file. This must come after the p5.js library file, as it relies on all of the p5 language.

#### Line 8

This is a bit of styling for our sketch to do away with a browser default spacing that it adds.

#### Line 10

Typically, developers would put all of the stuff and content that would be displayed on an actual webpage inside of the "body" (`<body> ... </body>`) element. This is where actual webpage text and such would go.


## Wrap Up

This is a very brief intro to the `index.html` page. But hopefully it helps you understand what this document is doing for us, how it is used on the web, and why it is important to have.
