---
title: JS Objects
module: 6
jotted: true
---

# JavaScript Objects

There are ways in JavaScript, to store more than one variable inside a variable! One way to do this is with JavaScript _objects_.

We will learn later, that JavaScript objects are very special, capable of many things in the language. But, for the time being, we can more simply think of it as a way of collecting, organizing, and cleaning up data and variables.

An _object_ can be thought of as a digital _thing_. For example, let's say we have an object called `smiley`, that represents a "smiley face" object. Objects allow us to store qualities about this smiley face within the object. We can define the size, proportions, color, position, etc., all attached to the `smiley` object. This collects this related under a shared name space.

To code such an object in JavaScript, we could first declare a variable name space. This name space then needs to be assigned as an object, using a set of curly brackets (`{}`). Then for each parameter that needs to be added, use a "dot notation" to create additional name spaces within the object. We can use this same dot notation to return the stored data. This is seen in the following code.

```js
// define a smiley variable.
// instantiate the variable as an object
var smiley = {};

// we can then assign qualities to the object
smiley.size = 150;
smiley.eye_mouth_y = -35;
smiley.color = 'yellow';
smiley.mouth_h = 50;

// to return a specific object property
// use the same dot notation
smiley.size // returns 150
```

The following code, demonstrates the entire use of the above example, showing the subsequent re-assignment of properties, and use of all properties to draw a smiley face.

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
// define a smiley variable.
// instantiate the variable as an object
var smiley = {};

// we can then assign qualities to the object
smiley.size = 150;
smiley.eye_mouth_y = -25;
smiley.color = 'yellow';
smiley.mouth_h = 90;
smiley.pos_x = 0;
smiley.pos_y = 0;

function setup() {
    createCanvas( windowWidth, windowHeight );
    background( '0' );

    smiley.pos_x = width/2;
    smiley.pos_y = height/2;
}


function draw() {

    // draw the smiley
    translate( smiley.pos_x, smiley.pos_y );

    fill( smiley.color );
    ellipse( 0, 0, smiley.size );

    fill('black');
    ellipse( smiley.eye_mouth_y, smiley.eye_mouth_y, smiley.size * 0.25 );
    ellipse( -smiley.eye_mouth_y, smiley.eye_mouth_y, smiley.size * 0.25 );

    arc( 0, -smiley.eye_mouth_y, smiley.size * 0.8, smiley.mouth_h, 0, PI );

    // update pos
    smiley.pos_x += random( -2, 2 );
    smiley.pos_y += random( -2, 2 );
}
{% endhighlight %}


    <div id="jotted-demo-3" class="" style="height:600px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/06/11_object_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/11_object_01/11_object_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/06/11_object_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/06/11_object_01/) |

## Instantiating Objects with Properties

To add property values during instantiation, include them within the curly brackets. Each property is added as a unique name space, appended with a colon (`:`), and the associated data placed following. These become "name/value" pairs.

```js
var myObject = {
    property1: "some data"
}
```

To add multiple properties, separate each "name/value" pair with a comma (`,`).

```js
var myObject = {
    property1: "some data",
    property2: "some more data"
}
```

These properties are accessed the same as above, using dot notation.

## Nested Objects

Objects can be nested within objects.

To nest an object, simply assign an object to another object's property.

```js
// creating a nested object during instantiation
var myObj = {
    property1: "first level data",
    nestedObj: {
        pOne: 1,
        pTwo: 2
    },
    property2: "the last piece of data"
}

// adding an object to another objects property
// through dot notation
var myOtherObj = {};
myOtherObj.innerObj = { innerProp: "inner property", ip2: 2 };
```

To access properties nested inside properties, continue the dot notation. The above, first example, could have the `pOne` property access with;

```js
myObj.nestedObj.pOne
```

# { TODO: }

Please read the following page on JS Objects.

- [JSON Objects](https://www.w3schools.com/js/js_json_objects.asp)

Please watch the following Shiffman video.

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/-e5h4IGKZRY" frameborder="0" allowfullscreen></iframe></div>
