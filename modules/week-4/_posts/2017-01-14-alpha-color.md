---
title: alpha values in color
module: 4
jotted: true
---

# Alpha Values in Color<br />(Making things see-through)

It is also possible to specify the alpha value for any color in p5. Specifying an alpha value for color function, allows other objects behind the shape to be seen. In other words, it makes a shape "see through".

The alpha value is most easily used in conjunction with grayscale and rgb color values.

To specify an alpha value for grayscale value, supply a second number parameter to any color function, between 0-255. (0 = completely transparent, 255 = completely opaque)

```js
// grayscale value w/ alpha value specified
fill(102, 150);
```

To specify an alpha value with the simple version of RGB parameters, supply a 4th value between 0-255.

```js
// rgb value w/ alpha value
fill( 240, 10, 20, 150 );
```

I like to specify alpha value by passing color functions an `'rgba()'` function wrapped in quotes. This allows the alpha value to be specified as a decimal value between 0.0 - 1.0. Which gives me a greater feel of control.

```js
fill( 'rgba(176, 255, 29, 0.5)' );
```

When placed together, you can see how the alpha values allow for colors to mingle and play with each other.


<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/04/08_alpha_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/04/08_alpha_01/08_alpha_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/04/08_alpha_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/04/08_alpha_01/) |



<br />




> For more information on using colors in p5, please read the [`color` reference page](https://p5js.org/reference/#/p5/color).



# Shiffman on Color

Please watch Mr. Shiffman on his approach to color.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/9mucjcrhFcM" frameborder="0" allowfullscreen></iframe></div>
