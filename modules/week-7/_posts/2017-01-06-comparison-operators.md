---
title: Comparison Operators
module: 7
jotted: true
---

# Comparison Operators

As mentioned earlier in this week's lesson, "the Boolean is sometimes known as the _truth value_, which is a ["value indicating the relation of a proposition to truth"](https://en.wikipedia.org/wiki/Truth_value)." In other words, a Boolean value is the result of _evaluating_ a _proposition_ for _truth_.

<br />


As an example, if I said;

- "Oxygen is required for humans to survive."

You would agree that to be a _true_ statement.

<br />


Likewise, if I said;

- "All trees in the world are purple!"

You would politely inform me that to be a _false_ statement.


<br />

> **Boolean Evaluations**
>
> In computer science, Boolean evaluations result in a statement returning _true_ or _false_.

Boolean evaluations often occur as a result of using a _comparison operator_ also known as _relational operator_. A _comparison operator_ is used to compare two values about their relationship to each other.

## Equality Operator

The first comparison operator to discuss is the _equality operator_. The equality operator compares two values to see if they are equal.

As an example, if we asked whether the _Number 4 is equal to the Number 4_, the result would be _true_.


<br />

The _equality operator_ is two equal sign characters placed together (`==`). The values that are being assessed for equality are placed on either side of the operator.

The above discussed example would look like the following in JavaScript code;

```js
4 == 4; // returns 'true'
```

The result of this statement (or any statement using _comparison operator's_) can be passed as the input parameter to the if statement. This can be done directly (i.e. calling the _comparison operator_ statement inside of the if statement), or through the use of a variable.

```js
if( 4 == 4 ) {
    // The statement results in the
    // 'true' function block being executed.
}

var eqResult = 4 == 4;
if( eqResult ) {
    // same result as above occurs.
}
```

> NOTE: You are going to accidentally swap out the _equality comparison operator_ and the _variable assignment_ operator. Be on the look out, and hyper-vigilent, that you are using **1** equal sign character to assign variables (`var der = 4;`), and **2** equal sign characters to compare for equality (`if( 4 == 4 )`).

The following example uses the _equality comparison operator_ to change the background color of the sketch. There is a variable, `loopNum`, which is incremented by `1` every frame. When this value equals `4`, then background of the sketch is changed from 'red' to 'purple'.

<div id="code-heading">sketch.js</div>

```js
// initialize bgColor and loopNum variables
var bgColor = 'red';
var loopNum = 0;

function setup() {
    createCanvas( windowWidth, 300 );
    // set a low frame rate so that you can see the change
    // frameRate is set to 1 frames per second
    frameRate(1);

    // adjust text display
    textSize(36);
    textAlign(CENTER,CENTER);
}

function draw() {
    // set the fill color for an ellipse
    if( loopNum == 4 ) {
        bgColor = 'purple';
    } // no need for an else function block

    // set and replace background
    background( bgColor );

    // display the current loopNum
    text( "loopNum = " + loopNum, width/2, height/2 );

    // increment the loopNum variable
    loopNum++;
}
```


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/05_equality_op_01/sketch.js"
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
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/05_equality_op_01/05_equality_op_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/05_equality_op_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/05_equality_op_01/) |



By combining some arithmetic operators, we can start to compose more complex sketches.

In the following sketch, a ball that moves across the screen has its fill color randomly set every 30 frames. To do this;

- The variable `x_pos` is incremented by `1` every frame.
- This incrementing value is evaluated against modulo 30 (` x_pos % 30`) and stored to the variable `fill_counter`.
- `fill_counter` is compared for equality to the value of `0` within the _if statement_, where when true, a random color value is calculated, and stored in the variable `ball_color`.

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
// initialize bgColor and loopNum variables
var ball_color;
var fill_counter = 0;
var x_pos = 0;

function setup() {
    createCanvas( windowWidth, 300 );
    // initialize ball color
    ball_color = color(200, 200, 200, 5);
    background('white');
}

function draw() {
    // increment x position value
    x_pos++;
    // bound the value within the canvas width
    x_pos %= width;

    // calculate fill counter value
    fill_counter = x_pos % 30;

    // check if fill counter equals 0
    if( fill_counter == 0 ) {
        ball_color = color(
            random(255),
            random(255),
            random(255),
            5
        );
    } // no else needed

    // draw the ball
    noStroke();
    fill( ball_color );
    ellipse( x_pos, height/2, height );
}
{% endhighlight %}


