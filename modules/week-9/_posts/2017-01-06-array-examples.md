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
	2. and a prefilled array.
2. The printing of both of these arrays as strings, using the p5 `text()` function.

```js
// create an empty array
var emptyArray = [];

// create a filled, array
// in this case, we have placed in integers
var numArray = [2, 4, 9, 100];


function setup() {
    createCanvas(windowWidth,400);
    bg_color = color(230, 240, 200);
    background(bg_color);
}

function draw() {
    textSize(56);
    // print the arrays to the screen
    text(“emptyArray: “ + emptyArray, 20, 80);
    text(“numArray: “ + numArray, 20, 200);
}
```

<!— place jotted here —>

Notice how the elements of the `numArray` are printed. Also notice, since the `emptyArray` is empty, nothing is printed. 


#### To access a single element

To print only a single element from an array, we access it using its index number. The following example;

1. Creates an array filled with strings
2. Prints out the entire array.
3. Prints out only the first element from the array.

```js
// create a filled array
// This array has strings in its elements
var stringArray = [“Ha”, “JS”, “:)”]


function setup() {
    createCanvas(windowWidth,400);
    bg_color = color(230, 240, 200);
    background(bg_color);
}

function draw() {
    textSize(56);
    // print the arrays to the screen
    text(“stringArray: “ + stringArray, 20, 80);
    text(“The first element in the array is: “ + stringArray[0], 20, 200);
}
```

Notice in the last line of code that `stringArray[0]` is used to return only the string `”Ha”`.


#### To rotate through elements

Now, let’s write a sketch that will print out a single element from the array. This sketch will also rotate through the elements, printing the _next_ element every frame. 

To do this, we will need to do a couple of things;

1. Instead of directly passing an Number as the index value to the array, we will instead need to pass a variable, referencing a Number value representing the desired index value. We will use the variable `idx`, which is often used as a shorthand for “index”.
2. The value of this index variable will need to be incremented every frame. (`idx++`).
3. Finally, in order to prevent an error by tryng to access an element that does not exist, we will need to wrap our incrementing index variable in the length of the array. We can do this suing the modulo operator (`%`), along with the length of the array (i.e. `stringArray.length`).

The following code implements the steps we just discussed. 

```js

var stringArray = [“Ha”, “JS”, “:)”, “arrays are fun”, “p5 is AWESOME!!”];

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

    text(“The index value is: “ + idx, 20, 80);
    text(“The element is: “ + stringArray[idx], 20, 200);
    
    // increment the idx variable
    // also make sure it stays within the bounds of the array
    idx = ( idx + 1 ) % stringArray.length;
}
```

## Using Numbers

Please study the following example. 

1. Notice that we create two arrays, which are assigned to parameters in an object.  
2. The pointer index is also stored as a parameter in the same object. 
3. Following the creation of the object, the length of one of the arrays is stored in another parameter within the object.
4. Finally, in the `draw()` loop, the object's parameters referencing arrays are ustilized to determine the size and position of a circle on the canvas. 

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