---
title: Reusing Code
module: 10
jotted: true
---

# Reusing Code with Functions

Functions can also be useful, and should be used, to reduce repetitions in code. That is, if you are repeating lines of code, you should likely encapsulate it in a single function that can be called.

For example, [back in Week 4]({{site.baseurl}}/modules/week-4/scale/), the following code was used to demonstrate that use of the `scale()` function. This code draws four smiley faces with various scale factors.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup(){
    createCanvas( windowWidth, 600 );
}

function draw() {
    // set the background to 'white'
    background(255);

    // NO SCALING
    translate( 75, 75 );
    // ** draw the smily face **
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );

    // scale by 200%
    scale(2.0);
    translate( 75, 75 );
    // ** draw the smily face **
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );

    // scale by 50%
    translate( -75, 75 );
    scale(0.5);
    // ** draw the smily face **
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );

    // scale by 50%
    translate( 0, 125 );
    scale(0.5);
    // ** draw the smily face **
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );
}
{% endhighlight %}


<div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/10/03_reusable_code_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

<br />


As you can see in the above code, each time the smiley face was drawn, the code to do so had to be repeated.

With functions, we can _refactor_ our code by encapsulating the repeated portions in a function. This new function would then be called instead. This will greatly shorten our code, and increase its readability.

### Breaking it Down

#### Function Namespace

The first step to _refactor_ the above code, might be define the function's namespace.

In this case, we can stick with something simple like;

```js
function smileyFace() {

}
```

#### Function Outline

The next step might be to outline the function and identify steps it must complete.

As we can see from the above code, each smiley block (lines 9-19, 21-32, 32-45, and 47-58), perform two basic tasks, to position and scale the smiley face, and to actually draw a smiley face. So our function might need the following steps;

```js
function smileyFace() {
    // 1. scale and position smiley face

    // 2. draw smiley face

}
```

#### Fill in the Outline

To fill the outline, in this case at least, we can copy and paste from our code. We know we want to draw the same smiley face, so I will move lines 11-19, from the code above into our new `smileyFace()` function.

```js
function smileyFace() {
    // 1. scale and position smiley face

    // 2. draw smiley face
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );
}
```

We also know we want this function to handle the positioning and scaling of the smiley face. Let's start by adding translate, and scale functions to outline #1.

```js
function smileyFace() {
    // 1. scale and position smiley face
    translate(  );
    scale( );

    // 2. draw smiley face
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );
}
```

Also, since we know we are handling translate and scale in the function, we should consider creating a push/pop sandbox, so that the functions execution will not effect other drawing statements.

```js
function smileyFace() {
    push(); // <- Begin sandbox

    // 1. scale and position smiley face
    translate(  );
    scale( );

    // 2. draw smiley face
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );

    pop(); // <- End sandbox
}
```

Finally, we need to be able to specify the translate and scale parameter values. We could do this through random number generators within the function. However, let's be more purposeful with this example. This means we need to pass in values which can be used for translate and scale. This also means we need to include input parameters to the function we are building. These parameter names should be something like;

- `pos_x`
- `pos_y`
- `scale_x`
- `scale_y`

Incorporating these into our function would cause it to look like;

```js
function smileyFace( pos_x, pos_y, scale_x, scale_y ) {
    push(); // <- Begin sandbox

    // 1. scale and position smiley face
    translate( pos_x, pos_y );
    scale( scale_x, scale_y );

    // 2. draw smiley face
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );

    pop(); // <- End sandbox
}
```

We can then use our function by calling something like;

```js
smileyFace( 40, 100, 1.5, 1.0 );
```

The above, would call the smileyFace function, which would draw a smiley face at `x:40, y:40`, with scale factors of `width:1.5, height:1.0`.

We could then also call lots of these smiley faces. In the below example, we call four, just like the original.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup(){
    createCanvas( windowWidth, 600 );
}

function draw() {
    // set the background to 'white'
    background(255);


    smileyFace( 40, 100, 1.0, 1.0 );
    smileyFace( 200, 100, 1.5, 1.0 );
    smileyFace( 200, 200, 0.5, 0.4 );
    smileyFace( 300, 250, 0.9, -3.0 );

}


/* SMILEY FACE FUNCTION */
function smileyFace( pos_x, pos_y, scale_x, scale_y ) {
    push(); // <- Begin sandbox

    // 1. scale and position smiley face
    translate( pos_x, pos_y );
    scale( scale_x, scale_y );

    // 2. draw smiley face
    stroke( 0 );
    fill('rgba(234, 255, 61, 1.0)');
    ellipse( 0, 0, 100 );
    noStroke();
    fill( 40, 255 );
    arc( 0, 15, 75, 50, 0, PI );
    ellipse( -20, -15, 20 );
    ellipse( 20, -15, 20 );

    pop(); // <- End sandbox
}
{% endhighlight %}


<div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/10/03_reusable_code_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/10/03_reusable_code_02/03_reusable_code_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/10/03_reusable_code_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/10/03_reusable_code_02/) |
