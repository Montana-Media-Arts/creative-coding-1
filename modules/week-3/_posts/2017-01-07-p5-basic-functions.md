---
title: Basic Functions in p5
module: 3
jotted: true
---

# The 2 Basic Functions in p5.js


<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/KIqijRKQ2Jk" frameborder="0" allowfullscreen></iframe></div>


We have so far only looked at one line in our "Hello World!" example, line no. 2. Obviously though, there are 2 more lines in this basic sketch we need to talk about.

Line no. 1, which has a number of things going on. And, line no. 3, which seems rather simple.

{% highlight js linenos %}
function setup(){
    ellipse(20, 20, 30, 30);
}
{% endhighlight %}

### Basics of Defining a Function

Line no. 1 defines a function called `setup()`.

In JavaScript, one way that a function can be defined is by using the `function` keyword, proceeded by the name of the function. A function definition should always include parenthesis, even if, as in the current example, they are empty. After giving a name and set of parenthesis to the function, the function is proceeded by what is known as a "function block".

A function block is always surround by curly brackets (`{}`). The last character we see in line no. 1 is the opening curly bracket for the "function block". The curly bracket character we see in line no. 3 is the closing function block bracket.

The guts of what a function does, are then placed inside of the curly brackets.

When defining a function in this way, the definition will look something like;


{% highlight js linenos %}
function nameOfFunction() {
    // things for the function to do
}
{% endhighlight %}


<br />


> Since p5 is a library for, and built on, JavaScript, a lot of the information I present this semester will be relevant to all JavaScript. Please be flexible and pay attention when I tell you whether information is specific to p5 or to all of JavaScript.

### Why Do You Care?

OK, this week I am not expecting you to write many functions or understand how to write functions. _BUT_, you will be filling in two functions in your sketches this week. In fact, you will use the following two functions in almost every code sketch you write with p5.

The first of these is the one you already saw, `function setup() { }`.

The other one is `function draw() { }`.

We will talk in depth later about writing your own functions. But, this week you need to understand what the `setup()` and `draw()` functions do in p5. These two functions are critical to p5, and could be considered as requirements for every code sketch.


## `setup()`

In p5, the setup function is where we place commands that relate to "setting up" a code sketch. p5 calls and executes the `setup()` function once, at the start of executing every p5 sketch.

You should write commands in the `setup()` function that;

1. only need to occur once
2. and need to occur at the start of the code sketch's execution.

There are a few commands and functions that you will almost always place in the `setup()` function.  For example, one command you will constantly write will be used to setup your canvas, which you could consider the workspace where information is sent to.


## `draw()`

The `draw()` function gets called by p5 after the `setup()` function has successfully been called and finished executing. You will place most of your code, especially in these first few weeks inside the `draw()` function. This is how we will tell p5 and the browser what to draw, do, or make.

The `draw()` function is where all of the "interesting" stuff will occur. This is where you will write commands to create visual artworks and interactive pieces.
