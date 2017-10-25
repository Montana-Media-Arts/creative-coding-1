---
title: Nested for Loops
module: 7
jotted: true
---

# Nested for Loops

Building from the last page, how could you use a for loop to _do something_ across both axis of the entire screen? I.E. I’m every row and every column? Essentially touching the entire grid? 

The _brute force_ way, would be to write a for loop that does something across the X-axis. Like the following, which currently draws a line of circles across the X-axis;

```js
function setup() {
	createCanvas( windowWidth, 400);
	noStroke();
}

function draw() {
	let numPerRow = 10;
	let circleSize = 50;
	let pad = width / numPerRow;
	let y = circleSize;
	
	background(0);
	
	for ( let x = circleSize; x < width; x += pad) {
		fill( 255, 140, random(255) );
		ellipse( x, y, circleSize, circleSize );
	}
}
```

<br />

Then to add another row, below the first, we could simply, copy, paste, and update where the Y-axis position will be.

```js
function setup() {
	createCanvas( windowWidth, 400);
	noStroke();
}

function draw() {
	let numPerRow = 10;
	let circleSize = 50;
	let pad = width / numPerRow;
	// set an initial ‘y’
	let y = circleSize;
	
	background(0);
	
	for ( let x = circleSize; x < width; x += pad) {
		fill( 255, 140, random(255) );
		ellipse( x, y, circleSize, circleSize );
	}
	
	y += pad;
	for ( let x = circleSize; x < width; x += pad) {
		fill( 255, 140, random(255) );
		ellipse( x, y, circleSize, circleSize );
	}
}
```

<br />

This, of course, raises the same issues, and inefficiencies discussed back on the first page of this weeks content. Specifically, that this is fine for a small number of iterations. But is impractical for larger numbers. It also suffers from the problem of being easily editable. (If you want to change one thing, you must do so every place that it occurs.)

Obviously, instead, we should create some sort of looped process to automate the task...

**LIKE A FOR LOOP!**

The eloquent solution is to create a _for loop_ that handles the movement of the for loop drawing circles across rows on the X-axis. This additional for loop will cause the X-axis for loop to move down every iteration, thereby drawing a new row. 

The code for this, migh look something like the following;

```js
function draw() {
	let numPerRow = 10;
	let circleSize = 50;
	let pad = width / numPerRow;

	background(0);
	
	// outer for loop - Y-Loop
	for ( let y = circleSize; y < height; y += pad) {
	
		inner for loop - X-Loop
		for ( let x = circleSize; x < width; x += pad) {
			fill( 255, 140, random(255) );
			ellipse( x, y, circleSize, circleSize );
		}
		
	}
}
```

With 2 additional lines of code, it become possible to execute any number of X-axis based for loops. 

The _outer for loop_ essentially handles specifying the Y-pos. You will notice that this outer for lop defines and uses the Number variable `y`, which is passed as “y” parameter to the ellipse function. 

As before in the above examples, the _inner for loop_ handles the placement of circles along the X-axis. 

<br />

For the moment, lets assume that the variable `pad` is set to 100. 

In this scenario, the _outer for loop - Y-Loop_, is initialized such that `y=50` (or the circleSize variable’s value). This for loop then executes the contents of its _function block_. This of course contains the _inner for loop - X-Loop_. 

This _inner for loop - X-Loop_ initializes the variable `x` to the value of 50, or `circleSize`. Since this is less than `width`, it executes its _function block_ contents. Which create a random color and draws a circle, positioned at the values of `x` and `y` or (x:50, y:50). 

Upon completion of thi process, the _inner for loop - X-Loop_ then updates its variable value by adding 100 to `x`, or the value of `pad`. The _inner for loop - X-Loop_ then checks whether this is less than `width`. Since it is, the _inner for loop - X-Loop_ executes its function block again. This time drawing a circle at (x:150, y:50). For a window that is 300px wide, this process would occur one more time, drawing a circle at (x:250, y:50). After the execution and drawing of this circle, the _update statement_ would set `x` to 350. The _conditional statement_ would return false, meaning `x` is greater than `width`. In this case, the _inner for loop - X-Loop_ exits. 

