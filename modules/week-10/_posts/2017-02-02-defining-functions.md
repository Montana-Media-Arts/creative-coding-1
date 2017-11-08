---
title: Defining Functions
module: 10
jotted: true
---

# Defining Your Own Functions

This page takes a deep look at defining your own functions in JavaScript.

There are a number of required elements needed to define your own functions. The first is the use of the `function` keyword to tell the interpreter that what follows is a _function_. We see this same thing in use with `setup()` and `draw()`. The keyword `function` proceeds the namespace that we will define for the function.

The other required element is the use of parenthesis (`()`), proceeding the function namespace definition. These are sometimes referred to as the _function operator_. These signify to the interpreter that what proceeded was the function namespace. As we will find out, this is also where we define input parameters for a function.

Finally, following all of this, is the _function block_, which we discussed previously, is signified by curly brackets.

Altogether, this looks like;

```js
function functionName( input1, input2 ) {
    // do something inside function block
}
```

When comparing the above to what we know for `setup()` or `draw()`, we see both look similar;

```js
function setup() {
    // do something once
    // like...
    createCanvas(windowWidth, windowHeight);
}

function draw() {
    // do something every frame

    // like draw something;
    ellipse(40, 40, 60);
}
```

Again, you have been defining these functions in every p5 sketch you write, without knowing that was what you were really doing.


# Naming Functions

When defining functions, you should follow the same naming conventions followed for variables in JavaScript. These conventions are;

#### Function Naming Rules

1. Functions can only contain;
    - letters (`a`-`z` and `A`-`Z`),
    - numbers (`0`-`9`)
    - or underscores (`_`)
2. Function names cannot start with;
    - capital letters (`A`-`Z`)
    - or numbers
3. Functions cannot contain;
    - spaces,
    - or other special characters

#### Function Naming Suggestions

1. Although technically legal, functions should not start or end with an underscore (`_`).
2. Function names should be meaningful and descriptive.

#### Function Naming Guidelines

1. Follow the same patterns for function names throughout a code project.
    - This is especially true as it relates to multi-word functions.


Again, this rules are the same as creating variable namespaces. Be consistent; Be Descriptive; Be Simple.




# "Hello World!" As a Function

Time to build a direct example. Let's function-ify our "Hello World!" example from Week 3.

The following, is an embellished version of the [p5 "Hello World!" example, with an ellipse, from week 3]({{site.baseurl}}/modules/week-3/hello-world/).


{% highlight js linenos %}
function setup(){
    createCanvas( windowWidth, 400 );
}

function draw() {
    background( 'rgb(91, 255, 147)' );
    ellipse( 150, 150, 150 );
}
{% endhighlight %}

<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/10/01_hello_world_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/10/01_hello_world_01/01_hello_world_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/10/01_hello_world_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/10/01_hello_world_01/) |

### Function-ify Drawing an Ellipse

For a moment, let's pretend that line 7, where the circle is drawn, is some complex set of statements (or not, whatever...). We have decided to encapsulate that code in a function, so that it is easier to read our sketch.js file. To do this we might _define_ and _write_ a function called `drawCircle()`. This function, as its sole purpose, will draw a circle at `x:150px, y:150px`, that is `150px` in diameter.

We would start, by first defining our new function, like so;

```js
function drawCircle() {
    // do something to draw a circle
}
```

Again, this uses

- the `function` keyword,
- proceeded by the _namespace_ of the function,
- proceeded by the function operator (`()`),
    - which is empty, as we are not currently passing it any input parameters,
- followed by the function block (`{}`).


<br />

We would then place the "stuff to do" inside the function block. In this example, this might simply be;

```js
function drawCircle() {
    fill( 'grey' );
    noStroke();
    ellipse( 150, 150, 150 );
}
```


<br />

Finally, we could then replace our call to ellipse, within `draw()` with our newly defined function (`drawCircle()`). The resulting code might look something like;


<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup(){
    createCanvas( windowWidth, 400 );
}

function draw() {
    background( 'rgb(91, 255, 147)' );

    // call our newly defined function
    drawCircle();
}

// Our newly defined function
function drawCircle() {
    fill( 'grey' );
    noStroke();
    ellipse( 150, 150, 150 );
}
{% endhighlight %}

<div class="displayed_jotted_example">
    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/10/01_hello_world_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/10/01_hello_world_02/01_hello_world_02.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/10/01_hello_world_02/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/10/01_hello_world_02/) |


> NOTE: How we place the function definition at the end of the file. When defining functions with the syntax discussed on this page, these functions can be placed "anywhere" within the text file, even **after** they are used.
>
> The interpreter "hoists" these types of functions before it begins the execution of code statements, therefore, as far as the interpreter is concerned, these have previously been defined.
>
> For you, this means you can add functions like this to the bottom of a text file, or in another text file altogether (discussed next week). This will allow you to keep increasing the readability of your code through thoughtful organization of code and specifically, functions.



# Function Definition vs. Function Expressions

So far this week, you have seen the following for how to define a function;

```js
function functionName( input1, input2 ) {
    // do something
}
```

This way of defining a function is known as a **_function definition_**. Also, sometimes as a **_function statement_**. By and large, this is the way that we will write function in this course.

There is another way of defining function in JavaScript known as **_function expression_**.

A _function expression_ will take the following form;

```js
var myFunction = function() {
    // statements - do something
}

// to call
myFunction();
```

In the above, the function is referenced from a variable namespace.

One of the main differences between a _function definition_ and a _function expression_, is that the latter is not _hoisted_. Therefore, you cannot use or call _function expressions_ until **after** they have occurred in the code.

_Function expressions_ are being presented now, so that if you see them in other peoples code, JS discussions, or help guides, you understand what they are, and that are used similarly to _function definitions_.


# Shiffman

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/wRHAitGzBrg" frameborder="0" allowfullscreen></iframe></div>
