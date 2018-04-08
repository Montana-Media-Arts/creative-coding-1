---
title: Array of Objects
module: 11
jotted: true
---

# An Array of Objects

Now that we can think in terms of objects, let's look at using an array to manage a large number of objects.

Arrays, as you already know, can hold any collections of any data type. Which means they can also hold a collection of objects!

If an array is just a collection of objects, we can address each array element as the object variable.

## Creating an Array of Objects

To create an array of objects, we simply need a loop in our `setup()` function that will _push_, _n_ number of objects into the array. This might look like;

```js
let dudes = [];
let num_of_dudes = 20;
let bg_color;

function setup() {
    createCanvas(windowWidth, windowHeight);
    bg_color = color(34, 131, 157);

    for (let i = 0; i < num_of_dudes; i++) {
        dudes.push( new MarchingDude() );
    }
}
```

Since the class handles all of the "nitty-gritty" during the construction of new objects, we simply need to use the `new` keyword and pass the new object into the array.

## Calling Objects

As you will see in the code below, the class we are using for this example has three methods that need to be executed every frame. However, in the class definition, there is an additional method, called `.frame()`. This method calls the other methods.

To call a method from within an object, use _this dot_ notation! (i.e. `this.someMethod()`);

In the class definition, the `frame()` method looks like;

```js
frame() {
    this.feetAngle();
    this.display();
    this.move();
}
```

Then, in the `sketch.js` file, the `draw()` function simply needs to call the `.frame()` method for every object. To do this, simply use a for loop to work through the array.

```js
function draw() {
    background(bg_color);

    for (var i = 0; i < dudes.length; i++) {
        dudes[i].frame();
    }
}
```

## Altogether

The final code and example looks like;


<div id="jotted-demo-1" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/11/02_dudes_array_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/02_dudes_array_01/02_dudes_array_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/02_dudes_array_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/11/02_dudes_array_01/) |


# Shiffman on Arrays of Objects

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/fBqaA7zRO58" frameborder="0" allowfullscreen></iframe></div>

The code from Shiffman's example is below;



<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/11/03_shiffman_bubbles_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/03_shiffman_bubbles_01/03_shiffman_bubbles_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/11/03_shiffman_bubbles_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/11/03_shiffman_bubbles_01/) |
