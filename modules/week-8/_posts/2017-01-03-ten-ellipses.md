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


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/01_for_wrong_01/sketch.js"
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
        { name: 'ace', options: { "maxLines": 100 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/01_for_wrong_01/01_for_wrong_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/01_for_wrong_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/01_for_wrong_01/) |


The above code is fine, in that;

- it obviously works
- and it is not _too_ complicated.

However, what if you wanted to draw 100 circles, or 1000, circles, or tens-of-thousands of circles? Do you really want to copy and paste 10,000 of the same lines of code? And what if you need to change something in one of the lines after the fact? Are you going to change each line? **OBVIOUSLY NO!**

If we want to eloquently accomplish the above, we are going to need to use a more efficient structure for our code.
