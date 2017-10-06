---
title: Readable Code
module: 5
jotted: false
---

# Readable Code

One of the goals, you should hold for yourself as a beginning programmer, is to write code that is _highly readable_.



## White Space - Blank New Lines

In JavaScript white space is ignored by the computer. Therefore, you should feel free to use white space to make your code more "readable". This means you should feel free to use new lines (pressing "return" or "enter"), to separate out sections of code.

Utilizing an example from earlier this week, the following code is for the smiley face that followed the mouse position.

Notice the use of new lines in the below code. There is a blank line, in line no. 3, to visually separate the first variable `smileySize` from the remaining variables, which are all in relation to `smileySize`. This helps me recognize that the first variable is the one that I should change, if adjusting size of the whole smiley face. While I would adjust the ratios for the remaining variables, if any of them felt off.

Likewise, I use blank, new lines, between my variable declaration section on-top, the `setup()` function, and the `draw()` function. This helps my eyes visually distinguish each large code block.

Within the `draw()` function. I use blank lines to visually separate the various statement groups, including the; translate section, head outline section, and mouth/eye section.


{% highlight js linenos %}
// initial variable. Defines smiley face size.
var smileySize = 100;

// all other variables are determined in
// relation to the smileySize variable.
var eyePos_X = smileySize * 0.2;
var eyePos_Y = smileySize * -0.15;
var eyeSize = smileySize * 0.2;
var smilePos_Y = smileySize * 0.15;
var smileWidth = smileySize * 0.75;
var smileHeight = smileySize * 0.50;


function setup() {
    createCanvas( windowWidth, windowHeight );
    background( 'rgb(61, 175, 120)' );
}


function draw() {

    // ** draw the smily face **

    // make the smiley face follow the mouse
    translate( mouseX, mouseY );

    // draw the outline and head
    stroke( 0 );
    fill('rgba(234, 255, 61, 0.5)');
    // note: the head size is based on a variable
    ellipse( 0, 0, smileySize );

    // draw the mouth and eyes
    // note: that their size and position is dependent on the initial smileySize var.
    noStroke();
    fill( 40, 127 );
    arc( 0, smilePos_Y, smileWidth, smileHeight, 0, PI );
    ellipse( -eyePos_X, eyePos_Y, eyeSize );
    ellipse( eyePos_X, eyePos_Y, eyeSize );
}
{% endhighlight %}


## White Space - New Lines

Sometimes, when writing a statement, you may also want to separate out parameters on to new-lines, so that it is easier to read and understand the statement. This can be particularly true for functions, which accept a lot of parameters, especially when you are using variables.

For example, The `arc()` function takes up to seven input parameters. If you were using variables, as in the following statement, it can be hard to read what is happening.

```js
var arc_X = 30;
var arc_y = 20;
var shape_width = 200;
var shape_height = shape_width * 0.5;
var arc_start = 0;
var arc_end = PI;

arc( arc_X, arc_Y, shape_width, shape_height, arc_start, arc_end );
```

If the variables were longer, or we were performing math inside of the function parameter list, that line could get ridiculously long. To fix this, it is sometime appropriate to separate out the parameters on to new lines, with an extra level of indentation.

```js
var arc_X = 30;
var arc_y = 20;
var shape_width = 200;
var shape_height = shape_width * 0.5;
var arc_start = 0;
var arc_end = PI;

arc(
    arc_X,
    arc_Y,
    shape_width,
    shape_height,
    arc_start,
    arc_end
);
```

Note: that in the above, the closing parenthesis is placed on its own line, at the same indent level as the function name and opening parenthesis.

## White Space - Within Lines

Another area that can become difficult to read, is individual lines of statements themselves. One solution, as just presented, is to use new-lines to logically break up long lines of code. However, sometimes the problem is just reading what is going on in a single short line.

For example, the following is short enough, but might be difficult to read, as it all runs together.

```js
var der=(width*0.5)/height+1000;
ellipse(der,der,der*2.1);
```

The above is not horrendous, but some additional spaces, could help visually separate out what is happening.

I would suggest the following;

```js
var der = (width * 0.5) / height + 1000;
ellipse( der, der, der * 2.1 );
```

In the above, by placing spaces on either side of operators, it becomes easier to see, that some sort of mathematical calculation is occurring. Likewise, placing spaces after comma-separated parameters makes it easier to read each parameter to a function.

## Tabs

Another detail, that you have hopefully already noticed, is the use of tabs to make code more readable. Again, the computer ignores white space, so tabs may be added to visually identify structure and hierarchy.

The below, with every statement starting at the same indent level, makes it difficult to identify structure.

```js
function setup() {
createCanvas(400,200);
}
function draw() {
background(
some_var1,
some_var2,
some_var3
);
translate(width*0.5,height*0.5);
ellipse(0,0,300,100);
}
```

Whereas, if we use indentation, we can more easily identify the visual structure of the code.

```js
function setup() {
    createCanvas( 400, 200 );
}

function draw() {
    background(
        some_var1,
        some_var2,
        some_var3
    );

    translate( width * 0.5, height * 0.5 );
    ellipse( 0, 0, 300, 100 );
}
```

> A NOTE About Indentation; In your text editor, you can set, as a preference, whether your indents are tabs, or spaces. Furthermore, if using spaces, you can specify whether these should be 2-spaces, or 4-spaces.
>
> Again, it is up to your personal preference, as long as you are consistent in your coding practice.,
>
> My code, is typically indented using tabs, set to be 4-spaces.

The following provides a nice laugh about this debate, watch Silicon Valley, Season 3 / Episode 6;

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/JfEIkkDkrmE" frameborder="0" allowfullscreen></iframe></div>

<br />

As a final example, the below is the same code as the most recent example, but it has been "minified", which makes the file smaller. This code is still _legal_ and will execute, but it is hard for human's to read.

```js
function setup(){createCanvas(400,200);} function draw(){background(some_var1,some_var2,some_var3);translate(width_0.5,height_0.5);ellipse(0,0,300,100);}
```

# Why Readability Matters

Readable code matters for a number of reasons;

1. It will make it easier for you to know what your are trying to do, and keep track of your own code.
2. It makes it easier to trouble shoot, and hunt down bugs, in well structures, readable code.
3. It makes it easier for others to understand your code.


# { TODO: }

Please read the following on style and readability;

- ["Writing highly readable code" – The Startup](https://medium.com/swlh/writing-highly-readable-code-94da94d5d636)
- ["Defining readable code" - Wildly Inaccurate](https://wildlyinaccurate.com/what-makes-code-readable/)

Also, please go to, follow along, and complete the following KhanAcademy tutorial.

- ["Readable Code" via KhanAcademy](https://www.khanacademy.org/computing/computer-programming/programming/writing-clean-code/p/readable-code)
