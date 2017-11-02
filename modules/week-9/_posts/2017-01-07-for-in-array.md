---
title: For Element in Array
module: 9
jotted: false
---

# Looping Through Arrays

We have already seen one way of looping through arrays on the previous page using the `draw()` loop. However, there will clearly be times when we want to loop through an array using a _for loop_. Hopefully, through our work on the last page, you already have an idea as to how this will occur? 

Since we access elements in arrays using an index Number, the _for loop_ is a natural interface to to work through all of these elements. 

Let’s talk about how to work through the following array;

```js
let testArr = [ 20, 30, 80, 150, 162 ];
```

To setup our for loop, we first need to provide a variable initialization statement. Obviously since we want to work though all of the elements in the array, we will want to initialize a variable to the Number value `0`. Likewise, since we know this is a variable used to access index values, we should probably name it something that reminds us of that. Possible options are;

- `I`
- `idx`
- `index`

I personally like to use `idx` when creating variables for index retrieval. This means our initialization statement will look like;

```js
let idx = 0;
```

For the conditional statement, we know we want to grab all elements, sequentially. Since the last element in an array has an index value of 1 less than the length of the array, let’s check that index is less than the length of the array. (NOTE: We want to use _less than_ and **NOT** _less than or equal to_, as this would try and access an element one beyond what exists. This means our conditional statement will look like;

```js
idx < testArr.length;
```

Finally, since we want to grab each element, we can simply increment the `idx` variable by 1 every loop iteration;

```js
idx++
```

To use each element, we simply need to pass the value of `idx` to the array variable, and the _do something with it_.

Our final for loop might look like;

```js
for( let idx = 0; idx < testArr.length; idx++ ) {
	testArr[idx]; // <- do something
}
```

This test example might be used to draw a series of rectangles at various x positions every frame, like so;

```js
let xPosArr = [ 20, 30, 180, 250, 462 ];

function setup() {
    createCanvas( windowWidth, 400 );
}

let yPos = 0;
function draw() {
    background( ‘rgb( 200, 37, 52 )’ );
    
    stroke( 255 );
    fill( ‘rgb( 100, 255, 0 )’ );
    
    for( let idx = 0; idx < xPosArr.length; idx++ ) {
        // draw some boxes!
        rect( xPosArr[idx], yPos, 20, 40 ); 
    }
    
    yPos = (yPos + 1) % windowHeight;  
}
```

#### Another Example

Please study the following code to see the same principles in another example.

```js
let numberlist;

function setup() {
    createCanvas(600, 300);
    numberlist = [50, 20, 100, 25, 5, 75];

}

function draw() {
    background(0);
    fill(255);

    // Here is how you use a for loop to iterate 
    // over each element of the array
    for (let i = 0; i < numberlist.length; i++) {
        noFill();
        stroke(255);
        ellipse(i * 100 + 100, 100, numberlist[i], numberlist[i]);
    }

  // The above code is the same as below!
  // Just uses a loop where i changes dynamically instead
  // of hard-coded indices
  // ellipse(100, 100, numberlist[0], numberlist[0]);
  // ellipse(200, 100, numberlist[1], numberlist[1]);
  // ellipse(300, 100, numberlist[2], numberlist[2]);
  // ellipse(400, 100, numberlist[3], numberlist[3]);
  // ellipse(500, 100, numberlist[4], numberlist[4]);

}
```

# For In Loops

There is a convenience method in JavaScript to work through arrays known as 
