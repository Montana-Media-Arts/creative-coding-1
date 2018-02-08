---
title: Array Examples
module: 9
jotted: true
---

# Arrays in p5

Now that we have discussed what arrays are a bit, let’s look more specifically at how to use them within p5 and JavaScript.

## Printing Arrays as Strings

The following simple example demonstrates;

1. The creation of two arrays,
	1. an empty array
	2. and a pre-filled array.
2. The printing of both of these arrays as strings, using the p5 `text()` function.

```js
// create an empty array
let emptyArray = [];

// create a filled, array
// in this case, we have placed in integers
let numArray = [2, 4, 9, 100];


function setup() {
    createCanvas(windowWidth,400);
    bg_color = color(230, 240, 200);
    background(bg_color);
}

function draw() {
    textSize(56);
    // print the arrays to the screen
    text("emptyArray: " + emptyArray, 20, 80);
    text("numArray: " + numArray, 20, 200);
}
```


    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/09/01_array_print_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/01_array_print_01/01_array_print_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/01_array_print_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/09/01_array_print_01/) |




Notice how the elements of the `numArray` are printed. Also notice, since the `emptyArray` is empty, nothing is printed.


#### To access a single element

To print only a single element from an array, we access it using its index number. The following example;

1. Creates an array filled with strings
2. Prints out the entire array.
3. Prints out only the first element from the array.

```js
// create a filled array
// This array has strings in its elements
let stringArray = ["Ha", "JS", ":)"]


function setup() {
    createCanvas(windowWidth,400);
    bg_color = color(230, 240, 200);
    background(bg_color);
}

function draw() {
    textSize(56);
    // print the arrays to the screen
    text("stringArray: " + stringArray, 20, 80);
    text("The first element in the array is: " + stringArray[0], 20, 200);
}
```


    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/09/01_array_print_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/01_array_print_02/01_array_print_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/01_array_print_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/09/01_array_print_02/) |



Notice in the last line of code that `stringArray[0]` is used to return only the string `"Ha"`.


#### To rotate through elements

Now, let’s write a sketch that will print out a single element from the array. This sketch will also rotate through the elements, printing the _next_ element every frame.

To do this, we will need to do a couple of things;

1. Instead of directly passing an Number as the index value to the array, we will instead need to pass a variable, referencing a Number value representing the desired index value. We will use the variable `idx`, which is often used as a shorthand for "index".
2. The value of this index variable will need to be incremented every frame. (`idx++`).
3. Finally, in order to prevent an error by trying to access an element that does not exist, we will need to wrap our incrementing index variable in the length of the array. We can do this suing the modulo operator (`%`), along with the length of the array (i.e. `stringArray.length`).

The following code implements the steps we just discussed.

```js

let stringArray = ["Ha", "JS", ":)", "arrays are fun", "p5 is AWESOME!!"];

let bg_color = ‘rgb( 230, 240, 200 )’;
function setup() {
    createCanvas(windowWidth,400);
    frameRate(1);
}

// initialize a variable ‘idx’ to the Number 0
let idx = 0;
function draw() {
    background(bg_color);
    textSize(56);

    text("The index value is: " + idx, 20, 80);
    text("The element is: " + stringArray[idx], 20, 200);

    // increment the idx variable
    // also make sure it stays within the bounds of the array
    idx = ( idx + 1 ) % stringArray.length;
}
```


    <div id="jotted-demo-3" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/09/01_array_print_03/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/01_array_print_03/01_array_print_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/01_array_print_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/09/01_array_print_03/) |


## Using Numbers

Please study the following example.

1. Notice that we create two arrays, which are assigned to parameters in an object.
2. The pointer index is also stored as a parameter in the same object.
3. Following the creation of the object, the length of one of the arrays is stored in another parameter within the object.
4. Finally, in the `draw()` loop, the object's parameters referencing arrays are utilized to determine the size and position of a circle on the canvas.

The following is very similar to the examples above using strings. However, in the following example, the arrays hole Number values, and the data is all packaged together in a single object.

```js
let circles = {
    diam: [ 20, 400, 150 ],
    pos: [ 40, 150, 250 ],
    idx: 0
};
circles.numCircles = circles.diam.length;

function setup() {
   createCanvas( windowWidth, 400 );
   frameRate( 1 );
}

function draw() {
    background( ‘rgb(30, 200, 120)’ );

    fill( ‘rgb(230, 30, 120)’ );
    ellipse(
        circles.pos[circles.idx],
        circles.pos[circles.idx],
        circles.diam[circles.idx]
    );

    circles.idx = ( circles.idx + 1 ) % circles.numCircles;
}
```


    <div id="jotted-demo-4" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-4"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/09/02_arrays_numbers_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/02_arrays_numbers_01/02_arrays_numbers_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/02_arrays_numbers_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/09/02_arrays_numbers_01/) |



## 2D Array Example

Look at the following code, in which we use a nested array to draw a star. Each of the 5 points of the star, are defined as arrays with two Numbers in each. These are used to draw lines, therefore, we get the array values by using the square bracket notation for nested arrays.

```js

// define locations of a star
let starArr = [
    [0, -9],
    [7, 9],
    [-9, -2],
    [9, -2],
    [-7, 9]
];
let idx = 0;

function setup() {
    createCanvas(windowWidth, 500);
    background(18, 82, 189);
    frameRate(2);
}

function draw() {

    translate( width/2, height/2 );

    // create a modulus wrapped plus-one idx
    let idxPlus = (idx + 1) % starArr.length;

    // grab the 2 points defining a line
    let x1 = starArr[idx][0] * 10;
    let y1 = starArr[idx][1] * 10;
    let x2 = starArr[idxPlus][0] * 10;
    let y2 = starArr[idxPlus][1] * 10;

    // draw the line
    strokeWeight(18);
    stroke(random(255), random(255), random(255), 150);
    line(x1, y1, x2, y2);

    // increment the idx
    idx = (idx + 1) % starArr.length;
}
```


    <div id="jotted-demo-5" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-5"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/09/06_2d_array_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/06_2d_array_01/06_2d_array_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/06_2d_array_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/09/06_2d_array_01/) |




# Shiffman's Take

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/VIQoUghHSxU" frameborder="0" allowfullscreen></iframe></div>
