---
title: p5 Variables
module: 5
jotted: true
---

# Variables

A key concept, that you will need to fully understand in order to do almost anything in coding, is that of _"variables"_.

A [_variable_](https://en.wikipedia.org/wiki/Variable_(computer_science)), is a _storage location_, paired with a _symbolic name_ or _identifier_. Within this storage location, data can be stored, referenced, replaced, updated, or removed.

A variable name, as we will see, serves as a way of telling a computer to references a specific storage location, where some data is or needs to be placed.


# Reserved p5 Variables

In p5, there are a number of reserved variable names, that the p5 language uses and sets for us. We have already utilized two such variables this week;

- `mouseX`
- `mouseY`

A reserved p5 variable, is a special namespace, that p5 sets with information and data, that a user may need to use. The `mouseX` & `mouseY` variables, for instance, are where p5 stores the X & Y locations of the mouse specific to the canvas for instance.

In the below example, the X and Y locations of the mouse are printed to the canvas, utilizing the `mouseX` & `mouseY` variables, so that you can see what type of data is stored inside of these variables. Notice: that as you move the mouse within the canvas, the number update. This is becuase these two values are reset, or updated, every frame (that is every time the `draw()` loop is called).


<div id="jotted-demo-1" class="jotted-theme-stacked" style="height:649px"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/02_mouse_location_01/sketch.js"
        },
        {
            type: "html",
            hide: true,
            url:"../../../p5_resources/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/02_mouse_location_01/02_mouse_location_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/02_mouse_location_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/02_mouse_location_01/) |

You can read more about `mouseX` and `mouseY` at their reference pages ([`mouseX` reference](https://p5js.org/reference/#/p5/mouseX), [`mouseY` reference](https://p5js.org/reference/#/p5/mouseY)).

> NOTE: `mouseX` and `mouseY` get obtain their value based on their position relative to the canvas' (0,0). This is _PRIOR_ to any transformations, which means you will always have to take into account `mouseX` and `mouseY` being based off of the top-left corner.

## `width` and `height`

Another set of p5 variables, that you may want to become familiar with are `width` and `height`. p5 uses these namespaces, to store the width and height of the canvas, respectively.

- [`width` reference page](https://p5js.org/reference/#/p5/width)
- [`height` reference page](https://p5js.org/reference/#/p5/height)

In the below example, the canvas is set to have a width value of 500px and a height of 200px. Using the `width` and `height` p5 variables, we then print out their values.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( 500, 200 );
}

function draw() {
    background( 'rgb(87, 219, 147)' );

    textSize(36);
    text("width: " + width, 10, 40);
    text("height: " + height, 10, 80);
}
{% endhighlight %}


<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/03_width_height_01/sketch.js"
        },
        {
            type: "html",
            hide: true,
            url:"../../../p5_resources/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/03_width_height_01/03_width_height_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/03_width_height_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/03_width_height_01/) |


> How else can `width` and `height` be used?

Another way of using width and height, is to specify position parameter values, relative to the canvas size. In the next example, an ellipse is placed in the center of the canvas, using the `width` and `height` values.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( 500, 200 );
}

function draw() {
    background( 'rgb(219, 111, 87)' );

    // translate to the "center" of the canvas
    // do this using width and height
    translate( width/2, height/2 );

    // draw a circle
    ellipse( 0, 0, 50 );
}
{% endhighlight %}


<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/03_width_height_02/sketch.js"
        },
        {
            type: "html",
            hide: true,
            url:"../../../p5_resources/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/03_width_height_02/03_width_height_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/03_width_height_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/03_width_height_02/) |


## `windowWidth` & `windowHeight`

Another set of useful p5 variables you should know are `windowWidth` and `windowHeight`.

- [`windowWidth` reference page](https://p5js.org/reference/#/p5/windowWidth)
- [`windowHeight` reference page](https://p5js.org/reference/#/p5/windowHeight)

As you noticed from reading the reference pages, these variables store the browser's window width, and window height, respectively.

These variables are most often used in conjunction with the `createCanvas()` function, to create a canvas that _IS_ the same size as the browser window.

This is seen below in the next example. You should change the size of the browser window, and "re-fresh" the page to get a full sense of what these variables do with `createCanvas()`. You will notice, that not only does the canvas size change, but that the ellipse always remains in the center of the canvas.

> NOTE: Although this is demo-ed in the code window, you should <a href="https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/04_window_vars_01/" target="_blank">open this example up in a new window to really experience it.</a>


<div id="jotted-demo-4" class="jotted-theme-stacked" style="height:600px"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-4"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/04_window_vars_01/sketch.js"
        },
        {
            type: "html",
            hide: true,
            url:"../../../p5_resources/index.html"
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/04_window_vars_01/04_window_vars_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/04_window_vars_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/04_window_vars_01/) |



> NOTE: The canvas is only created once, and placing these variables within the `createCanvas()` function will not create a canvas that automatically resizes. If this behavior is desired, other steps will need to be taken, which are described later in the course.
>
> Or you could google the answer...


# Constants

In addition to event and environment based p5 reserved variables, such as `width` and `mouseY`, there are a number of "constant" variables, whose value is set and never changes. We have already come across these while looking at radians and the unit circle.

- `PI`
- `HALF_PI`
- `QUARTER_PI`
- `TWO_PI`


# Other p5 Variables

There are many other p5 variables you might want to check out. Some of these may prove useful to your work this semester and beyond. I will try to make sure we highlight new event and environment variables as they are presented throughout the semester. But know that, if you see something you do not recognize, you should look it up on the p5 reference page or google it.



# Shiffman on p5 Variables

Here is Dan Shiffman on p5 Variables and introduction to animation.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/RnS0YNuLfQQ" frameborder="0" allowfullscreen></iframe></div>
