---
title: Else If Statements
module: 7
jotted: true
---

# 'Else If' Statements

Let's keep deep diving on conditional flow for our program structure. So far, we have looked at _if statements_, where _if_ a input parameter evaluates to `true` the first function block is executed, _else_ the second function block (which follows the `else` keyword) is executed.

There is also the possibility of including addition conditional tests in an _if statement_ using _else if statements_.

An _else if statement_ looks like the following;

```js
if( someConditionCheck ) {
    // function block 1
    // executed if the above returns 'true'
} else if ( aDifferentConditionCheck ) {
    // function block 2
    // executed if the 'else if' condition is true
} else {
    // function block 3
    // executed if all 'if, else if' statements are 'false'
}
```

This conditional flow program structure can be used to construct more advanced programs!

## Example

Let's look at an example. Say we wanted to set the background of the canvas to one of 3 colors, depending on the mouse X (`mouseX`) position. To do this, we could use the `else if` statement, and check by region.

- In our first conditional check, we would need to check if the mouse X position, is less than one-third of the canvas width.
    - `if( mouseX < width * 1/3 ) {}`
- In the second conditional check, we could check if the mouse X position is less than two-thirds of the canvas width. This would use the `else if()` syntax.
    - `else if( mouseX < width * 2/3 ) {}`
    - This works because if the first condition (`mouseX < width*1/3`) is true, the rest of the conditional statement will be "skipped", so this condition would never be checked.
- Finally, if both of the above return _false_, we can assume the mouse is greater than two-thirds of the canvas width.
    - `else {}`

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup() {
    createCanvas(windowWidth, 300);
}

function draw() {
    // If the mouse position is less than
    // one-third of the screen (width*1/3), set the
    // background to black, otherwise, if the mouse
    // position is less than two-thirds of the screen,
    // set the background to red. Else, if both
    // are false, set the background to orange.
    if (mouseX < width*1/3) {
        background(0);
    } else if(mouseX < width*2/3) {
        background('red');
    } else {
        background('orange');
    }

    // draw lines in the middle
    stroke('white');
    line(width/3, 0, width/3, height);
    line(width*2/3, 0, width*2/3, height);
}
{% endhighlight %}


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/14_else_if_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/14_else_if_01/14_else_if_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/14_else_if_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/14_else_if_01/) |
