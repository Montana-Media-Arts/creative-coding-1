---
title: Classes and Objects Example
module: 11
jotted: true
---

# An Example using Classes and Objects

Let's finish out the Ball class example so that you can see all of this in use.

## Define a Class

First, we need to write our class. We know we want this class to be a digital representation of a "ball", so let's label it as such. This means, our class initially will look like the following;

```js
class Ball {
    constructor() {

    }
}
```

## Consider Object Properties

I would argue the next step is to consider what type of properties a "ball object" needs to exist in our digital world. To do this, we need to define the ball's behavior.

Let's for the purposes of this experience, say this ball will;

- have a solid color
- and be of a random size.

This ball will also;

- travel on straight line
- when it hits a wall, it will bounce, traveling at a mirror angle.

These spec's can help us determine the properties the ball will need. We can say that the ball will likely need;

- a color property
- a radius, to describe it size
- a set of position values (X and Y)
- a set of delta values to describe the movement of the ball (deltaX and deltaY)

From this, lets assume we will set the delta value randomly within the constructor method, and will pass the color, size, and position properties to the ball when a new one is created. Finally, as we will see below, we will need to easily access both the radius and diameter of the ball. So, let's calculate the radius of the ball from the diameter/size, and store that in a dedicated property.

This might result in the following constructor method;

```js
class Ball {
    constructor( x, y, size, color ) {
        this.color = color;
        this.size = size;
        this.rad = this.size / 2;
        this.posX = x;
        this.posY = y;
        this.deltaX = random(-2, 2);
        this.deltaY = random(-2, 2);
    }
}
```

## Consider Object Methods

The next step might be to start writing the methods objects of this class may need. Since we are trying to write modular, highly-readable code, we want to try and write methods that do individual, well defined tasks. With that in mind, we can start to describe the following characteristic of balls that we need;

- The ball needs to be drawn on the canvas every frame.
- The ball needs to move every frame
- The ball needs to check if it has hit a wall, in which case, its direction needs to change.

With this in mind, lets write three methods, one for each of the characteristic described above.

#### Display

The first of these we may want to write is the method to display the ball. We need to be careful not to overwrite functions or other keywords reserved by p5 or JavaScript. So, since p5 uses the function `draw()` as part of its core, let's call our method `display()` to separate it.

In this method, we need to grab the ball's size, color, and position properties, so that it can be drawn at the specified position, with a specific size and color. The rest of the method will follow p5 code conventions.

```js
display() {
    push();
    // remove the balls outer stroke
    noStroke();
    // set the balls fill color
    fill( this.color );
    // set the position of the ball
    translate( this.posX, this.posY );
    ellipse( 0, 0, this.size );
    pop();
}
```

#### Move the Ball

To move the ball, we are going to write a method like we did on the previous page. This method will grab the X and Y position properties, respectively. It will then add the X and Y delta values to each, and reassign the new value back to the X and Y position properties.

```js
move() {
    this.posX += this.deltaX;
    this.posY += this.deltaY;
}
```

#### Edge Check

The final method to write is an edge check that will see if the ball is hit a wall. If it does, this method needs to adjust the angle of the ball to bounce at the mirror angle. To accomplish this, we can set the delta value of the corresponding axis to its "negative" self. To do this we will multiply by `-1`.

In order to know if the ball has hit a wall, we will also need to use some conditional logic to check the position of the ball in relation to the canvas window. Also, let's use the edge of the ball, and not it's center. To do this, we need to add the radius of the ball to the pos values, so that we can accurately calculate the edge of the ball.

```js
edgeCheck() {
    // check if the ball has hit a vertical wall (left or right walls)
    if( this.posX + this.rad >= width || this.posX - this.rad <= 0 ) {
        this.deltaX *= -1;
    }
    // check if the ball has hit a horizontal wall (top or bottom walls)
    if( this.posY + this.rad >= height || this.posY - this.rad <= 0 ) {
        this.deltaY *= -1;
    }
}
```

#### Altogether

Altogether, the class definition might look like;


{% highlight js linenos %}
class Ball {
    constructor( x, y, size, color ) {
        this.color = color;
        this.size = size;
        this.rad = this.size / 2;
        this.posX = x;
        this.posY = y;
        this.deltaX = random(-2, 2);
        this.deltaY = random(-2, 2);
    }

