---
title: Homework Example
module: 4
jotted: true
---

# Homework Example<br>My Self-Portrait


This video shows you one approach to this assignment, including a workflow, and ways of thinking about drawing in p5. The code created from the video, is below.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/eIu5KqnStgI" frameborder="0" allowfullscreen></iframe></div>


{% highlight js linenos %}
function setup() {
    // create a canvas to draw on
    createCanvas( 600, 800 );
}

function draw() {

    // background
    background( 'rgb(119, 255, 255)' );

    /* ***************************** */
    /* MAIN SANDBOX */
    /* ***************************** */
    push();

    // set the grid center( x:0, y:0 )
    // to canvas center
    translate( 300, 400 );


    /* ***************************** */
    /* ARMS */
    /* ***************************** */
    push();
    translate( 0, -55 );

    // left arm
    stroke( 'rgba(158, 0, 0, 1.0)' );
    strokeWeight( 50 );
    line( -140, 0, -200, -100 );
    line( -200, -100, -200, -200 );

    // hand
    stroke( 'rgb(133, 94, 0)' );
    strokeWeight( 75 );
    point( -200, -200 );

    // right arm
    rotate( PI );
    stroke( 'rgba(158, 0, 0, 1.0)' );
    strokeWeight( 50 );
    line( -140, 0, -200, -100 );
    line( -200, -100, -200, -200 );

    // hand
    stroke( 'rgb(133, 94, 0)' );
    strokeWeight( 75 );
    point( -200, -200 );

    pop(); // ARMS END


    /* ***************************** */
    /* BODY */
    /* ***************************** */
    push();
    // main shirt rectangle
    rect( -150, -100, 300, 300 );

    // red short stripes
    push();
    fill( 'rgba(255, 0, 0, 0.66)' );
    translate(-150, -100);
    rect(0, 0, 300, 40);
    translate(0, 80);
    rect(0, 0, 300, 40);
    translate(0, 80);
    rect(0, 0, 300, 40);
    translate(0, 80);
    rect(0, 0, 300, 40);
    pop();

    // green shirt stripes
    push();
    fill( 'rgba(16, 143, 0, 0.66)' );
    translate(-150, -100);
    rect(0, 0, 40, 300);
    translate(87, 0);
    rect(0, 0, 40, 300);
    translate(87, 0);
    rect(0, 0, 40, 300);
    translate(87, 0);
    rect(0, 0, 40, 300);
    pop();

    // button
    ellipse( 0, 0, 30 );

    pop(); // BODY END!


    /* ***************************** */
    /* LEGS */
    /* ***************************** */
    push();
    translate( 0, 200 );

    // left leg
    fill( 'rgb(133, 94, 0)' );
    triangle( -130, 0, 0, 0, -150, 500 );
    // right leg
    scale( -1, 1 );
    triangle( -130, 0, 0, 0, -150, 500 );
    pop(); // LEGS END


    /* ***************************** */
    /* HEAD */
    /* ***************************** */
    push();
    translate( 0, -175 );

    fill( 'rgb(205, 142, 218)' );
    ellipse( 0, 0, 330, 200 );

    // mouth
    fill( 0 );
    arc(
        0,
        50,
        250,
        60,
        radians(350),
        radians(190),
        PIE
    );

    // mustache
    push();
    noStroke();
    fill( 'rgb(119, 56, 25)' );
    quad( 0, 10, -10, 40, -150, 50, -110, 20 );
    scale( -1, 1 );
    quad( 0, 10, -10, 40, -150, 50, -110, 20 );
    pop();

    // nose
    triangle( 0, -20, 30, 20, -30, 20 );

    // eyes
    // left
    push();
    translate( -60, -40 );

    fill(255);
    ellipse( 0, 0, 60, 35 );
    noFill();
    fill( 'rgb(75, 185, 255)' );
    ellipse( 0, 0, 30 );
    fill( 0 );
    ellipse( 0, 0, 20 );

    fill( 'rgb(119, 56, 25)' );
    quad( 40, -40, 35, -30, -50, -10, -45, -30 );
    pop();

    // right
    push();
    translate( 60, -40 );

    fill(255);
    ellipse( 0, 0, 60, 35 );
    noFill();
    fill( 'rgb(75, 185, 255)' );
    ellipse( 0, 0, 30 );
    fill( 0 );
    ellipse( 0, 0, 20 );
    fill( 'rgb(119, 56, 25)' );
    quad( -40, -40, -35, -30, 50, -10, 45, -30 );
    pop();

    pop(); // HEAD END

    pop(); //END CHARACTER
}
{% endhighlight %}


    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/hwExamples/HW-4_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-4_02/HW-4_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-4_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/hwExamples/HW-4_02/) |




# Additional Example

Here is additional code, from an earlier iteration of the video example code. This is just one example, of how this assignment might be approached. Please feel free to pull it apart, study it, play with it, etc.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    // Setup basic elements
    createCanvas(500, 500);
    background(255, 247, 240);

    // move everything to the center of the canvas
    translate(250, 250);

    // Main body
    push();
    rectMode(CENTER);
    fill(200, 10, 20);
    rect(0, 0, 200, 300);
    line(15, -150, 15, 150);
    fill(0);
    ellipse(-5, -50, 15, 15);
    ellipse(-5, -10, 15, 15);
    ellipse(-5, 30, 15, 15);
    ellipse(-5, 70, 15, 15);
    ellipse(-5, 110, 15, 15);
    pop();

    // Legs
    push();
    // translate to the leg position
    translate( 0, 150 );
    fill(90, 50, 245);
    triangle(10, 0, 100, 0, 210, 190);
    triangle(-10, 0, -100, 0, -210, 190);
    pop();

    // Arms
    push();
    // translate to the arm position
    translate(0, -50);
    strokeWeight(20);
    line(80, 0, 140, 0);
    line(140, 0, 210, -50);
    fill(0, 0, 0);
    ellipse(210, -50, 20, 20);
    line(-80, 0, -140, 40);
    line(-140, 40, -190, 150);
    fill(0, 0, 0);
    ellipse(-190, 150, 20, 20);
    pop();



    // Head

    // skull
    push();
    // translate to the head position
    translate(0, -150);
    fill(200, 10, 200);
    ellipse(0, 0, 400, 125);

    // eyes
    fill(250, 249, 255);
    ellipse(-80, -20, 100, 40);
    fill(0, 0, 0);
    ellipse(-80, -20, 40, 40);

    fill(250, 249, 255);
    ellipse( 80, -20, 100, 10);
    fill(0, 0, 0);
    ellipse( 80, -20, 60, 5);

    // mouth
    fill(2, 240, 250);
    arc(0, 30, 200, 60, 0, PI, CHORD);

    // mustache
    fill( 113, 81, 57 );
    quad(0,5,-5,40,-120,40,-90,20);
    quad(0,5,5,40,120,40,90,20);

    // nose
    fill(200, 90, 170);
    triangle(-10, -40, -10, 5, 70, 80);

    // end of head
    pop();

    // Naming
    push();
    // move the text up
    translate( 0, -250 );
    textAlign(CENTER);
    textSize(20);
    textFont("Georgia");
    text("A Self-Portrait, by Michael Musick", 0, 27);
    pop();

}
{% endhighlight %}



    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/hwExamples/HW-4/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-4/HW-4.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-4/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/hwExamples/HW-4/) |
