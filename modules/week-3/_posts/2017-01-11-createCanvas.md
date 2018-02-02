---
title: createCanvas()
module: 3
jotted: true
---

# `createCanvas()`

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/LuVT5FAdQIo" frameborder="0" allowfullscreen></iframe></div>


One of the first things you will need to do, in almost every p5 code sketch, is to create a canvas. This is one of the functions you will _always_ put in the p5 `setup()` function definition.

The "canvas" is what p5 draws to. This is what most of the code you write this semester will effect.

In HTML5 the `<canvas>` element was designed as a way of allowing JavaScript to create complex graphics, visuals, and video within a common element on a webpage. p5 takes advantage of this element and uses it almost exclusively for its output.

- [More information on the `<canvas>` element.](https://www.w3schools.com/html/html5_canvas.asp)

<br />


The "Hello World!" code sketches we just completed utilized, and where produced, using the HTML5 canvas. This was possible because p5 automatically creates a canvas for you, even if you do not specify one. However, the default canvas element that p5 creates is only 100 pixels in width by 100 pixels in height.

> From now on, "pixels" will be abbreviated as "px".

<br />


The following demonstrates the default size of the p5 canvas. Notice how it takes up a very small corner of the possible output area.

<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/03/02_defaultCanvas_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>


<br />

In order to more fully utilize space, and to create a larger area for our code sketches to be displayed in, we will need to explicitly write a statement to create a larger canvas element. To do this, we will use the `createCanvas()` function.

Please look at and read through the `createCanvas()` documentation below.

([Link to `createCanvas()` function documentation](https://p5js.org/reference/#/p5/createCanvas))

<div class="embed-responsive" style="padding-bottom:80%; border: 1px solid #000"><iframe class="embed-responsive-item" src="https://p5js.org/reference/#/p5/createCanvas" frameborder="0" allowfullscreen></iframe></div>



### Function Parameters

The documentation for `createCanvas()` tells us a number of interesting details.

The function requires at least two parameters and can accept an optional third parameter. These are;

- `w`
    - A Number (This can be any real positive value)
    - That sets the **width** of the canvas in pixels
- `h`
    - A Number (This can be any real positive value)
    - That sets the **height** of the canvas in pixels
- [`renderer`]
    - This can be used to tell p5 to use WEBGL, thereby enabling 3d sketches. (More on that later in the semester).

This means we can set the size of our canvas, in pixels.

Below is an example of using the `createCanvas()` function. Notice that initially, the `w` and `h` parameters are set to 600px by 400px. Change these values in line no. 3 to change the size of the canvas.

> Remember to keep the separation comma intact between the 2 parameters. <br />
> `( 600, 400 )`
>
> Also notice that there is another line `background('blue')`. You should ignore this for the time being.


{% highlight js linenos %}
function setup(){
    // Change the number in the createCanvas() function
    createCanvas( 600, 400 );

    // Ignore this line for the moment,
    // This is what is "coloring" the canvas
    background( 'blue' );
}
{% endhighlight %}

<div class="displayed_jotted_example">
<div id="jotted-demo-2" class="" style="height:500px;"></div>
</div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/03/03_createCanvas_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/03/03_createCanvas_01/03_createCanvas_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/03/03_createCanvas_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/03/03_createCanvas_01/) |


<br />

**NOTE:** You should always write a statement to `createCanvas()` as one of the first lines in your `setup()` function.
