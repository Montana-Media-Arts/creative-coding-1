---
title: 10 Ellipses
module: 8
jotted: true
---

# 10 Ellipses

By this point, you have probably experienced _and written_, code sketches that are;

- getting quite large,
- seem to sprawl, with little organization,
- and have lots of lines of code that do practically the same thing, with slight variations...

The type of code just described is hard to deal with, understand, or change. Really, it is poorly written code. You must be saying to yourself... "There's gotta be a better way!"

Well, there is... but first, let's review the above problem in more detail.

#### 10 Circles

Let's create a specific problem. What would be the best way to write a sketch that contains 10 circular ellipses spread across a canvas?

You might be thinking to yourself, that we should write 10 lines of code to draw each ellipse. The following does this, it defines and draws 10 ellipses. Each ellipse's position is set as a ratio of the `windowWidth`.

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 300 );
}


// using 'let' instead of 'var'
let pos_x = 0;
let pos_y = 0;
let d = 30;
let r = d/2;

function draw() {
    background( 'rgb(3, 78, 115)' );

    // define drawing parameters
    fill(255);
    noStroke();

    // circle 0
    pos_x = width * 0/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 1
    pos_x = width * 1/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 2
    pos_x = width * 2/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 3
    pos_x = width * 3/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 4
    pos_x = width * 4/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 4
    pos_x = width * 4/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 5
    pos_x = width * 5/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 6
    pos_x = width * 6/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 7
    pos_x = width * 7/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 8
    pos_x = width * 8/10 + r;
    ellipse( pos_x, pos_y, d );

    // circle 9
    pos_x = width * 9/10 + r;
    ellipse( pos_x, pos_y, d );

    pos_y++;
    if (pos_y > height) {
        pos_y = 0;
    }
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
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/08/01_for_wrong_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/08/01_for_wrong_01/01_for_wrong_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/08/01_for_wrong_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/08/01_for_wrong_01/) |


The above code is fine, in that;

- it obviously works
- and it is not _too_ complicated.

However, what is you wanted to draw 100 circles, or 1000, circles, or tens-of-thousands of circles? Do you really want to copy and paste 10,000 of the same lines code? And what if you need to change something in that line after the fact? Are you going to change each line? **OBVIOUSLY NO!**

If we want to eloquently accomplish the above, we are going to need to use a better control structure.
