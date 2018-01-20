---
title: Array of Objects
module: 11
jotted: true
---

# An Array of Objects

Now that we can think in terms of objects, let's look at using an array to manage a large number of objects.

Arrays, as you already know, can hold any collections of any data type. Which means they can also hold a collection of objects!

If an array is just a collection of objects, we can address each array element as the object variable.

## Creating an Array of Objects

To create an array of objects, we simply need a loop in our `setup()` function that will _push_, _n_ number of objects into the array. This might look like;

```js
let dudes = [];
let num_of_dudes = 20;
let bg_color;

function setup() {
    createCanvas(windowWidth, windowHeight);
    bg_color = color(34, 131, 157);

    for (let i = 0; i < num_of_dudes; i++) {
        dudes.push( new MarchingDude() );
    }
}
```

Since the class handles all of the "nitty-gritty" during the construction of new objects, we simply need to use the `new` keyword and pass the new object into the array.

## Calling Objects

As you will see in the code below, the class we are using for this example has three methods that need to be executed every frame. However, in the class definition, there is an additional method, called `.frame()`. This method calls the other methods.

To call a method from within an object, use _this dot_ notation! (i.e. `this.someMethod()`);

In the class definition, the `frame()` method looks like;

```js
frame() {
    this.feetAngle();
    this.display();
    this.move();
}
```

Then, in the `sketch.js` file, the `draw()` function simply needs to call the `.frame()` method for every object. To do this, simply use a for loop to work through the array.

```js
function draw() {
    background(bg_color);

    for (var i = 0; i < dudes.length; i++) {
        dudes[i].frame();
    }
}
```

## Altogether

The final code and example looks like;

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
let dudes = [];
let num_of_dudes = 20;
let bg_color;

function setup() {
    createCanvas(windowWidth, windowHeight);
    bg_color = color(34, 131, 157);

    for (let i = 0; i < num_of_dudes; i++) {
        dudes.push( new MarchingDude() );
    }
}

function draw() {
    background(bg_color);

    for (var i = 0; i < dudes.length; i++) {
        dudes[i].frame();
    }
}





/////////////////////////////////////////
//      Marching Dude Class
/////////////////////////////////////////

/**
 * MarchingDude Class. Creates creepy marching things.
 *
 */
class MarchingDude {

    constructor() {
        this.size_w = random(20, 80);
        this.size_h = random(20, 80);
        this.loc_x = random(width);
        this.loc_y = random(height);
        this.move_x = random(-2, 2);
        this.move_y = random(-2, 2);
        this.body_color = color(random(255), random(255), random(255));
        this.size_w = this.size_w;
        this.size_h = this.size_h;
        this.eye_x = this.size_w * 0.165;
        this.eye_y = this.size_h * 0.33 * -1;
        this.eye_size = this.size_w * 0.25;
        this.feet_x = this.size_w * 0.25 + (this.size_w * 0.25);
        this.feet_y = this.size_h * 0.5;
        this.feet_w = this.size_w * 0.75;
        this.feet_h = this.size_h * 0.4;
        this.left_foot_angle = 0;
        this.right_foot_angle = 0;
        this.foot_angle_delta = random(3);
        this.foot_angle_max = -20;
        this.active_foot = 0;
    }

    // call this method once per frame to update marching dude
    frame() {
        this.feetAngle();
        this.display();
        this.move();
    }

    display() {

        push();

        translate(this.loc_x, this.loc_y);
        fill(this.body_color);

        ellipse(0, 0, this.size_w, this.size_h);

        // eyes
        fill(255);
        ellipse(-this.eye_x, this.eye_y, this.eye_size, this.eye_size);
        ellipse(this.eye_x, this.eye_y, this.eye_size, this.eye_size);

        // feet
        push();
        rotate(PI * (this.right_foot_angle * 0.01));
        translate(this.feet_x, this.feet_y);
        scale(1, -1);
        arc(0, 0, this.feet_w, this.feet_h, 0, -PI, CHORD);
        pop();
        push();
        rotate(PI * -(this.left_foot_angle * 0.01));
        translate(-this.feet_x, this.feet_y);
        scale(-1, -1);
        arc(0, 0, this.feet_w, this.feet_h, 0, -PI, CHORD);
        pop();

        pop();
    }

    feetAngle() {

        if (this.active_foot === 0) {
            this.left_foot_angle -= this.foot_angle_delta;
            if (this.left_foot_angle <= this.foot_angle_max) {
                this.foot_angle_delta *= -1;
            }
            if (this.left_foot_angle >= 0) {
                this.active_foot = 1;
                this.foot_angle_delta *= -1;
            }
        } else if (this.active_foot === 1) {
            this.right_foot_angle -= this.foot_angle_delta;
            if (this.right_foot_angle <= this.foot_angle_max) {
                this.foot_angle_delta *= -1;
            }
            if (this.right_foot_angle >= 0) {
                this.active_foot = 0;
                this.foot_angle_delta *= -1;
            }
        }

        // console.log(this.left_foot_angle);
    }

    move() {
        this.loc_x += this.move_x;
        this.loc_y += this.move_y;

        if (this.loc_x >= width) {
            this.move_x *= -1;
            this.loc_x = width - abs(this.move_x);
        } else if (this.loc_x <= 0) {
            this.move_x *= -1;
            this.loc_x = abs(this.move_x);
        } else if (this.loc_y >= height) {
            this.move_y *= -1;
            this.loc_y = height - abs(this.move_y);
        } else if (this.loc_y <= 0) {
            this.move_y *= -1;
            this.loc_y = abs(this.move_y);
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
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/11/02_dudes_array_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/02_dudes_array_01/02_dudes_array_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/02_dudes_array_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/11/02_dudes_array_01/) |


# Shiffman on Arrays of Objects

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/fBqaA7zRO58" frameborder="0" allowfullscreen></iframe></div>

The code from Shiffman's example is below;

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
let bubbles = [];

function setup() {
    createCanvas(windowWidth, 400);
    let b = new Bubble(width/2, height/2, 10);
    bubbles.push(b);
}

function mouseDragged() {
    let r = random(10, 50);
    let b = new Bubble(mouseX, mouseY, r);
    bubbles.push(b);
}

function draw() {
    background(0);
    for (let i = 0; i < bubbles.length; i++) {
        bubbles[i].move();
        bubbles[i].show();
    }
}

class Bubble {
    constructor(x, y, r) {
        this.x = x;
        this.y = y;
        this.r = r;
    }

    move() {
        this.x = this.x + random(-5, 5);
        this.y = this.y + random(-5, 5);
    }

    show() {
        stroke(255);
        strokeWeight(4);
        noFill();
        ellipse(this.x, this.y, this.r * 2);
    }
}
{% endhighlight %}



<div class="displayed_jotted_example">
    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/11/03_shiffman_bubbles_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/03_shiffman_bubbles_01/03_shiffman_bubbles_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/03_shiffman_bubbles_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/11/03_shiffman_bubbles_01/) |
