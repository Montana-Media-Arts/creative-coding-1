---
title: Order of Operations
module: 4
jotted: true
---

# Order of Operations

Order of operations matters greatly in code. As has already been demonstrated with both the 2D Primitive Shape functions, and the transformation functions. The order in which things are placed effects everything else.

For example, when we created the smiley face for the transformation pages, the order that we specify various shapes is critical. This is because, with shapes, the last shape is the one placed on top of the previous shapes. Since we want our smiley face to have a mouth and eyes, it is critical that those are placed **after** the statement to draw the head.

Likewise, in order to make the head "yellow" we must place the appropriate `fill('yellow');` function before the head is drawn. Likewise, we have to place the `fill('black');` function after the head is drawn and before the eyes/mouth are drawn in order for those elements to be colored correctly.

Let's take a look at two examples of the smiley face. In both cases, we will add an alpha value to the head color, so that we can see if something gets placed behind it. In the first example, we will try to draw the eyes and mouth first, and notice that they are 'covered' by the head. Whereas, in the second version, all is as expected.

```js
/* WRONG ORDER */
translate( 150, 75 );
// ** draw the smiley face mouth **
arc( 0, 15, 75, 50, 0, PI );

// ** draw smily face eyes **
// ** left eye **
ellipse( -20, -15, 20 );
// ** right eye **
ellipse( 20, -15, 20 );

// ** draw the smily face head **
stroke( 0 );
fill('rgba(234, 255, 61, 0.8)');
ellipse( 0, 0, 100 );

// add fill information for eyes and mouth
noStroke();
fill( 40, 255 );


/* CORRECT ORDER */
translate( 0, 150 );
// ** draw the smily face head **
stroke( 0 );
fill('rgba(234, 255, 61, 0.8)');
ellipse( 0, 0, 100 );

// add fill information for eyes and mouth
noStroke();
fill( 40, 255 );

// ** draw the smiley face mouth **
arc( 0, 15, 75, 50, 0, PI );

// ** draw smily face eyes **
// ** left eye **
ellipse( -20, -15, 20 );
// ** right eye **
ellipse( 20, -15, 20 );
```

<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/04/14_order_smiley_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/04/14_order_smiley_01/14_order_smiley_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/04/14_order_smiley_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/04/14_order_smiley_01/) |



<br />
<br />
<br />


Likewise, remember how the `rotate()` function rotates _around_ the (x:0, y:0) point on the grid, that is why it is critical that rotate typically comes _after_ translate. Otherwise, you are likely to rotate your shapes **_OFF_** the canvas.

> Note: If you are using `rotate()` and can't see your shapes, check your order of operations, there is a good chance you "rotated" your image off the canvas.

Also, the scale function, changes the grid layout, therefore, it is important that you carefully consider order between `scale()`, `translate()`, and `rotate()`.

<br />


Your homework this week asks you draw a portrait (more to come later). In creating this sketch, you will need to think carefully about order of operations for your functions. Both for transformations, and shape placement.
