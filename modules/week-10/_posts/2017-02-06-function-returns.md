---
title: Function Returns
module: 10
jotted: true
---

# Returning Data from Functions

Functions can also return data back to the calling process. This is known simply as a _function return_.

> You already have experience with _function returns_, can you think of a few?



What about the `floor()` function? This function takes a single input parameter. If a valid Number is supplied, it returns the floor value, or the nearest whole number that is less than the supplied parameter.

The value that is _returned_ can be stored inside another variable or used right away.

```js
console.log( floor(3.14) ); // ← print the value to the JS console

let flr = floor( 3.14 ); // ← pass the resulting value to a variable for storage an later usage.
```

To return data from a function in JavaScript, you simply need to prepend the target data with the keyword `return`, with a space between the keyword and return data.

In the following example, the String value "Musick", would be returned from the function.

```js
function testReturn() {
    return "Musick";
}

/////////////////////////////////////////////
let testVar = testReturn();
testVar; // ← is set to "Musick"
```

You can return any type of data you want, and it can be passed to the `return` keyword using variables.

Let's return to the `addThings()` function. It would likely be more useful for the function to return the results of addition, rather than simply post text to the canvas. To do this, you simply need to pass the results of the operation to the `return` keyword.

```js
function addThings( value1, value2 ) {
    // 1. Add the values together. Store them into some variable.
    let result = value1 + value2;

    // 2. Return the value
    return result;
}
```

> Note: Although not strictly enforced, you should typically place the `return` statement at the end of the function. As you will find out, the `return` keyword causes a function to "finish" or stop execution. This keyword, along with telling the interpreter to send out some data, also tells it that the function is finished executing.

Let's refactor the code slightly, from that previous example, to draw a smiley face at the returned result of the `addThings()` function.


<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/10/04_return_data_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/10/04_return_data_01/04_return_data_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/10/04_return_data_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/10/04_return_data_01/) |


# Shiffman

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/qRnUBiTJ66Y" frameborder="0" allowfullscreen></iframe></div>
