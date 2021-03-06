---
title: Constrain
module: 6
jotted: true
---

# Constraining Values

Another useful function is the constrain function (`constrain()`), which, constrains an input parameter's value to be within the min and max values supplied in the second and third parameters.

This can be useful for drawing, and protecting output values from "going out of range".

The following code is adapted from the p5 site, and demonstrates using constrain to keep a ball, whose position is dictated by the mouse, between two lines on a canvas.


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/08_constrain_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/08_constrain_01/08_constrain_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/08_constrain_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/08_constrain_01/) |
