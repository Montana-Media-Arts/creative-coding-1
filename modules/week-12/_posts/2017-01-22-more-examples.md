---
title: More Examples
module: 12
jotted: true
---

# More Examples of Things Interacting

I want you to examine the next two examples to figure out how I am doing what I am doing.

## Re-Generating Happy Faces

The following example has "bouncing happy faces". But, when two of the run into each other, one is deleted. When a happy face is deleted, two more are re-generated. This occurs until an upper-threshold of the number of happy faces is reached.


<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
let happyface = [];
let init_numHappyFaces = 2;
let bg_color;
let canCreateNewHappyFace = true;

function setup() {
    createCanvas(windowWidth,windowHeight);

    let init_x = 100;
    let init_y = 100;
    let init_size = random(40, 150);

    for (let i = 0; i < init_numHappyFaces; i++) {
        happyface.push(
            new Happyface(init_x, init_y, init_size, randomColor())
        );
        init_x += init_size + random(50, 150);
        if (init_x >= width) {
            init_x = 100;
            init_y += init_size + random(10, 30);
        }
        init_size = random(20, 150);
    }
}

function draw() {
    background(255, 255, 255, 5);

    canCreateNewHappyFace = true;

    for (let i = 0; i < happyface.length; i++) {
        happyface[i].frame(happyface, i);
    }

}

function randomColor() {
    return color( floor(random(256)), floor(random(256)), floor(random(256)) );
}


function createNewHappyFace(){
    for (let i = 0; i < 2; i++) {
        happyface.push(
            new Happyface(random(width), random(height), random(20, 150), randomColor())
        );
    }
}

function killHappyFace(idx){
    happyface.splice(idx, 1);
}
{% endhighlight %}


<div id="code-ruler"></div>
<div id="code-heading">happyface.js</div>


{% highlight js linenos %}
class Happyface {

    // Constructor Method
    constructor(init_x, init_y, size, color) {
        // Parameters
        this.loc = {
            x: init_x,
            y: init_y
        };
        this.size = size;
        this.rad = this.size * 0.5;
        this.angle = 0;
        this.color = color;
        this.eye = {
            x: this.size * 0.2,
            y: this.size * -0.33,
            size: this.size * random(0.2, 0.4)
        };
        this.mouth = {
            y: this.size * 0.5 * 0.15,
            width: this.size * 0.75,
            height: this.size * 0.45,
            color: '#000'
        };
        this.delta = {
            x: map(this.size, 40, 150, 10, 0.5) * map(round(random(1, 2)), 1, 2, -1, 1),
            y: 0,
            gravity: 0.1
        };
    }


    frame(objArr, myIdx) {
        this.bounce();
        this.checkCollisions(objArr, myIdx);
        this.display();
    }


    display() {
        push();
        translate(this.loc.x, this.loc.y);
        rotate(this.angle);

        fill(this.color);

        noStroke();
        ellipse(0, 0, this.size, this.size);

        push();
        fill('#fff');
        ellipse(-this.eye.x, this.eye.y, this.eye.size, this.eye.size);
        fill('#000');
        ellipse(-this.eye.x, this.eye.y, this.eye.size * 0.25, this.eye.size * 0.25);
        pop();
        push();
        fill('#fff');
        ellipse(this.eye.x, this.eye.y, this.eye.size, this.eye.size);
        fill('#000');
        ellipse(this.eye.x, this.eye.y, this.eye.size * 0.25, this.eye.size * 0.25);
        pop();

        fill(this.mouth.color);
        arc(0, this.mouth.y, this.mouth.width, this.mouth.height, 0, PI, CHORD);
        pop();
    }


    bounce() {
        // move horizontally
        this.loc.x += this.delta.x;
        if (this.loc.x + this.rad >= width) {
            this.loc.x = width - 1 - this.rad;
            this.delta.x *= -1;
        } else if (this.loc.x - this.rad <= 0) {
            this.loc.x = 1 + this.rad;
            this.delta.x *= -1;
        }

        // Vertical Bounce
        this.delta.y += this.delta.gravity;
        this.loc.y += this.delta.y;
        if (this.loc.y + this.rad >= height) {
            this.loc.y = height - 1 - this.rad;
            this.delta.y *= 0.9;
            this.delta.y *= -1;
        }
    }


