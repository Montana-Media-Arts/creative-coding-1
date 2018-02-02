---
title: What is Going On?
module: 3
jotted: true
---

# What is Going On in "Hello World!" ?


<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/O34SIkgwpRg" frameborder="0" allowfullscreen></iframe></div>


OK, so you made your first code "sketch", but the likely hood is high, you have now idea "what is going on".

Let's start to talk about that a bit.

Here is the code again;

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup(){
    ellipse(20, 20, 30, 30);
}
{% endhighlight %}


<br />

First, let's discuss line two.

## Using Functions

In line no. 2, we used our first "_function_".


<br />


A function is a;

- re-usable piece of code,
- which can be defined or created;
    - for you (a built-in function),
    - or by you (a self-defined function).

<br />


A function is a;

- single piece of text (no spaces. More on what this means later.)
- followed directly by parenthesis `()`, without a space between them and the piece of text.
    - i.e. `nameOfFunction()`


<br />


A function;

- does _something_...
- and contains many instructions for how to do this something.

<br />



#### ellipse()

In our case, the function we are using in line no. 2 is `ellipse()`.

The ellipse function is used to draw ellipses, such as;

- ovals
- and circles

## Function "Parameters"

The behavior or specifics of what a function _does_ are specified by "_parameters_".

In p5, this may be;

- the location of something,
- the color of something,
- the size or shape of something,
- etc.

<br />

Parameters;

- Can by any data type, but must match the expected data types of the function (more on this later).
- Are always separated by comma's `,`.
- Occur within the function's paranthesis.


<br />



In our example, there are 4 parameters.

- The first 2, specify the location of the center of the ellipse on the canvas (more on that later as well).
    - In our case, we are telling the ellipse's center to be placed;
        - `20` pixels in, along the X-axis (from the left of the canvas).
        - and `20` pixels down, along the Y-axis (from the top of the canvas).
- The second 2, specify the width and height of the ellipse.
    - In our case, because both of these numbers are the same, a circle is created.
    - Specifically, a circle that is 30 pixels in width, and 30 pixels in height.

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup(){
    ellipse(20, 20, 30, 30);
}
{% endhighlight %}


<br />


### { TODO: }

I would like you to know change these parameters and notice the change to your code "sketch".

- From the below code output section, select the "JavaScript" tab.
- _OR_ in your own code, within Atom.
- Change the parameters of the `ellipse()` function in line 2.
- Explore changing the parameters.
    - You can change the first 2 parameters to be any integer (whole number) between 0 & 100.
    - You can change the second 2 parameters to be any integer between 1 & 100.

Doing this will change the position and size of the ellipse in the left corner of the available code output area.


<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/03/01_hello-world_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>


# Discovering What Functions Can Do

Regrettably, until you spend many, many, many, hours coding in p5, or any language, it will be difficult to remember;

- what parameters a function accepts,
- what these parameters do,
- and often, what the function itself does.

Luckily, any language "worth it's salt" will have detailed and accessible documentation. p5 is a language designed for artists and beginners, and has a great documentation section.

Let's look at the documentation for the `ellipse()` function. Below is the documentation page for the `ellipse()` function from the p5 website.

<br />


Notice that this page from top-to-bottom tells the user;

- What language is being discussed
- That this is a "Reference" page
- What is being referenced on this page.
    - In this case, the p5 `ellipse()` function.
- An example of how to use the function.
- A description of the topic in question.
- A "Syntax" description
    - This is a more descriptive portion of how to use the function.
    - For the `ellipse()` function, this lists the function, along with the parameters it accepts.
    - These parameters are "named" so that we know how to refer to them.
    - Parameters that appear within a set of square brackets `[]`, are optional parameters.
        - In the case of the `ellipse()`, providing only the `w` parameter is acceptable, as the function will use the same value for the height of the ellipse, thereby creating a perfect circle.
- A detailed description of the named "Parameters"
    - Each parameter is listed by its name.
    - This is followed by data type the parameter expects.
        - In the case of the `ellipse()` each parameter expects a "Number".
    - Each list item concludes with a description of what the parameter effects in the function.
- Finally, each function page has a "Return" section. This tells the user what the function returns. (We will talk about this more later).
    - In the case of the `ellipse()`, the function returns a new "ellipse object".

([Direct Link to `ellipse()` doc page.](https://p5js.org/reference/#/p5/ellipse) In case the page does not load below, or you would like to see the page directly in the p5 website.)

<div class="embed-responsive" style="padding-bottom:80%; border: 1px solid #000"><iframe class="embed-responsive-item" src="https://p5js.org/reference/#/p5/ellipse" frameborder="0" allowfullscreen></iframe></div>

The following link will take you to the top-level page for p5 documentation. You should book mark this page, as you will utilize it a lot this semester. Please do a number of things on this page;

1. Quickly browse the various functions and classes that exist in the p5 documentation. Taking note of the various Heading Categories that they exist under.
2. Find the `ellipse()` function and identify how it is categorized?  (i.e. what headings is it underneath?)
3. Click through to a few more of the functions in the same category as `ellipse()`. See if the documentation for these functions makes sense? And if you can understand how they might be used?

[**P% Reference Page**](https://p5js.org/reference/)
