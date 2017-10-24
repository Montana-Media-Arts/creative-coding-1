---
title: More for loops
module: 8
jotted: true
---

# More for loops

Let's look at some more examples of using _for loops_. 


## Update Statement

The _update statement_ portion of _for loops_ creates lots of flexibility for how data, and the progression of the for loop can occur. 

So far, we have only discussed and seen this statement utilize the _increment by 1_ syntax (i.e `i++`). But, any statement that returns a new value for the defined variabemay be used. This might include any of the following;

```js
i++;
i--;
i+=2;
i-=2;
i = (i ** 10) / 3;
```

As long as the _update statement_ returns a valid Number, then anything can be used. NOTE: The only thing to be wary of is that the _update statement_ moves the Number variable towards completion of the loop. Be cautious of _update statements_ that cause an infinite loop. That is, statements that do not move the Number variable towards completion of the _for loop_.  For example, the following would cause a silent problem, as the Number variable is _decreasing_ in the _update statement_, but the _conditional statement_ will only cause an exit once the Numbver variable is greater than 10.

```js
for( var i=5; i < 10; i-- ) {
	// do something
	// never exits this loop
}
```

<br />

On the other hand, the following example increments by 60 every loop, until `i` is greater than 400. Notice how the diagnol lines are each 60 pixels apart?  This is because of the _update statements_ use of increment by 60. 

**{ TODO: }** Change the _update statements_ value from 60 to some other values to see how the sketch changes. 

```js
function setup() {
  createCanvas(600, 400);
  strokeWeight(8);
}

function draw() {
  background(200);
  // try changing "60" to other numbers
  for (let i = 20; i < 400; i += 60) { 
    line(i, 40, i + 60, 80);
  }
}

// above is equivalent to

// function draw() {
//   line(20, 40, 80, 80);
//   line(80, 40, 140, 80);
//   line(140, 40, 200, 80);
//   line(200, 40, 260, 80);
//   line(260, 40, 320, 80);
//   line(320, 40, 380, 80);
//   line(380, 40, 440, 80);
// }
```

## Number Variable Declaration 

The first statement of a _for loop_ is the _Number variable declaration and initialization_. As mentioned on the previous page, this tells the _for loop_ what variable to use and what it is initially set to. 



```js
function setup() {
	createCanvas(480, 240);
	strokeWeight(2);
}

function draw() {
	background(200);
	for (let i = 20; i < 400; i += 20) {
		line(i, 0, 1.5*i, 120);
	}
}
```