    checkCollisions(objArr, myIdx) {
        for (var i = 0; i < objArr.length; i++) {
            if (myIdx !== i) {
                var obj = objArr[i];
                var objDist = dist(this.loc.x, this.loc.y, obj.loc.x, obj.loc.y);
                var maxDist = this.rad + obj.rad;
                if (objDist <= maxDist) {
                    this.delta.x *= -1;
                    this.delta.y *= -1;
                    if (canCreateNewHappyFace) {
                        createNewHappyFace();
                        canCreateNewHappyFace = false;
                    }
                    killHappyFace(myIdx);
                }
            }
        }
    }
}
{% endhighlight %}


<div id="code-ruler"></div>
<div id="code-heading">index.html</div>

{% highlight html linenos %}
<!DOCTYPE html>
<html>

    <head>
        <script src="p5_lib/p5.min.js"></script>
        <script src="sketch.js"></script>
        <script src="happyface.js"></script>
        <style> body {padding: 0; margin: 0;} </style>
    </head>

    <body>
    </body>

</html>
{% endhighlight %}





<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class="" style="height:800px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/12/04_bouncing_smileys_01/sketch-flat.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/12/04_bouncing_smileys_01/04_bouncing_smileys_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/12/04_bouncing_smileys_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/12/04_bouncing_smileys_01/) |


## Too Many PacMans

In the next example, the sketch creates 100 "PacMan-like" objects. These move only along cardinal directions (north, south, east, or west). After some random amount of time, each object can randomly choose another of those four directions to travel.

If, a PacMan runs into another PacMan that is blocking his path, then he waits until he chooses a new direction, or the blocking PacMan moves out of the way.

<div id="code-heading">sketch.js</div>

{% highlight js linenos %}
// Define an empty PacMan object Array
let pacmans = [];
let numPacMans = 100;

// setup function
function setup() {
	createCanvas(windowWidth, windowHeight);

	// create some pacmans
	let xpos = 0;
	let ypos = 20;
	let diam = 0;
	for (let i = 0; i < numPacMans; i++) {
		diam = round(random(10,60));
		xpos = xpos + random(60, 300);
		if( xpos >= width - 21){
			ypos = ypos + 80;
			xpos = diam;
		}
		pacmans[i] = new PacMan(xpos, ypos, diam );
	}
}

// draw loop
function draw() {
	let tempArr = [];
	background(200);

	// update pacman positions
	for (let i = 0; i < pacmans.length; i++) {
		// check neihbors by passing in an array of other PacMan's
		tempArr = pacmans.slice(0,i);
		tempArr = tempArr.concat( pacmans.slice(i+1, pacmans.length) );
		pacmans[i].checkPos( tempArr );

		pacmans[i].draw();
	}

}
{% endhighlight %}

<div id="code-ruler"></div>
<div id="code-heading">pacman.js</div>

{% highlight js linenos %}
class PacMan {

    // constructor for PacMan
    constructor(xpos, ypos, diam) {
        // shape
        this.diam = diam;
        this.radius = this.diam / 2;
        this.eyePos = this.diam / 7;
        this.eyeDiam = this.diam / 8;
        this.mouthAngle = (1 / 6);
        this.mouthChange = 1 / 128;

        //  position and movement
        this.xpos = xpos;
        this.ypos = ypos;
        this.direction = 0;
        this.change = 0;
        this.xChange = 0;
        this.yChange = 0;
        this.maxDirChange = 4;
        this.wait = false;

        // timing
        this.curTime = 0;
        this.maxTime = 8;
        this.targetTime = random(this.maxTime);

        this.curDist = 0;
        this.minDist = 0;
        this.xDiff = 0;
        this.yDiff = 0;

    }


    draw() {
        // call move
        this.timer();
        this.move();

        push();
        translate(this.xpos, this.ypos);

        // check direction and rotate PacMan
        if (this.direction === 0) {
            // do nothing
        } else if (this.direction === 1) {
            rotate(PI / 2);
        } else if (this.direction === 2) {
            scale(-1, 1);
        } else if (this.direction === 3) {
            rotate(-PI / 2);
        }

        // draw the pacman
        // body
        fill(color("Yellow"));
        arc(0, 0, this.diam, this.diam, PI * this.mouthAngle, -PI * this.mouthAngle, PIE);
        // eyes
        fill(color("Black"));
        arc(this.eyePos, -this.eyePos * 2, this.eyeDiam, this.eyeDiam, PI * this.mouthAngle * 2, -PI * this.mouthAngle * 2, PIE);

        // // testing text TODO: remove later
        // text(this.direction, this.radius, -20);
        // text(this.minDist, this.radius, -10);
        // text(this.curDist, this.radius, 0);
        // text(this.xDiff, this.radius, 10);
        // text(this.yDiff, this.radius, 20);

        pop();
    }


