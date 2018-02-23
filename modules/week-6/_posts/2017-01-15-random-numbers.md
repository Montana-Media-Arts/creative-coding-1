---
title: Random Numbers
module: 6
jotted: true
---

# Random Number Generators

Another useful function, that you must understand, and will use often, is the random number generator function ( `random()` ).

The random number generator produces and returns a random Number every time the function is called.

- [`random()` reference page](https://p5js.org/reference/#/p5/random)

As you saw from the reference page, the random number generator function can accept 0, 1, 2, or an array of input parameters. (We will ignore the array option for the moment).

## Default Random Number Generator

If no input parameters are supplied, then the function will return values between `0.0` and `1.0`.

The below code, gets a new random number every frame, and displays it in the canvas.

> NOTE: The range of the function is inclusive of the min and exclusive of the max. This means that the random number generator function can return a value of `0`, but can only provide a return value of _just_ below the max or `1`, such as `0.9999999999999`.


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/09_random_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_01/09_random_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/09_random_01/) |

## Random Number Generator with Inputs

When you provide 1 or 2 input parameters, the random number generator takes care of scaling for you. If you provide 1 input parameter, the return values are scaled or mapped, between `0` and the supplied Number. When 2 input parameters are provided, the return values are scaled linearly between the two provided parameters.

This next example demonstrates the use of a single input parameter to return values between `0` and `255`, which are used to set the background color. (NOTE: That these return values are also "floored" using the `floor()` function, so that the values are integer values for the background function. This means the max value provided at the input parameter is 256. Since this function is exclusive of the max, it will never return 256, and we want to round down to 255. )

<div id="jotted-demo-2" class="jotted-theme-stacked" style="300px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/09_random_02/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_02/09_random_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/09_random_02/) |

In this last example, we provide two parameters, which are used to scale the random number generators return values between `10` and `width-10`, which we use to randomly grab set the size of an ellipse.
<div id="code-heading">sketch.js</div>

<div id="jotted-demo-3" class="jotted-theme-stacked" style="300px;"></div>

<script>
new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/09_random_03/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_03/09_random_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/09_random_03/) |


# More Examples

I am providing three more examples, please examine them, figure out what is going on, and play with them.

## Random Ombré Triangles on a Canvas

The following creates a canvas where, consecutive triangles are placed, with varying position, to make an ombré color progression. The slight "askew-ness" of the triangles is accomplished through random number generators. Likewise, the color progression is created through random number generators, and wrapped using modulus.


<div id="jotted-demo-4" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-4"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/09_random_04_ombre_canvas/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_04_ombre_canvas/09_random_04_ombre_canvas.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_04_ombre_canvas/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/09_random_04_ombre_canvas/) |

## Random Walker

A rather infamous example, using random generators is to create a "random walker", this is a sketch that draws a shape, which randomly "walks" around the canvas. There are two examples of the sketch, one with a small point, and one with a larger ellipse. Notice how they use the random number generator and the addition-assignment operator to update the position of the object.

#### Small Walker Object

<div id="jotted-demo-5" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-5"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/09_random_05_walker_02/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_05_walker_02/09_random_05_walker_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_05_walker_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/09_random_05_walker_02/) |


#### Large Walker Object


<div id="jotted-demo-6" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-6"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/09_random_05_walker_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_05_walker_01/09_random_05_walker_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/09_random_05_walker_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/09_random_05_walker_01/) |


# Shiffman on Random

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/nfmV2kuQKwA" frameborder="0" allowfullscreen></iframe></div>
