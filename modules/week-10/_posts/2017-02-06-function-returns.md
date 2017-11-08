---
title: Function Returns
module: 10
jotted: true
---

# Returning Data from Functions

Functions can also return data back to the calling process. This is known simply as a _function return_.

You already have experience with _function returns_, can you think of a few?


<br />

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

> Note: Although not strictly enforced, you should typically place the return statement at the end of the function.

Let's refactor the code slightly, from that previous example, to draw a smiley face at the result of the `addThings()` function.


<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas(windowWidth, 400);
    frameRate(3);
}

function draw() {
    background('rgb(91, 255, 147)');

    let num1 = floor(random(0, 200));
    let num2 = floor(random(0, 200));

    let pos = addThings(num1, num2);

    smileyFace( pos, pos, pos/200, 1.0 );
}


/* ADD THINGS FUNCTION */
function addThings(value1, value2) {
    // 1. Add the values together. Store them into some variable.
    let result = value1 + value2;

    // 2. Return the value
    return result;
}


/* SMILEY FACE FUNCTION */
function smileyFace(pos_x, pos_y, scale_x, scale_y) {
    push(); // <- Begin sandbox

    // 1. scale and position smiley face
    translate(pos_x, pos_y);
    scale(scale_x, scale_y);

    // 2. draw smiley face
    stroke(0);
    fill('rgba(234, 255, 61, 1.0)');
    ellipse(0, 0, 100);
    noStroke();
    fill(40, 255);
    arc(0, 15, 75, 50, 0, PI);
    ellipse(-20, -15, 20);
    ellipse(20, -15, 20);

    pop(); // <- End sandbox
}
{% endhighlight %}

<div class="displayed_jotted_example">
    <div id="jotted-demo-3" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/10/04_return_data_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/10/04_return_data_01/04_return_data_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/10/04_return_data_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/10/04_return_data_01/) |


# Shiffman

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/qRnUBiTJ66Y" frameborder="0" allowfullscreen></iframe></div>
