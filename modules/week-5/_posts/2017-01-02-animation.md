---
title: Animation
module: 5
jotted: true
---

# Animation

What fun would programming be if it wasn't easy to make things move, animate, and change over time!?! It wouldn't be nearly as much fun. So, of course, p5 allows artists to create sketches that change over time and that can react to user input.

A simple example involves replacing a user's mouse with an ellipse, which then follows the intended position of the mouse around the canvas.



<div id="jotted-demo-1" class="" style="height:600px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/01_ellipse_mouse_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/01_ellipse_mouse_01/01_ellipse_mouse_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/01_ellipse_mouse_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/01_ellipse_mouse_01/) |


<br />


<br />


So..., how is the above working? Here is the code for the above sketch.


{% highlight js linenos %}
function setup() {
    createCanvas( 800, 600 );
    background( 'rgb(255, 210, 94)' );
}

function draw() {
    noCursor();
    fill( 255 );
    ellipse( mouseX, mouseY, 40 );
}
{% endhighlight %}


<br />

There are a few new elements to this sketch. So let's discuss them.

In line 7, there is a function being used called [`noCursor()`](https://p5js.org/reference/#/p5/noCursor). But, all this function does, is remove the visual presence of a user's cursor inside a canvas. This is therefore, not what is animating the sketch.

In line 9 however, there are two new things we have not seen before, `mouseX` & `mouseY`. You will learn about these p5 Variables on the next page. Briefly, I will tell you they simply query p5 for the location of the mouse on the canvas. It would seem as though, these are what is causing the animation to happen. Although, yes, these are assisting in the animation, they are simply being updated by p5, then passed along to the `ellipse()` function.

It is actually the combination of the `mouseX`/`mouseY` variables, along with something else we have previously discussed, that is animating this sketch.


<br />

The thing animating this sketch, is actually the `draw()` function!

## The `draw()` loop

The `draw()` function has been mentioned earlier in the course. However, until now, the significance between the `draw()` and `setup()` functions has perhaps been understated.

As mentioned earlier, the `setup()` function gets called by p5 at the start of your sketch's execution. The `setup()` function gets called _once.  AND ONLY ONCE!_

After the `setup()` function finishes executing, the `draw()` function then gets called.


<br />


After the `draw()` function finishes executing, the `draw()` function then gets called again.

<br />


<br />


<br />


After the `draw()` function finishes executing, the `draw()` function then gets called again.

After the `draw()` function finishes executing, the `draw()` function then gets called again.

After the `draw()` function finishes executing, the `draw()` function then gets called again.

After the `draw()` function finishes executing, the `draw()` function then gets called again.

...and again...

...and again...

...and again...

...and again...

...and again...

...and again...



<br />


<br />

...until there is an error or the browser page is closed.


<br />

In p5, the `draw()` function is also sometimes referred to as the _"draw loop"_. That is because it gets called repeatedly by p5.

## Animation

Animation is achieved through slight movement of objects on a screen, in quick enough succession, as to _fool_ the eye. The default rate at which the "draw loop" is called (aka. the default "frame rate") in p5 is 60fps (frames per second).

This frame rate is important not only for animation, but also for human-computer interaction. As the draw loop is where we will also eventually put code that allows the user to "interact" with the sketch. This is why it is important that the frame rate be high enough as to reduce any perceptible delay to a human.

## Slight Visual Changes

How can you achieve slight changes in your sketch's drawings from frame to frame? So far, we have only learned how to use "hard coded numbers" as input parameters, or `mouseX`/`mouseY` which, we still don't really know anything about. Well, obviously we will need to find a way of changing the numbers that we pass as input parameters to functions from frame to frame. That is the topic of the next few slides. 
