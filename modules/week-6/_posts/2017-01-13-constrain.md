---
title: Constrain
module: 6
jotted: true
---

# Constraining Values

Another useful function is the constrain function (`constrain()`), which, constrains an input parameter's value to be within the min and max values supplied in the second and third parameters.

This can be useful for drawing, and protecting output values from "going out of range".

The following code is adapted from the p5 site, and demonstrates using constrain to keep a ball, whose position is dictated by the mouse, between two lines on a canvas.

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function draw() {
  background( 'rgb(137, 140, 204)' );

  var leftWall = 50;
  var rightWall = width - 50;

  // xm is just the mouseX, while
  // xc is the mouseX, but constrained
  // between the leftWall and rightWall!
  var xm = mouseX;
  var xc = constrain(mouseX, leftWall, rightWall);

  // Draw the walls.
  stroke( 'red' );
  line(leftWall, 0, leftWall, height);
  line(rightWall, 0, rightWall, height);

  // Draw xm and xc as circles.
  noStroke();
  fill(255);
  ellipse(xm, 33, 9,9); // Not Constrained
  fill(0);
  ellipse(xc, 66, 9,9); // Constrained
}
{% endhighlight %}



    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/08_constrain_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/08_constrain_01/08_constrain_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/08_constrain_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/08_constrain_01/) |