    //  Moe Function
    move() {
        // update position
        if (!this.wait) {
            this.xpos += this.xChange;
            this.ypos += this.yChange;
        }

        //  mouth animation
        this.mouthAngle = this.mouthAngle + (this.mouthChange * this.change);
        if (this.mouthAngle > (1 / 6)) {
            this.mouthChange = -this.mouthChange;
            this.mouthAngle = (1 / 6);
        }
        if (this.mouthAngle < 0.01) {
            this.mouthChange = -this.mouthChange;
            this.mouthAngle = 0.03;
        }


        // edge check
        if (this.xpos + this.radius >= width) {
            this.xpos = width - this.radius;
            this.xChange = 0;
        } else if (this.xpos - this.radius <= 0) {
            this.xpos = 0 + this.radius;
            this.xChange = 0;
        }

        if (this.ypos + this.radius >= height) {
            this.ypos = height - this.radius;
            this.yChange = 0;
        } else if (this.ypos - this.radius <= 0) {
            this.ypos = 0 + this.radius;
            this.yChange = 0;
        }
    }


    // Timer
    timer() {
        var curTime = this.curTime;
        if (curTime >= this.targetTime * frameRate()) {
            // change direction and update timer
            this.changeDirection();
        } else {
            this.curTime++;
        }
    }


    changeDirection() {
        var newDirection;

        // reset timer
        this.curTime = 0;
        this.targetTime = random(this.maxTime);

        // choose a new direction
        do {
            newDirection = floor(random(4));
            // loop if random chooses same as previous
        } while (newDirection == this.direction);

        this.direction = newDirection;

        // get a new travel speed
        this.change = random(this.maxDirChange);
        // assign direction values accordingly
        if (newDirection === 0) {
            // East
            this.xChange = this.change;
            this.yChange = 0;
        } else if (newDirection === 1) {
            // South
            this.xChange = 0;
            this.yChange = this.change;
        } else if (newDirection === 2) {
            // West
            this.xChange = -this.change;
            this.yChange = 0;
        } else if (newDirection === 3) {
            // North
            this.xChange = 0;
            this.yChange = -this.change;
        }
    }


    // distance checks
    checkPos(pacArray) {
        var minDist = 0;
        var curDist = 0;
        var xDiff = 0;
        var yDiff = 0;

        this.wait = false;
        for (var i = 0; i < pacArray.length; i++) {
            curDist = dist(this.xpos, this.ypos, pacArray[i].xpos, pacArray[i].ypos);
            // minDist = sqrt(pow(this.diam,2) + pow(pacArray[i].diam,2));
            minDist = this.radius + abs(this.xChange) + abs(this.yChange) + pacArray[i].radius;

            xDiff = pacArray[i].xpos - this.xpos;
            yDiff = pacArray[i].ypos - this.ypos;

            if (this.direction === 0 && curDist <= minDist && xDiff > 0) {
                // check for conflict to the east
                this.wait = true;
            } else if (this.direction == 1 && curDist <= minDist && yDiff > 0) {
                // check for conflicts to the south
                this.wait = true;
            } else if (this.direction == 2 && curDist <= minDist && xDiff < 0) {
                // check for conflicts to the south
                this.wait = true;
            } else if (this.direction == 3 && curDist <= minDist && yDiff < 0) {
                // check for conflicts to the south
                this.wait = true;
            }

            // this.curDist = curDist;
            // this.minDist = minDist;
            // this.xDiff = xDiff;
            // this.yDiff = yDiff;
        }
    }

}
{% endhighlight %}

<div id="code-ruler"></div>
<div id="code-heading">index.html</div>

{% highlight html linenos %}
<!DOCTYPE html>
<html>

    <head>
        <script src="p5_lib/p5.min.js"></script>
        <script src="sketch.js"></script>
        <script src="pacman.js"></script>
        <style> body {padding: 0; margin: 0;} </style>
    </head>

    <body>
    </body>

</html>
{% endhighlight %}


<div class="displayed_jotted_example">
    <div id="jotted-demo-2" class="" style="height:800px;"></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/12/05_auto_pacman_01/sketch-flat.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/12/05_auto_pacman_01/05_auto_pacman_01.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/12/05_auto_pacman_01/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/12/05_auto_pacman_01/) |