<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/05_equality_op_02/sketch.js"
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
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/05_equality_op_02/05_equality_op_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/05_equality_op_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/05_equality_op_02/) |


## Inequality Operator

The counterpart to the equality operator is the _inequality operator_. The _inequality operator_ returns _true_ when two values **do not** equal each other.

The _inequality operator_ is an exclamaition mark and equals sign placed together (`!=`).

In the following, the background of a canvas is randomly set every frame as long as a random number generator _does not_ return 0. Once '0' is found, no more numbers are searched, and the background turns 'pink'. There is also text in each of the function blocks to update the user on the state of the machine.

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 300 );
    // adjust text display
    textSize(36);
    textAlign(CENTER,CENTER);
}

var searchNum = -10000;

function draw() {

    if( searchNum != 0 ) {
        background( random(255), random(255), random(255) );
        text("searching for 0...", width/2, height/2);

        // get a new number to try next time
        searchNum = floor(random(200));
    } else {
        background( 'pink' );
        // after finding a random 0, celebrate
        text("Found a random 0!!!", width/2, height/2);
        text("click the mouse to try again", width/2, height*0.75);
    }
}



// a mouse event to run it again
function mousePressed() {
    searchNum = -1000;
}
{% endhighlight %}


<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/06_inequality_01/sketch.js"
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
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/06_inequality_01/06_inequality_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/06_inequality_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/06_inequality_01/) |

## Less Than and Greater Than

Another way of comparing numerical relationships is whether one value is _less than_ or _greater than_ another value.

As you may remember, traditionally, the _less than_ and _greater than_ operators in algebra are carets, which show which way the comparison is occurring. I.E. When checking whether the left value is _greater than_ the right value, a caret with an opening on the left is used. Likewise, when checking if the left value is _less than_ the right value, a caret with the small end on the left is used. This is true for the JavaScript version operators as well.

```js
// is 5 greater than 4
5 > 4; // ⇒ true

// is 5 less than 4
5 < 4; // ⇒ false
```

## Less Than or Equal To and Greater Than or Equal To

As with algebra, JavaScipt can also check whether a value is _greater than or equal to_ or _less than or equal to_. These _comparison operators_ append an equal sign character to the relevant comparison operator from the section above.

```js
<= // ⇒ 'less than or equal to'
>= // ⇒ 'greater than or equal to'
```

As with the above operators, the _greater than or equal to_ and _less than or equal to_ operators check if the value the relationship of the value on the left of the operator to the one on the right.

```js
// is 5 'greater than or equal to' 4
5 >= 4; // ⇒ true

// is 4 'greater than or equal to' 4
4 >= 4; // ⇒ true

// is 3 'greater than or equal to' 4
3 >= 4; // ⇒ false

// is 3 'less than or equal to' 4
3 <= 4; // ⇒ true
```

## Comparison Operator Examples

As an example of the comparison operators, the following, sets the background of the canvas to be black `if` the mouse's X position (`mouseX`), is greater than the middle of the canvas (`width/2`). Otherwise, the background color is set to white.

<div id="code-heading">sketch.js</div>

```js
function draw() {
    // If the mouse position is greater than the
    // middle of the screen (width/2), set the
    // background to black, otherwise, set the
    // background to white.
    if (mouseX > width / 2) {
        background(0);
    } else {
        background(255);
    }

    // draw a line in the middle
    stroke('red');
    line(width/2, 0, width/2, height);
}
```


<div id="jotted-demo-5" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-5"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/08_comparison_op_01/sketch.js"
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
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/08_comparison_op_01/08_comparison_op_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/08_comparison_op_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/08_comparison_op_01/) |

## Shiffman on Conditional Statements

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/1Osb_iGDdjk" frameborder="0" allowfullscreen></iframe></div>


## Shiffman Making a Bouncing Ball

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/LO3Awjn_gyU" frameborder="0" allowfullscreen></iframe></div>

<div id="code-heading">sketch.js</div>


{% highlight js linenos %}
var x = 300;
var speed = 5;

function setup() {
    createCanvas(windowWidth, 400);
}

function draw() {
    background(0);

    stroke(255);
    strokeWeight(4);
    noFill();
    ellipse(x, height / 2, 100, 100);

    if (x > width) {
        speed = -3;
    }
    x = x + speed;
}
{% endhighlight %}


<div id="jotted-demo-6" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-6"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/09_bouncing_ball_01/sketch.js"
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
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/09_bouncing_ball_01/09_bouncing_ball_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/09_bouncing_ball_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/09_bouncing_ball_01/) |
