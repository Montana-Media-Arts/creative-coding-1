---
title: Simple Math
module: 5
jotted: true
---

# Simple Math & Animation

In addition to storing static values in variables that will get used throughout a code sketch, another use of variables is to store the results of mathematical calculations, for use later in your code.

We have already seen the use of the p5 variables `mouseX` and `mouseY` to animate a p5 sketch. But what if you wanted to create generative code, that will cause a sketch to appear and form over time?

The answer of course, is the use of variables to hold the output of mathematical calculations.

We will get into math more deeply next week, for this week, I will assume you understand how addition/subtraction, and multiplication/division work.

> You are going to get good at math again! I promise.

## Assign Results from Calculations to Variables

To assign the results of a mathematical calculation to a variable, you simply need to use the assignment operator (i.e. the equals sign, `=`) with the calculation.

For example, the following assigns the result of `2 + 2` to the variable, `four`;

```js
var four = 2 + 2;
```

> The above would be said as; "The variable four _gets_ the result of two plus two."

This is obviously quite boring, and superfluous, as we know that `2 + 2` equals `4`. However, there may come a time when you have many variables in relation to each other, where a change in one, needs to be propagated throughout the system. In such a system, you may have multiple variables, that are each used in the calculations.

<br />


In the following example, we declare and assign an initial variable `smileySize`. From this, all other aspects of the smiley face's shape and size are calculated. If this first variable (`smileySize`) is changed (which you should do in the example code below), then the rest of the sketch adjusts. This occurs since the rest of the variables are based off this initial size variable.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
// initial variable. Defines smiley face size.
var smileySize = 100;

// all other variables are determined in
// relation to the smileySize variable.
var eyePos_X = smileySize * 0.2;
var eyePos_Y = smileySize * -0.15;
var eyeSize = smileySize * 0.2;
var smilePos_Y = smileySize * 0.15;
var smileWidth = smileySize * 0.75;
var smileHeight = smileySize * 0.50;


function setup() {
    createCanvas( windowWidth, windowHeight );
    background( 'rgb(61, 175, 120)' );
}


function draw() {

    // ** draw the smily face **

    // make the smiley face follow the mouse
    translate( mouseX, mouseY );

    // draw the outline and head
    stroke( 0 );
    fill('rgba(234, 255, 61, 0.5)');
    // note: the head size is based on a variable
    ellipse( 0, 0, smileySize );

    // draw the mouth and eyes
    // note: that their size and position is dependent on the initial smileySize var.
    noStroke();
    fill( 40, 127 );
    arc( 0, smilePos_Y, smileWidth, smileHeight, 0, PI );
    ellipse( -eyePos_X, eyePos_Y, eyeSize );
    ellipse( eyePos_X, eyePos_Y, eyeSize );
}
{% endhighlight %}


    <div id="jotted-demo-1" class="" style="height:600px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/08_related_vars_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/08_related_vars_01/08_related_vars_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/08_related_vars_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/08_related_vars_01/) |


## In Practice, in order to Animate

These same principles can be applied to animation. This will allow us to work towards our generative art sketch.


<br />

As an example, let's define two variables globally, which will store position data.

```js
var posX = 0;
var posY = 0;
```

Then, inside of the `draw()` function loop, let's use them to represent the position parameters for an ellipse function.

After that, we will add `1` to each variable, and then re-assign that result _BACK_ to the variable.

```js
function draw() {
    ellipse( posX, posY, 30, 30 );

    // update posX & posY every frame
    // add 1, then re-assign back to self
    posX = posX + 1;
    posY = posY + 1;
}
```

Now, every frame, the value of `posX` & `posY` will get larger by `1`. Thereby, moving the position of the ellipse every frame of the `draw()` loop. The complete code and output for this example might look like;

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( 600, 700 );
    background( 200, 40, 6 );
}

// Variables to define ellipse position
// NOTE: This *must* be defined globally.
// Otherwise, if they were defined locally inside draw
// they would get reset to '100' every frame,
// and the object would not move
var posX = 0;
var posY = 0;

function draw() {
    ellipse( posX, posY, 30, 30 );

    // update posX & posY every frame
    // add 1, then re-assign back to self
    posX = posX + 1;
    posY = posY + 1;
}
{% endhighlight %}


    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/09_basicAnimation_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/09_basicAnimation_01/09_basicAnimation_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/09_basicAnimation_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/09_basicAnimation_01/) |

# Another Example

Examine the following example for how variables are used to create a "Creepy Spinning Variable Person".

Notice that the following sketch uses;

- Variables that serve as references for other values.
    - Such as `headWidth` & `headHeight`, in lines 13 & 14
