---
title: Bouncing Ball
module: 7
jotted: true
---

# Bouncing Ball, Rollovers, and More

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/r2S7j54I68c" frameborder="0" allowfullscreen></iframe></div>

#### Rollover Code

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
// Rollover Rect

var x = 250;
var y = 150;
var box_size = 100;

function setup() {
    createCanvas(windowWidth, 400);
}

function draw() {
    background(200);
    // check if the mouse is witin the bounds
    // of the box?
    if ((mouseX > x) && (mouseX < x + box_size) && (mouseY > y) && (mouseY < y + box_size)) {
        fill(0);
    } else {
        fill(255);
    }

    // draw the rollover box
    rect(x, y, box_size, box_size);
}
{% endhighlight %}


    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/16_rollover_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/16_rollover_01/16_rollover_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/16_rollover_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/16_rollover_01/) |




#### Update to Bouncing Ball

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
var x = 300;
var speed = 5;

function setup() {
    createCanvas(windowWidth, 400);
}

function draw() {
    background(0);

    stroke(255);
    strokeWeight(4);
    noFill();
    ellipse(x, height / 2, 100, 100);

    if ( x > width || x < 0 ) {
        speed = speed * -1;
    }
    x = x + speed;
}
{% endhighlight %}


    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/15_bouncing_ball_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/15_bouncing_ball_02/15_bouncing_ball_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/15_bouncing_ball_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/15_bouncing_ball_02/) |
