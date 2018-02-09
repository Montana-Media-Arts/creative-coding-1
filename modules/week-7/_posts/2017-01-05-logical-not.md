---
title: Logical Not
module: 7
jotted: true
---

# Alternating Boolean States

Hopefully, you realized from the last example, that if we can tell a Boolean variables to alternate its value between `true` and `false`, we could easily change the state of a sketch. We could use this changing state to alternate or flicker the color fill of the ellipse form the last page between red and blue.

There are two easy ways of alternating a Boolean variables state or value between `true` and `false`;

1. Use an if statement.
2. Use the _logical not_ operator.

## Alternating States through IF

If we can check a variable's Boolean state, we can change it to the opposite state. To do this, after checking it, we can re-assign the variable to `false` in the _true function block_ or `true` in the _false function block_. In other words,

- _if_ the variable equals _true_
    - set the variable to _false_
- _else if_ the variable equals _false_
    - set the variable to _true_

In code, this would like like;

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
var boolState = true;

function draw() {
    // check the variable's Boolean state
    if( boolState ) {
        // if true, set to false
        boolState = false;
    } else {
        // if false, set to true
        boolState = true;
    }
}
{% endhighlight %}

In the above code, we;

1. Declare and initialize a variable `boolState` to be `true`
2. In line 5, we pass the value of the variable to the if statement function.
3. If the value passed equals _true_, then we alternate the state of `boolState` to _false_ in line 7.
4. Likewise, if the value passed equals _false, then we alternate the state of `boolState` to _true_ in line 10.
5. With each passing of the `draw()` loop, the state of `boolState` will alternate between _true_ and _false_.

This is also demonstrated more fully in the below code. The following example builds on the previous, by using the value of `boolState` to also change the value of a variable holding onto color values `fillColor`, between `'red'` and `'blue'`. This is then passed to the `fill()` function, which results in the alternating color of the ellipse. The value of the Boolean variable, `boolState`, is also displayed as text.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 300 );
    // set a low frame rate so that you can see the change
    // frameRate is set to 2 frames per second
    frameRate(2);

    // adjust text display
    textSize(36);
    textAlign(CENTER,CENTER);
}

// declare an initialize global variables
var boolState = false;
var fillColor;

function draw() {
    background('black');

    // set the fill color for an ellipse
    if( boolState ) {
        // switch bool variable state
        boolState = false;
        // set fill color
        fillColor = 'red';
    } else {
        // switch bool variable state
        boolState = true;
        // set fill color
        fillColor = 'blue';
    }

    // display text and ellipse
    // fill color dependent on boolState
    fill( fillColor );
    text( boolState, width/2, height/4 );
    ellipse( width/2, height/2, 80 );
}
{% endhighlight %}


<div id="jotted-demo-1" class="jotted-theme-stacked" style="300px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/03_bool_state_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/03_bool_state_01/03_bool_state_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/03_bool_state_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/03_bool_state_01/) |


## Logical Not

Before we look at the second method for alternating Boolean state, we need to discuss another operator first.

The new operator is the _Logical Not Operator_. This new operator is similar to the [_Unary Negative Operator_]({{site.baseurl}}/modules/week-6/math/#unary-operators). The _Unary Negative Operator_ flips the sign of a Number value. The _Unary Negative Operator_ (`-`) is proceeded by a Number or a variable holding a Number, (i.e. `-10` or `-num_var`).

> A _unary operator_ is called as such, because it only effects a single parameter or value. As opposed to a _binary operator_ (i.e. `+`, `-`, `*`, `/`, `%`), where with a value on each side, the program tries to computer the arithmetic result of both numbers together.

```js
// negative 10
-10

// store -22 in a variable.
var num_var = -22;
// the following returns +22
-num_var;
```

The _Logical Not Operator_ is another _unary operator_, that is applied or used with a single Boolean value. This operator returns the opposite of the Boolean state. In other words, using this operator with a Boolean value of _true_, returns _not true_ or _false_. Likewise, using this with a Boolean value of _false_ return _not false_ or _true_.

The _Logical Not Operator_ is the exclamation mark (`!`). As with the _Unary Negative Operator_, the _Logical Not Operator_ is used by preceeding the value it is to act on.

```js
!true // ⇒ would result in "not true" or false.
```

In the below code example, _not true_ (`!true`) is passed to the if statement. As a result the _false function block_ is the one executed by the program.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 300 );
    background('black');

    // adjust text display
    fill('white');
    textSize(36);
    textAlign(CENTER,CENTER);

    var textStr;

    // pass in "NOT" true
    if( !true ) {
        // this block DOES execute
        textStr = "The result was TRUE";
    } else {
        // THIS BLOCK DOES EXECUTE
        textStr = "The result was FALSE";
    }

    // display the results of the if statement
    text( textStr, width/2, height/2 );
}
{% endhighlight %}


<div id="jotted-demo-2" class="jotted-theme-stacked" style="300px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/04_logical_not_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/04_logical_not_01/04_logical_not_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/04_logical_not_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/04_logical_not_01/) |

In the following sketch, the value of `!false`, is added to a string and printed. This further demonstrated that the use of the _Logical Not Operator_ returns the opposite of a Boolean value state.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 300 );
    background('black');

    // adjust text display
    fill('white');
    textSize(36);
    textAlign(CENTER,CENTER);

    var textStr;

    textStr = "!false ⇒ " + !false;

    // display the results of the if statement
    text( textStr, width/2, height/2 );
}
{% endhighlight %}


<div id="jotted-demo-3" class="jotted-theme-stacked" style="300px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/04_logical_not_02/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/04_logical_not_02/04_logical_not_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/04_logical_not_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/04_logical_not_02/) |


### Using _Logical Not_ to Alternate Boolean Value State

Following from everything just presented, we can use the _Logical Not Operator_ to return the opposite of a Boolean values state. If the result of this is reassigned back to the same variable, the state of the Boolean variables value has been "flipped". Let's alter the above example that demonstrated how to flip the state of a Boolean variable value using _if statements_.

Now, instead of reassigning the value in an _if statement_, we will use the _Logical Not Operator_ to return the opposite of the current state, and then reassign that to the same `boolState` variable. This will occur at the top of the draw loop (line 21). Then we can reduce the number of extraneous lines in the _if statement_.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
function setup() {
    createCanvas( windowWidth, 300 );
    // set a low frame rate so that you can see the change
    // frameRate is set to 2 frames per second
    frameRate(2);

    // adjust text display
    textSize(36);
    textAlign(CENTER,CENTER);
}

// declare an initialize global variables
var boolState = false;
var fillColor;

function draw() {
    background('black');

    // switch bool variable state
    // use "logical not operator"
    boolState = !boolState;

    // set the fill color for an ellipse
    if( boolState ) {
        fillColor = 'red';
    } else {
        fillColor = 'blue';
    }

    // display text and ellipse
    // fill color dependent on boolState
    fill( fillColor );
    text( boolState, width/2, height/4 );
    ellipse( width/2, height/2, 80 );
}
{% endhighlight %}


<div id="jotted-demo-4" class="jotted-theme-stacked" style="300px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-4"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/07/04_logical_not_03/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/04_logical_not_03/04_logical_not_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/07/04_logical_not_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/07/04_logical_not_03/) |