- Variables that are mathematically transformed and re-assigned to themselves every frame.
    - Such as `headAngle`, `headRotationRate`, & `armAngle` in lines 24, 27, & 29.
- p5 reserved word variables, that are serving to alter the sketch.
    - Such as `windowWidth` & `windowHeight` in line 7.
    - `mouseY` adjusting the `headRotationRate` in line 24.
    - `mouseX` & `mouseY` setting the person position in line 38.
    - `mouseX` setting the left arm rotation angle in line 67.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
/**
 * Creepy Spinning Variable Person
 *
 */

function setup() {
    createCanvas( windowWidth, windowHeight );
}

var headAngle = 0;
var headRotationRate = 0;
var armAngle = 0;
var headWidth = 80;
var headHeight = 40;

function draw() {
    // erase every frame
    background( 'rgb(56, 177, 255)' );
    // turn the cursor off
    noCursor();

    // UPDATE VALUES
    // base head rotation rate on mouseY pos
    headRotationRate = (mouseY * 0.1) - 20;
    // update head angle,
    // to equal itself plus headRotationRate
    headAngle = headAngle + headRotationRate;
    // set the arm to spin at a constant rate
    armAngle = armAngle - 3;


    // *****************************
    // PERSON SANDBOX
    // *****************************
    push();

    // make the person follow the mouse.
    translate( mouseX, mouseY );

    // ARMS
    push();
    // right arm
    strokeWeight( 10 );
    stroke( 0 );
    // draw the spinning forarm
    push();
    // move the position of the arm
    // to facilitate rotation
    translate( 60, -40 );
    // rotate the arm
    rotate( radians(armAngle) );
    // draw the arm
    line( 0, 0, 50, 0 );
    // define and draw a hand-thing
    fill( 'rgb(255, 176, 59)' );
    noStroke();
    ellipse( 50, 0, 20 );
    pop();
    // draw the static upper arm
    line( 10, -20, 60, -40 );

    // left arm
    push();
    // move the center to facilitate rotate
    translate( -10, -20 );
    // rotate, based on mouseX position
    rotate( radians( mouseX) );
    // draw arm and hand
    line( 0, 0, 150, 0);
    fill( 'rgb(255, 176, 59)' );
    noStroke();
    ellipse( 150, 0, 20 );
    pop();
    pop();


    // BODY
    // boring body shape
    ellipse( 0, 0, 40, 100 );

    // HEAD
    push();
    noStroke();
    fill( 'rgb(255, 176, 59)' );
    // move center
    translate( 0, -60 );
    // rotate head based on headAngle
    rotate( radians(headAngle) );
    // draw head skull
    ellipse( 0, 0, headWidth, headHeight );
    stroke(0);
    fill(255);
    // eyes
    strokeWeight(2);
    push();
    // draw eyes based on head size
    translate( headWidth * -0.2, headHeight * -0.2 );
    ellipse( 0, 0, headWidth * 0.33, headHeight * 0.33 );
    noStroke();
    fill( 'rgb(255, 31, 111)' );
    ellipse( 0, 0, 10 );
    fill( 0 );
    ellipse( 0, 0, 5 );
    pop();
    push();
    translate( headWidth * 0.2, headHeight * -0.2 );
    ellipse( 0, 0, 20 );
    noStroke();
    fill( 'rgb(255, 31, 111)' );
    ellipse( 0, 0, 10 );
    fill( 0 );
    ellipse( 0, 0, 5 );
    pop();

    // MOUTH
    push();
    fill( 0 );
    arc( 0, headHeight * 0.2, 60, 20, 0, PI );
    pop();
    pop(); // END HEAD

    // LEGS
    fill( 255 );
    noStroke();
    // keep legs out off bottom of window
    triangle( -15, 35, 5, 35, -40, height+100 );
    triangle( 15, 35, -5, 35, 40, height+100 );

    pop(); // END PERSON

}
{% endhighlight %}


    <div id="jotted-demo-3" class="" style="height:800px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/hwExamples/HW-5/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-5/HW-5.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-5/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/hwExamples/HW-5/) |


# { TODO: }  |  More on Variables in JS

Please read the following, which provides additional information on declaring and using variables in JavaScript.

- [w3schools variable tutorial](https://www.w3schools.com/js/js_variables.asp)
- [multi-word conventions](http://javascript.info/draft/variable-naming)


# Shiffman on Using Your Own Variables

Here is Dan Shiffman on how to declare and assign your own variables.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/Bn_B3T_Vbxs" frameborder="0" allowfullscreen></iframe></div>