Since the _inner for loop - X-Loop_ is wrapped in the _outer for loop - Y-Loop_, this for loop then has to check its state and values. At the end of execution of the _inner for loop_, the _outer for loop - Y-Loop_ executes its _update statement_ thereby setting `y` tp 150. Assuming a canvas with a height of 200, the _conditional statement_ would return `true` that `y` is less than `height`. In which case, the _outer for loop - Y-Loop_ would execute its function block again. This would result in the _inner for loop - X-Loop_ executing again, as though it had not before. The variable `x` will be re-initialized and defined to the value of `circleSize` or 50. It will therefor execute 3 times again, drawing circles at; 

- (x:50, y:150)
- (x:150, y:150)
- (x:250, y:150)

Afterwards, the _inner for loop_ would exit again, return control to the _outer for loop_ again. This would continue until the `y` value is greater than `height`, thereby triggering the _outer for loop_ to exit. 


# More Examples

Please look at the following examples from “Make: Getting started with p5”. Notice how with slight modifications, quite interesting patterns can be achieved.


### Example 1 of more nested for loops

```js
function setup() {
	createCanvas(480, 120);
}

function draw() {
	background(0);
	for (var y = 32; y <= height; y += 8) {
		for (var x = 12; x <= width; x += 15) {
			ellipse(x + y, y, 16 - y/10.0, 16 - y/10.0);
		}
	}
}
```

### Example 2 of more nested for loops

```js
function setup() {
	createCanvas(600, 200);
}

function draw() {
	background(0);
	for (let y = 0; y <= height; y += 10) {
		for (let x = 0; x <= width; x += 10) {
			let d = y/10;
			ellipse(x + y, y, d, d);
		}
	}
}
```


### Example 3, Crazy Options

NOTE: Click with your mouse on the next example.

```js
// FORM+CODE
// Casey Reas and Chandler McWilliams

var option = 5;
function setup() {
  createCanvas(windowWidth, windowHeight);
  noFill();
}

function draw() {
  background(255);
  var density = map(mouseX, 0, width, 20, 50);

  if (option == 1) {
    // Option 1: Stitches
    for (var x = 50; x <= width-50; x += density) {
      for (var y = 50; y <= height-50; y+=density) {
        line(x-5, y-5, x+5, y+5);
        line(x+5, y-5, x-5, y+5);
      }
    }
  }
  else if (option == 2) {
    // Option 2: Perspective
    for (var x = 50; x <= width-50; x += density) {
      for (var y = 50; y <= height-50; y+=density) {
        line(x, y, width/2, height/2);
      }
    }
  }
  else if (option == 3) {
    // Option 3: Overlapping circles
    for (var x = 50; x <= width-50; x += density) {
      for (var y = 50; y <= height-50; y+=density) {
        ellipse(x, y, 40, 40);
      }
    }
  }
  else if (option == 4) {
    // Option 4: Rotating arcs
    var count = 120;
    for (var x = 50; x <= width-50; x += density) {
      for (var y = 50; y <= height-50; y+=density) {
        var s = map(count, 120, 0, 0, TWO_PI*2);
        arc(x, y, 14, 14, s, s + PI);
        count--;
      }
    }
  }
  else if (option == 5) {
    // Option 5: Groups of five
    for (var x = 50; x < width-50; x += density) {
      for (var y = 50; y < height-50; y+=density) {
        //rect(x-10, y-10, 22, 22);
        for (var i = 0; i < 16; i+=4) {
          line(x + i, y, x + i, y + 12);
        }
        line(x, y, x + 12, y + 12);
      }
    }
  }
}

function mousePressed() {
  option++;
  if (option > 5) option = 1;
}
```