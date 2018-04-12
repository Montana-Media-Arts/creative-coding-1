---
title: Objects Interacting w/ Each Other
module: 12
jotted: true
---

# Objects Interacting with Each Other

The next challenge to solve this week is;

- How do we make objects aware of each other?
- And how do we make objects interact with each other?

The basic technique is rather simple, to get an object to interact with, or rather have awareness about, other objects in a sketch, that object needs to be given information about the _other objects_.

## Making it Happen

To work through how to do this, we are going to start with a slightly modified version of the bouncing ball code from the previous week. It has been modified to have an array of bouncing balls.



<div id="jotted-demo-1" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/12/03_objects_w_objects_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/03_objects_w_objects_01/03_objects_w_objects_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/03_objects_w_objects_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/12/03_objects_w_objects_01/) |


## Check Other Objects

In this example we are building, let's say that _"if, a ball touches another ball, then, it should go in the opposite direction."_ Since we are going to stay with an OOP approach, let's encapsulate this functionality in the ball class. We will create a new method called, `ballCheck()`, that will check all of the other balls, to determine if `this.` will/is touching another ball.

In order to check a ball's relationship of itself to the other balls, it needs information about the other balls. This means we need to pass our new method the information about the other balls. One way of solving this, and the one we will explore right now, is to pass in the entire ball array. To do this, we will call the new `ballCheck()` method every `draw()` loop, passing in a reference to the array.

```js
function draw() {
    background( 'rgb(66, 57, 66)' );

    for (let i = 0; i < balls.length; i++) {
        // call the ball's methods
        // -- notice that we pass in the ball array
        balls[i].ballCheck(balls, i);
        balls[i].move();
        balls[i].edgeCheck();
        balls[i].display();
    }
}
```

This will allow the ball to check itself against every other ball. HOWEVER, we have one more problem, this ball also needs to know which ball _**it**_ is, so that it does not try and check itself against itself.

![ball needs to know itself](../imgs/ball-self.png)

To solve this, we will simply also pass in the index of the current ball (`i`).

```js
ball.ballCheck( balls, i );
```

In the `ballCheck()` method that we are writing in the class, we will take these two pieces of data, and use them to check whether the ball is touching another ball. To do this, the code needs to check each of the _other_ balls that exist, skipping itself.

```js
ballCheck( otherBalls, myId ) {
    // for loop touches each of the balls in the array
    for (let n = 0; n < otherBalls.length; n++) {
        // if n != myId, then check for touching
        // otherwise, its ME and we need to skip
        if( n != myId ) {
            // check for touching here!
        }
    }
}
```

> Note how the input parameter names are different in the class method from the statements in the `draw()` loop. This is allowed since the class handles its own data.

To find out if the balls are touching, we need to employ a similar method as was used to check if the mouse was touching a bubble. If the distance between the center points for each ball is _less than_ the combined radius of both balls, then the balls are touching.

![Demonstrating how to check if a ball is touching another ball.](../imgs/balls-touching.png "Demonstrating how and when a ball would be touching another ball.")

```js
ballCheck( otherBalls, myId ) {
    // for loop touches each of the balls in the array
    for (let n = 0; n < otherBalls.length; n++) {
        // if n != myId, then check for touching
        // otherwise, its ME and we need to skip
        if( n != myId ) {
            let d = dist( this.posX, this.posY, otherBalls[n].posX, otherBalls[n].posY );
            let combinedR = this.rad + otherBalls[n].rad;

            if( d <= combinedR ) {
                this.deltaX *= -1;
                this.deltaY *= -1;
            }
        }
    }
}
```

> I am also adding in some color changes that display if the ball has most recently; 1.) Been created; 2.) Hit a wall; 3.) Hit another ball.

Altogether the code now looks like;

<div id="jotted-demo-3" class="jotted-theme-stacked" style="600px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/12/03_objects_w_objects_02/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/03_objects_w_objects_02/03_objects_w_objects_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/03_objects_w_objects_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/12/03_objects_w_objects_02/) |

> Can you figure out why the balls sometimes get "stuck" on each other?
