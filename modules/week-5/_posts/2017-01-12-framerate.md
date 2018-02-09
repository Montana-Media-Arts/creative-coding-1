---
title: frameRate() & frameCount
module: 5
jotted: true
---

# `frameRate()` & `frameCount`

Now that we are starting to animate, there are a few more p5 functions and variables we should discuss. These relate to the rate of the `draw()` functions execution, and the number of times the `draw()` function has executed.

### Setting `frameRate()`

The `frameRate()` function is used to _get_ or _set_ the frame rate of a sketch; that is the rate at which the `draw()` function is executed.

NOTE: By default, p5 tries to execute your sketch with a frame rate of 60 frames per second (fps).

- [`frameRate()` reference page](https://p5js.org/reference/#/p5/frameRate)

Per the functions documentation page, to _set_ the frame rate of a sketch, we simply need to pass a Number as a single parameter to the function.

In the following example, we have an ellipse, that is rotating clockwise, updating its position by 45° every iteration of the `draw()` loop. In this first example, the frame rate is not adjusted.

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/11_frameRate_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_01/11_frameRate_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/11_frameRate_01/) |

<br />


In the following example, the only change made is adding the `frameRate()` function to `setup()` function. Additionally, the frame rate is set to 2 fps, by passing the Number `2` as a parameter to the `frameRate()` function. Our code, and result, now looks like;

> Notice how we can now clearly see the frame based movement of the spinning ellipse.
>
> You should also adjust the frame rate value in the below example. How low is too low, and how high is too high?


<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/11_frameRate_02/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_02/11_frameRate_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/11_frameRate_02/) |


### Getting `frameRate()`

We can also _get_ the value currently being used for frame rate from the `frameRate()` function. When we call `frameRate()` and pass it _NO_ parameters, the function knows that we are instead querying it for the current frame rate.

In the below example, I have added a `push()`/`pop()` sandbox around the rotating ellipse, and then added two lines at the bottom of the `draw()` function to _get_ the frame rate and the display it in the top-left corner of the canvas.

```js
let fr = frameRate();
text( "frame rate: " + fr, 10, 20 );
```


<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/11_frameRate_03/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_03/11_frameRate_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/11_frameRate_03/) |

**NOTE:** That the frame rate value returned is not always 2, but is often just, very _close_ to two. The `frameRate()` function returns whatever the _true_ frame rate that the sketch is running at. The sketch tries to run as close as possible to the specified frame rate. But, slight variations occur, causing it to drift just a bit.

Usually, it is close enough, that we can safely assume the sketch is running at the _specified_ frame rate. However, if you create large, complex code sketches, that require lots of processing time, then you will notice this number vary much more widely.


<br />

Finally, putting this all together, lets use the `mouseX` position to set the frame rate. Since the canvas is currently 400 pixels wide, the `mouseX` value is multiplied by `0.3` so that there is a max frame rate of 120 fps. A base of 0.25 has also been added to this value.  This is to protect from setting a frame rate of 0. If frame rate is set to 0, it will never grab the mouse coordinates again, or update the sketches frame rate again. By setting a base of 0.25, we guarantee that the longest time between frames is `1/0.25` or 4" seconds.

This code is placed at the top of the `draw()` function loop.

<div id="jotted-demo-4" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-4"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/11_frameRate_04/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_04/11_frameRate_04.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/11_frameRate_04/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/11_frameRate_04/) |

> What do you notice while playing in the above example?
>
> 1. How long does it take before the sketch initially updates the frame rate?
> 2. What is the max frame rate the sketch will go to?

We know, from the conversation up above, that the sketch can go as long as 4" between frames, as happens on the first frame.

We also find out, from looking at the frame rate output, that the highest the p5 sketch will try and go is 60 fps. This is the max frame rate that we can set for p5 currently.


## Getting the `frameCount`

`frameCount` is a p5 reserved word variable, which can be used to query the number of frames that have elapsed since the start of the sketch.

In the following example, the frame count is grabbed using the `frameCount` variable, and then displayed in the top-left corner of the sketch.


<div id="jotted-demo-5" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-5"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/12_frameCount_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/12_frameCount_01/12_frameCount_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/12_frameCount_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/12_frameCount_01/) |

> The above code uses a mathematical function known as [modulo](https://en.wikipedia.org/wiki/Modulo_operation). The operator for this is the `%` symbol. We will talk more about modulo next week during a more complete discussion of math in p5.
