---
title: p5 Workspace
permalink: /:title/
jotted: true
---

# Blank p5 Workspace

| [**DOWNLOAD - Empty p5 project**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/_empty_example/empty-example.zip) |

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            content:"\nfunction setup() {\n\t\n}\n\nfunction draw() {\n\t\n}\n"
        },
        {
            type: "html",
            hide: true,
            url: "https://montana-media-arts.github.io/creative-coding-1/p5_resources/p5-workspace.html"
        }
    ],
    showBlank: false,
    showResult: true,
    plugins: [
        { name: 'ace', options: { "maxLines": 100 } },
        { name: 'play', options: { firstRun: false } },
        { name: 'console', options: { autoClear: true } },
    ]
});
</script>
