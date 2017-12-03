---
title: Objects Interacting w/ Each Other
module: 12
jotted: true
---

# Objects Interacting with Each Other

The next challenge to solve this week is;

- How do we make objects aware of each other?
- And how do we make objects interact with each other?

The basic technique if rather simple, to get an object to interact with, or rather have awareness about other objects in a sketch, that object needs to be given information about the _other objects_.

## Making it Happen

To work through how to do this, we are going to start with a slightly modified version of the bouncing ball code from the previous week. It has been modified to have an array of bouncing balls.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
// create a variable for the ball object
let balls = [];
const numOfBalls = 20;

function setup() {
    createCanvas(windowWidth, windowHeight);

    // create a new ball object of class type "Ball"
    let init_x = 60;
    let init_y = 60;
    for ( let i = 0; i < numOfBalls; i++ ) {
        balls.push( new Ball( init_x, init_y ) );
        // move the starting position over
        // This is to ensure that the balls do not start
        // "on top" of each other
        init_x += 100;
        if( init_x > width ) {
            init_x = 60;
            init_y += 100;
        }
    }
}

function draw() {
    background( 'rgb(66, 57, 66)' );

    for ( let ball of balls) {
        // call the ball's methods
        ball.display();
        ball.move();
        ball.edgeCheck();
    }
}






//////////////////////////////////////////////////
//      BALL CLASS DEFINITION
//////////////////////////////////////////////////
class Ball {
    constructor(x, y, size) {
        this.color = 'red';
        this.size = random(20, 80);
        this.rad = this.size / 2;
        this.posX = x;
        this.posY = y;
        this.deltaX = random(-10, 10);
        this.deltaY = random(-10, 10);
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
            this.color = 'rgb(110, 240, 158)';
        }
        // check if the ball has hit a horizontal wall (top or bottom walls)
        if (this.posY + this.rad >= height || this.posY - this.rad <= 0) {
            this.deltaY *= -1;
            this.color = 'rgb(110, 240, 158)';
        }
    }
}

{% endhighlight %}

<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class="" style="height:600px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/12/03_objects_w_objects_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/12/03_objects_w_objects_01/03_objects_w_objects_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/12/03_objects_w_objects_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/12/03_objects_w_objects_01/) |
