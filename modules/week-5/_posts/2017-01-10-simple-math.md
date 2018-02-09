---
title: Simple Math
module: 5
jotted: true
---

# Simple Math & Animation

In addition to storing static values in variables that will get used throughout a code sketch, another use of variables is to store the results of mathematical calculations, for use later in your code.

We have already seen the use of the p5 variables `mouseX` and `mouseY` to animate a p5 sketch. But what if you wanted to create generative code, that will cause a sketch to appear and form over time?

The answer of course, is the use of variables to hold the output of mathematical calculations.

We will get into math more deeply next week, for this week, I will assume you understand how addition/subtraction, and multiplication/division work.

> You are going to get good at math again! I promise.

## Assign Results from Calculations to Variables

To assign the results of a mathematical calculation to a variable, you simply need to use the assignment operator (i.e. the equals sign, `=`) with the calculation.

For example, the following assigns the result of `2 + 2` to the variable, `four`;

```js
let four = 2 + 2;
```

> The above would be said as; "The variable four _gets_ the result of two plus two."

This is obviously quite boring, and superfluous, as we know that `2 + 2` equals `4`. However, there may come a time when you have many variables in relation to each other, where a change in one, needs to be propagated throughout the system. In such a system, you may have multiple variables, that are each used in the calculations.

<br />


In the following example, we declare and assign an initial variable `smileySize`. From this, all other aspects of the smiley face's shape and size are calculated. If this first variable (`smileySize`) is changed (which you should do in the example code below), then the rest of the sketch adjusts. This occurs since the rest of the variables are based off this initial size variable.

<div id="jotted-demo-1" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/08_related_vars_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/08_related_vars_01/08_related_vars_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/08_related_vars_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/08_related_vars_01/) |


## In Practice, in order to Animate

These same principles can be applied to animation. This will allow us to work towards our generative art sketch.


<br />

As an example, let's define two variables globally, which will store position data.

```js
let posX = 0;
let posY = 0;
```

Then, inside of the `draw()` function loop, let's use them to represent the position parameters for an ellipse function.

After that, we will add `1` to each variable, and then re-assign that result _BACK_ to the variable.

```js
function draw() {
    ellipse( posX, posY, 30, 30 );

    // update posX & posY every frame
    // add 1, then re-assign back to self
    posX = posX + 1;
    posY = posY + 1;
}
```

Now, every frame, the value of `posX` & `posY` will get larger by `1`. Thereby, moving the position of the ellipse every frame of the `draw()` loop. The complete code and output for this example might look like;

<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/09_basicAnimation_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/09_basicAnimation_01/09_basicAnimation_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/09_basicAnimation_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/09_basicAnimation_01/) |

# Another Example

Examine the following example for how variables are used to create a "Creepy Spinning Variable Person".

Notice that the following sketch uses;

- Variables that serve as references for other values.
    - Such as `headWidth` & `headHeight`, in lines 13 & 14
- Variables that are mathematically transformed and re-assigned to themselves every frame.
    - Such as `headAngle`, `headRotationRate`, & `armAngle` in lines 24, 27, & 29.
- p5 reserved word variables, that are serving to alter the sketch.
    - Such as `windowWidth` & `windowHeight` in line 7.
    - `mouseY` adjusting the `headRotationRate` in line 24.
    - `mouseX` & `mouseY` setting the person position in line 38.
    - `mouseX` setting the left arm rotation angle in line 67.

<div id="jotted-demo-3" class="jotted-theme-stacked" style="800px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/hwExamples/HW-5/sketch.js"
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
        { name: 'ace', options: { "maxLines": 150 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-5/HW-5.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/hwExamples/HW-5/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/hwExamples/HW-5/) |


# { TODO: }  |  More on Variables in JS

Please read the following, which provides additional information on declaring and using variables in JavaScript.

- [w3schools variable tutorial](https://www.w3schools.com/js/js_variables.asp)
- [multi-word conventions](http://javascript.info/draft/variable-naming)


# Shiffman on Using Your Own Variables

Here is Dan Shiffman on how to declare and assign your own variables.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/Bn_B3T_Vbxs" frameborder="0" allowfullscreen></iframe></div>
