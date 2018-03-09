---
title: For Loops and Drawing
module: 8
jotted: true
---

# For Loops and Drawing

A very common use of _for loops_ is to _do something_ from one place on a screen, to another place on a screen. For example, you may find yourself wanting to do something, or rather the same things, from the left area of a canvas (`x=0`), to the right edge of a canvas (`x=width`).

In this situation, you will likely setup your _for loop_ such that;

1. the variable declaration’s name is meaningful to the task at hand. If you are working across the x-axis, `x` may be the most suitable.
2. You will want to initialize this value to the left-edge of the area where you want something to occur.
3. The conditional check statement should cause the loop to terminate once it _reaches_ the right-edge of the desired area. Again, if you were working from left-edge to right-edge of a canvas in p5, this likely would be some sort of conditional, checking whether the variable is at or past the canvas’ `width` ( `x < width` ).
4. Finally, for the _update statement_, this should cause the variable’s update to reflect the movement across the screen that you are trying to accomplish. Let’s say you wanted to draw circles across the screen’s x-axis, starting at `x=0` and terminating at `x=width`. You would obviously set up the _for loop_ so that it started at 0 and ended at `width`. The _update statement_ will be dependent on the desired size and spacing of the circles. For example, if we want circles with a width of 50px, that touch, then our update value will likely need to be `x+=50`.

This example is shown in one possible solution below, with the description for the circles applied to both the x-axis and y-axis.

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-1"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/06_for_loops_drawing_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/06_for_loops_drawing_01/06_for_loops_drawing_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/06_for_loops_drawing_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/06_for_loops_drawing_01/) |



## Drawing A Diagonal Series

What if you wanted to draw a diagonal series on a canvas that what not square? The problem is obviously that we cannot use the same variable to describe the position of an object for both the x-axis and y-axis.

The following example utilizes the properties we have been talking about, applied to the problem of drawing a diagonal line of objects across a screen of indeterminate length.


<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-2"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/07_for_diagnolDrawing_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/07_for_diagnolDrawing_01/07_for_diagnolDrawing_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/07_for_diagnolDrawing_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/07_for_diagnolDrawing_01/) |
