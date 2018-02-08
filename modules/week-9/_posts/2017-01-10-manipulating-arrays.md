---
title: Manipulating Arrays
module: 9
jotted: true
---

# Manipulating Arrays

In addition to creating pre-filled arrays, you will find many times where you need to dynamically manipulate the values stored within an array's elements. In this page, we will talk about some of the ways you can do that.

# Set an Array Element

In addition to being used to get the element stored, the square bracket notation can also be used to _set_ the values of a specific array element.

In the following, the element at index 2 is replaced with the String, `"Sue"`.

```js
let arrReplace = [ "orange", "banana", "grape", "strawberry" ];

arrReplace[2] // ← returns "grape"

arrReplace[2] = "Sue";
// the array -> [ "orange", "banana", "Sue", "strawberry" ]

arrReplace[2] // <- returns "Sue"
```

#### The Setter in Empty Arrays

You can also use the square bracket setter notation to add values to an empty array. For example, we can place an element at index 0 with;

```js
let myArr = []; // create an empty array

myArr[0] = "Harry";

// myArr -> [ "Harray" ]
```

You can use this same technique to add elements that are beyond the length of the current array. If we continued on our above example, and added "Sally" at index 4, then JavaScript will fill the remaining elements with `undefined`. **This will likely cause unforeseen errors with your code.**

```js
myArr[4] = "Sally";

// myArr -> [ "Harry", undefined, undefined, undefined, "Sally" ];

myArr[2] // returns 'undefined'
```


# Push

Another, perhaps safer, way of adding an element to an array is to use the array method _push_.

_push_, "pushes", or rather "appends" an element to the end of an array. This way, you do not have to keep track of the arrays current size yourself. To use this new function, add it to the array variable as a function, using the dot notation. Within it's parenthesis place the element you want to add as a parameter.

This would look like the following;

```js
exampleArray.push( ellementToAdd );
```

In practice, this function has the following effects;

```js
let exampleArray = [];
// array → [ ] (empty)
exampleArray.length // 0

exampleArray.push( 32 );
// array → [ 32 ]
exampleArray.length // 1

exampleArray.push( 2 );
// array → [ 32, 2 ]
exampleArray.length // 2

exampleArray.push( 88 );
// array → [ 32, 2, 88 ]
exampleArray.length // 3
```

#### In Use

Let's create an example, where we use this new array method.

1. First, we should create an empty array, that is scoped outside of `setup()` and `draw()`. I am going to have this array hold the sizes of circles. So let's also call it `circleSizes`.
```js
let circleSize = [];
```

2. In the `setup()` function, I want to randomly generate 10 numbers that will represent the size of each circle. We will do this using a for loop.
```js
for( let num=0; num<10; num++ ){
    // create and push in a new random number
    circleSize.push( random( 20, 200 ) );
}
```

3. Then we will use this new array to draw a series of circles in the `draw()` function.
```js
for( let idx=0; idx<circleSize.length; idx++ ){
    xpos = windowWidth / circleSize.length * idx + 30;
    circle( xpos, 100, circleSize[idx] );
}
```


Altogether, this might look like;

```js
let circleSize = [];

function setup() {
    createCanvas(windowWidth, 400);

    for( let num=0; num<10; num++ ){
        // create and push in a new random number
        circleSize.push( random( 20, 200 ) );
    }
}

function draw() {
    background( 'white' );
    stroke( 'rgb(177, 177, 177)' );
    fill('rgba(143, 255, 248, 0.6)');

    for( let idx=0; idx<circleSize.length; idx++ ){
        xpos = windowWidth / circleSize.length * idx + 30;
        ellipse( xpos, 100, circleSize[idx] );
    }
}
```


<div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/09/05_array_push_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/05_array_push_01/05_array_push_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/09/05_array_push_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/09/05_array_push_01/) |



> Think for a second: Why did the pushing of values into the array need to occur in the `setup()` function?
>
> Because if we did it in the `draw()` function, we would add 10 more random values to the array **every** frame.

# Splice

Now that we know how to _add_ elements to the array, we should figure out how also to remove them.

There are numerous ways to do this, but we are only going to study one for the moment, the _splice_ array method.

Just like _push_, _splice_ is appended to the end of an array. _splice_ takes a number of parameters as inputs; anywhere from 1 to 3. Depending on the number of input parameters, the _splice_ method performs differently. However, we will only be looking at the use of 2 parameters, allowing us to delete elements. If you would like to read more about the _splice_ method, please see its documentation page on Mozilla Developer Network.

- [`splice()` method documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

For our use, the 2 parameters will specify;

1. What position to start at in the array.
2. The number of elements to delete in the array.

Both of these input parameters should be integer Numbers.

The method works as follows;

```js
let testArray = [ "hat", "cat", "bat", "snow", "mat" ];

testArray.length // ← returns 5

// remove "snow"
// snow is at index 3
// and we only want to remove 1 element
testArray.splice(3, 1);

testArray.length // ← returns 4
testArray // [ "hat", "cat", "bat", "mat" ];

// remove "cat" & "bat"
// "cat" is at index 1
// and we want to remove 2 elements
testArray.splice(1, 2);

testArray.length // ← returns 2
testArray // [ "hat", "mat" ];
```



## { TODO: }

Please read the following on arrays, for more info about the possible uses of arrays in JavaScript;

- [Arrays in JavaScript - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
