---
title: background()
module: 3
jotted: true
---

# `background()`

Now that we can create a canvas to draw to, lets talk about how we can change the color of that canvas. To do this, we will use the `background()` function.

This function, which is often written in `setup()` specifies the background color of a code sketch's canvas.

To write a command to change or set the background, we will often use the `background()` function. Below is the documentation from the p5 site for the `background()` function.

There will be a lot of information inside of the `background()` documentation that does not yet make sense to you. That is OK. But, please read through it and see how much you can understand.

([Link to `background()` function documentation](https://p5js.org/reference/#/p5/background))

<div class="embed-responsive" style="padding-bottom:80%; border: 1px solid #000"><iframe class="embed-responsive-item" src="https://p5js.org/reference/#/p5/background" frameborder="0" allowfullscreen></iframe></div>


After reading the `background()` documentation, you should have found out how you can specify a background color for your code sketches.

There are many ways to specify colors in p5. We will look at a couple of these this week.


## Named Color String

The first, and perhaps easiest way of specifying a color is by providing a "named color string". We will talk about "strings" more later, but essentially, a string is any set of characters that are placed between double or single quotes. (`"This is a string"`, `'This is also a string!'`).

For any function in p5 that accepts a named color string, we can supply any common color, as a word, surrounded by quotes.

Let's first create a 'blue' background. To do this, we will supply the string `'blue'`, as the first parameter to the `background()` function, inside of our declared `setup()` function.



{% highlight js linenos %}
function setup() {
    // first we need to specify our canvas size
    createCanvas( 800, 400 );

    // Then we can color this background
    // Notice how the word 'blue' is surrounded in quotes
    background('blue');
    // Try replacing the word 'blue' with other common color names.
    // NOTE: Be sure to keep the word surrounded with quotes.
}
{% endhighlight %}


<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/03/04_background_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

#### { TODO: }

In the above code output section, open the "JavaScript" tab and replace the `'blue'` string parameter inside the `background()` function with other common color names. Then re-open the "Result" tag to see the changes.

Names to try;

- `'black'`
- `'red'`
- `'green'`
- `'grey'`
- `'beige'`
- `'yellow'`
- `'brown'`
- `'magenta'`
- `'pink`
- `'orange'`
