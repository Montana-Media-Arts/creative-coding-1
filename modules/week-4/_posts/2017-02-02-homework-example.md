---
title: Homework Example
module: 4
jotted: true
---

# Homework Example<br>My Self-Portrait

I am presenting code I wrote for this assignment, so you can see one example, of how this might be approached. Please feel free to pull it apart, study it, play with it, etc.

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


<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/hwExamples/HW-4/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/hwExamples/HW-4/HW-4.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/hwExamples/HW-4/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/hwExamples/HW-4/) |
