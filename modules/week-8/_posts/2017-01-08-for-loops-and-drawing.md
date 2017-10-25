–––
title: For Loops and Drawing
module: 8
jotted: true
–––

# For Loops and Drawing

A very common use of _for loops_ is to _do something_ from one place on a screen, to another place on a screen. For example, you may find yourself wanting to do something, or rather the same things, from the left area of a canvas (`x=0`), to the right edge of a canvas (`x=width`). 

In this situation, you will likely setup your _for loop_ such that;

1. the variable declaration’s name is meaningful to task at hand. If you are working across the x-axis, `x` may be the most suitable. 
2. You will want to initialize this value to the left-edge of the area where you want something to occur. 
3. The condition check statement should cause the loop to terminate once it _reaches_ the righ-edge of the desired area. Again, if you were working from left-edge to right-edge of a canvas in p5, this likely would be some sort of conditional, checking whether the variable is at or past the canvas’ `width` ( `x < width` ).
4. Finally, for the _update statement_, this should cause the variable’s update to reflect the movement across the screen that you are trying to accomplish. Let’s say you wanted to draw circles across the screen’s x-axis, starting at `x=0` and terminating at `x=width`. You would obviously set up the _for loop_ so that it started at 0 and ended at `width`. The _update statement_ will be dependent on the desired size and spacing of th circles. For example, if we want circles with a width of 50px, that touch, then our update value will likely need to be `x+=50`.

This example is shown in one possible solution below, with the description for the circles applied to both the x-axis and y-axis. 

```js
function setup() {
	createCanvas(600, 400);
	noStroke();
}

function draw() {
	background(0);
	for (let y = 0; y < height+25; y += 50) {
		fill(255, 140);
		ellipse(0, y, 50, 50);
	}
	for (let x = 0; x < width+25; x += 50) {
		fill(255, 140);
		ellipse(x, 0, 50, 50);
	}
}
```


## Drawing A Diagnol Series

What if you wanted to draw a diagnol series on a canvas that what not square? The problem is obviously that we cannot use the same variable to describe the position of an object on for both the same x-axis and y-axis. 

The following example utilizes the properties we have been talking about, applied to the problem of drawing a diagnol line of objects across a screen of indeterminate length. 

```js
function setup() {
	createCanvas( windowWidth, 400 );
	background( 200, 0, 40 );
}



function draw() {
	// establish scoped variables 
	let padding = 20;
	let size = 20;
	let num_of_objs = 30;
	// to determine spacing, 
	// first determine the amount available space
	// then devide by one less than the desired number of objects
	let x_spacing = (width-padding*2) / (num_of_objs-1);
	let y_spacing = (height-padding*2) / (num_of_objs-1);
	
	rectMode( CENTER );
	for( let i=0; i < num_of_objs; i++ ) {
		rect( 
			// to determine spacing;
			// multiply the iterator (i) by the spacing. 
			// add padding to offset from (x:0, y:0)
			i*x_spacing+padding, 
			i*y_spacing+padding, 
			size, 
			size 
		);
	}
}
```