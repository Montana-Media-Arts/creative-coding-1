---
title: Nested for Loops
module: 8
jotted: true
---

# Nested for Loops

Building from the last page, how could you use a for loop to _do something_ across both axis of the entire screen? I.E. In every row and every column? Essentially touching the entire grid?

The _brute force_ way, would be to write a for loop that does something across the X-axis. Like the following, which currently draws a line of circles across the X-axis;


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-1"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/08_nested_loops_SingleLine_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/08_nested_loops_SingleLine_01/08_nested_loops_SingleLine_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/08_nested_loops_SingleLine_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/08_nested_loops_SingleLine_01/) |



<br />

Then to add another row, below the first, we could simply, copy, paste, and update where the Y-axis position will be.

<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-2"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/08_nested_loops_BruteForce_02/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/08_nested_loops_BruteForce_02/08_nested_loops_BruteForce_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/08_nested_loops_BruteForce_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/08_nested_loops_BruteForce_02/) |


<br />

This, of course, raises the same issues, and inefficiencies discussed back on the first page of this weeks content. Specifically, that this is fine for a small number of iterations. But is impractical for larger numbers. It also suffers from the problem of not being easily editable. (If you want to change one thing, you must do so in every place that it occurs.)

Obviously, instead, we should create some sort of looped process to automate the task...

**_LIKE A FOR LOOP!_**

The eloquent solution is to create a second _for loop_ that handles the movement of the for loop drawing circles across rows on the X-axis. This additional for loop will cause the X-axis for loop to move down every iteration, thereby drawing a new row.

The code for this might look something like the following;


<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-3"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/08_nested_loops_CORRECT_03/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/08_nested_loops_CORRECT_03/08_nested_loops_CORRECT_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/08_nested_loops_CORRECT_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/08_nested_loops_CORRECT_03/) |


With 2 additional lines of code, it becomes possible to execute any number of X-axis-based for loops.

The _outer for loop_ essentially handles specifying the Y-position. You will notice that this outer for lop defines and uses the Number variable `y`, which is passed as the "y" parameter to the ellipse function.

As before in the above examples, the _inner for loop_ handles the placement of circles along the X-axis.

<br />

For the moment, lets assume that the variable `pad` is set to 100.

In this scenario, the _outer for loop (Y-Loop)_, is initialized such that `y=50` (or the circleSize variable’s value). This for loop then executes the contents of its _function block_. This of course contains the _inner for loop (X-Loop)_.

This _inner for loop (X-Loop)_ initializes the variable `x` to the value of 50, or `circleSize`. Since this is less than `width`, it executes its _function block_ contents. Which create a random color and draws a circle, positioned at the values of `x` and `y` or (x:50, y:50).

Upon completion of this process, the _inner for loop (X-Loop)_ then updates its variable value by adding 100 to `x`, or the value of `pad`. The _inner for loop (X-Loop)_ then checks whether this is less than `width`. Since it is, the _inner for loop (X-Loop)_ executes its function block again. This time drawing a circle at (x:150, y:50). For a window that is 300px wide, this process would occur one more time, drawing a circle at (x:250, y:50). After the execution and drawing of this circle, the _update statement_ would set `x` to 350. The _conditional statement_ would return `false`, meaning `x` is greater than `width`. In this case, the _inner for loop (X-Loop)_ exits.

Since the _inner for loop (X-Loop)_ is wrapped in the _outer for loop (Y-Loop)_, this for loop then has to check its state and values. At the end of execution of the _inner for loop_, the _outer for loop (Y-Loop)_ executes its _update statement_ thereby setting `y` tp 150. Assuming a canvas with a height of 200, the _conditional statement_ would return `true` that `y` is less than `height`. In which case, the _outer for loop (Y-Loop)_ would execute its function block again. This would result in the _inner for loop (X-Loop)_ executing again, as though it had not before. The variable `x` will be re-initialized and defined to the value of `circleSize` or 50. It will therefor execute 3 times again, drawing circles at;

- (x:50, y:150)
- (x:150, y:150)
- (x:250, y:150)

Afterwards, the _inner for loop_ would exit again, return control to the _outer for loop_ again. This would continue until the `y` value is greater than `height`, thereby triggering the _outer for loop_ to exit.


# More Examples

Please look at the following examples from “Make: Getting started with p5”. Notice how with slight modifications, quite interesting patterns can be achieved.


### Example 1 of more nested for loops


<div id="jotted-demo-4" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-4"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/09_nested_loops_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/09_nested_loops_01/09_nested_loops_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/09_nested_loops_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/09_nested_loops_01/) |



### Example 2 of more nested for loops


<div id="jotted-demo-5" class="jotted-theme-stacked"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-5"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/10_nested_loops_02/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/10_nested_loops_02/10_nested_loops_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/10_nested_loops_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/10_nested_loops_02/) |



### Example 3, Crazy Options

NOTE: Click with your mouse on the next example.


<div id="jotted-demo-6" class="jotted-theme-stacked" style="800px;"></div>

<script>
	new Jotted(document.querySelector("#jotted-demo-6"), {
	files: [
		{
			type: "js",
			url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/11_nested_for_03/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/11_nested_for_03/11_nested_for_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/11_nested_for_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/11_nested_for_03/) |
