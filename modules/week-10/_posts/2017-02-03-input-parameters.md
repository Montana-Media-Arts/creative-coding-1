---
title: Input Parameters
module: 10
jotted: true
---

# Input Parameters

Many of the functions you have used include some number of input parameters that "do something" with specific data types. When writing your own functions, you will also find times when you need to include input parameters to inform the function how to do, the thing it does.

In JavaScript, since it is a _loosely-typed_ language, we can simply include input parameter namespaces, following the same rules as variable declaration.

The input parameter namespace defined within the function's parentheses, can be used as is (i.e. without further definition) within the function block.

```js
function functionName( input1, input2 ) {
    // use input1
    input1; // ← Do something with the input
    input2; // ← Do something with the input
}
```

# An Example

To illustrate, let's write a function that adds two numbers together; essentially a function to replace the addition operator.

#### Naming

The name of this function should somehow illuminate or clarify its use. In this case, since we are writing a function that "adds two things together", we might call it something like `addThings`.

#### Input Parameters

Since this function is intended to add things together, we will need to provide input parameters that pass the things to be added to the function. Let's call these `value1` and `value2`.

At this point, our function might look like;

```js
function addThings( value1, value2 ) {
    // do something
}
```

#### Doing Its Thing

Now that we have defined the outline of the function, it is time to write the _function block_ and make it "do its thing".

In this case, as we mentioned, we are going to add two things together. As a note, we have not talked about what we should do with the result yet. So, for the time being, let's simply post the result as text on our canvas.

This means we need to write a statement that takes the two values, and adds them together. Then write another statement that prints the results out as a string to the canvas.

In order to finish writing this function, I would suggest you add comments, for the steps you need to do. Then work on them step by step.

```js
function addThings( value1, value2 ) {
    // 1. Add the values together. Store them into some variable.

    // 2. Print the results as a string to the canvas.

}
```

Since we are in a new _scope_, we will need to define a variable to store the result in for later use in the function. So, using `let` create a variable called `result` that stores the two values added together, using the addition operator.

> Note: Again, since we define the input parameters in the function definition, we can use them directly in the function without redefining them.

```js
function addThings( value1, value2 ) {
    // 1. Add the values together. Store them into some variable.
    let result = value1 + value2;

    // 2. Print the results as a string to the canvas.

}
```

Finally, to print the result, lets make a String, that we will store back into `result`, which we can then print using the p5 `text()` function. We will print this to the middle of the screen. (This also means we need to change the `textAlign()` to be `CENTER`)

```js
function addThings( value1, value2 ) {
    // 1. Add the values together. Store them into some variable.
    let result = value1 + value2;

    // 2. Print the results as a string to the canvas.
    result = "The result of adding '" + value1 + "' and '" + value2 + "' is '" + result + "'.";
    textAlign( CENTER );
    text( result, width/2, height/2 );
}
```

To use this function, we can call it in our `draw()` function, passing in any two Number values. These will then print to the Canvas. For the time being, I am going to reduce the frame rate in `setup()`, then pass in random numbers every frame to both input parameter values.

```js
let num1 = floor(random(0, 100));
let num2 = floor(random(0, 100));
addThings( num1, num2 );
```

> NOTE: Since we are using p5 functions, this function ultimately must be called by one of p5's main functions. More on this later.


The final code might look like;

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/10/02_input_parameters_01/sketch.js"
        },
        {
            type: "html",
            hide: true,
            url:"../../../p5_resources/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/10/02_input_parameters_01/02_input_parameters_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/10/02_input_parameters_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/10/02_input_parameters_01/) |


# Shiffman

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/zkc417YapfE" frameborder="0" allowfullscreen></iframe></div>
