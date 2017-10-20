---
title: Buttons, Roll Overs, & Switches
module: 7
jotted: true
---

# Buttons, Roll Overs, & Switches

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/Rk-_syQluvc" frameborder="0" allowfullscreen></iframe></div>

## Button Example 1

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 400 );
}


function draw() {
    background( 0 );
    stroke( 255 );
    strokeWeight( 4 );
    noFill();

    if( mouseX > 250 && mouseX < 350 && mouseY > 150 && mouseY < 250 ) {
        if( mouseIsPressed ) {
            background(0, 255, 0);
        }
        fill(255, 0, 200);
    }

    rectMode(CENTER);
    rect(300, 200, 100, 100);
}
{% endhighlight %}

<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/07/17_button_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/07/17_button_01/17_button_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/07/17_button_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/07/17_button_01/) |



## Button Example 2

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
var on = false;

function setup() {
    createCanvas( windowWidth, 400 );
}


function draw() {

    if( on ) {
        background( 0, 255, 0 );
    } else {
        background( 0 );
    }

    stroke( 255 );
    strokeWeight( 4 );
    noFill();

    if( mouseX > 250 && mouseX < 350 && mouseY > 150 && mouseY < 250 ) {
        fill( 255, 0, 200 );
    }

    rectMode(CENTER);
    rect(300, 200, 100, 100);
}

function mousePressed() {
    if( mouseX > 250 && mouseX < 350 && mouseY > 150 && mouseY < 250 ) {
        on = !on;
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
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/07/17_button_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/07/17_button_02/17_button_02.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/07/17_button_02/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/07/17_button_02/) |
