---
title: More Examples
module: 12
jotted: true
---

# More Examples of Things Interacting

I want you to examine the next two examples to figure out how I am doing what I am doing.

## Re-Generating Happy Faces

The following example has "bouncing happy faces". But, when two of the run into each other, one is deleted. When a happy face is deleted, two more are re-generated. This occurs until an upper-threshold of the number of happy faces is reached.





<div id="jotted-demo-1" class="jotted-theme-stacked" style="800px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/12/04_bouncing_smileys_01/sketch-flat.js"
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
        { name: 'ace', options: { "maxLines": 200 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/04_bouncing_smileys_01/04_bouncing_smileys_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/04_bouncing_smileys_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/12/04_bouncing_smileys_01/) |


## Too Many PacMans

In the next example, the sketch creates 100 "PacMan-like" objects. These move only along cardinal directions (north, south, east, or west). After some random amount of time, each object can randomly choose another of those four directions to travel.

If, a PacMan runs into another PacMan that is blocking his path, then he waits until he chooses a new direction, or the blocking PacMan moves out of the way.


<div id="jotted-demo-2" class="jotted-theme-stacked" style="800px;"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/12/05_auto_pacman_01/sketch-flat.js"
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
        { name: 'ace', options: { "maxLines": 300 } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/05_auto_pacman_01/05_auto_pacman_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/12/05_auto_pacman_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/12/05_auto_pacman_01/) |