    display() {
        push();
        // remove the balls outer stroke
        noStroke();
        // set the balls fill color
        fill( this.color );
        // set the position of the ball
        translate( this.posX, this.posY );
        ellipse( 0, 0, this.size );
        pop();
    }

    move() {
        this.posX += this.deltaX;
        this.posY += this.deltaY;
    }

    edgeCheck() {
        // check if the ball has hit a vertical wall (left or right walls)
        if( this.posX + this.rad >= width || this.posX - this.rad <= 0 ) {
            this.deltaX *= -1;
        }
        // check if the ball has hit a horizontal wall (top or bottom walls)
        if( this.posY + this.rad >= height || this.posY - this.rad <= 0 ) {
            this.deltaY *= -1;
        }
    }
}
{% endhighlight %}

# Creating and Using a Ball Object

To create and use a Ball object in a p5 sketch, we will need to;

- create a variable namespace to store a reference to the object in
- create a new object and store it in the variable namespace
- call the objects methods every frame to update position, and draw the object

One common issue is that beginning programmers will try to create objects in the `draw()` loop. This causes problems, because we then create anew object every frame, rather than creating one instance, that we can then update and reference.

#### Create a Variable Namespace

The first thing, according to our list above, is to create a variable to store a reference to the object in. We will do this outside of either `setup()` or `draw()` so that it is accessible in both p5 functions.

```js
let ball;
```

#### Create a New Ball Object

Next, we will create a new Ball object inside the `setup()` function, and then assign a reference to this new object in our variable `ball`. Also, since we have four parameters that we need to pass to the Ball's constructor function, we will need to remember those when we create a new ball object. Again these are; `x` and `y` position, `size`, and `color`.

```js
function setup(){
    // createCanvas( windowWidth, windowHeight );
    createCanvas( windowWidth, 600 );

    // create a new ball object of class type "Ball"
    ball = new Ball( width/2, height/2, 50, 'red' );
}
```

#### Call the Ball's Methods

Finally, in order to use our new Ball object, we need to call the relevant ball object methods every frame. To do this, we can place them in the `draw()` function loop.

```js
function draw() {
    background(0);

    // call the ball's methods
    ball.display();
    ball.move();
    ball.edgeCheck();
}
```
> Look how simple and clean that code above looks! It is so easy to read and understand. By abstracting the ball into a class, we can create a ball object, that we call simple instructions on. Each one makes sense and is readable!


## Where do you Place the Class Definition?

One thing we have not discussed yet, is where the class definition gets placed. For simple classes like the one we just wrote, these can be placed at the bottom of your `sketch.js` file. These will then get loaded and hoisted by the JavaScript engine, and will be available for use throughout your code.

## Final Example

The final code, following what we have described above, might look like the following;

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
// Ball Class Example
// Week 11


// create a variable for the ball object
let ball;

function setup() {
    createCanvas(windowWidth, windowHeight);

    // create a new ball object of class type "Ball"
    ball = new Ball(width / 2, height / 2, 50, 'red');
}

function draw() {
    background(0);

    // call the ball's methods
    ball.display();
    ball.move();
    ball.edgeCheck();
}


//////////////////////////////////////////////////
//      BALL CLASS DEFINITION
//////////////////////////////////////////////////
class Ball {
    constructor(x, y, size, color) {
        this.color = color;
        this.size = size;
        this.rad = this.size / 2;
        this.posX = x;
        this.posY = y;
        this.deltaX = random(-2, 2);
        this.deltaY = random(-2, 2);
    }

    display() {
        push();
        // remove the balls outer stroke
        noStroke();
        // set the balls fill color
        fill(this.color);
        // set the position of the ball
        translate(this.posX, this.posY);
        ellipse(0, 0, this.size);
        pop();
    }

    move() {
        this.posX += this.deltaX;
        this.posY += this.deltaY;
    }

    edgeCheck() {
        // check if the ball has hit a vertical wall (left or right walls)
        if (this.posX + this.rad >= width || this.posX - this.rad <= 0) {
            this.deltaX *= -1;
        }
        // check if the ball has hit a horizontal wall (top or bottom walls)
        if (this.posY + this.rad >= height || this.posY - this.rad <= 0) {
            this.deltaY *= -1;
        }
    }
}
{% endhighlight %}


<div id="jotted-demo-1" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/11/01_ball_class_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/01_ball_class_01/01_ball_class_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/01_ball_class_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/11/01_ball_class_01/) |
