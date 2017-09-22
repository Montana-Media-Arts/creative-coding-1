---
title: Code on This Site
module: 3
jotted: true
---

# Code on This Site

Now that we have started looking at code, I want to mention a few specifics about how code will work on look like on this site.

You have hopefully already noticed, during all of these first three weeks that there are specific code blocks. These should be displayed in your browser with a dark grey background and utilize a monospaced font. In theory this should _look like code_.

<div id="code-heading">Code Info</div>

```
Example Code Block

This is what code will look like in your browser on this site.
```

<br />


This code will also be highlighted so that the syntax of the code is more apparent.

## Specifying Language or File

When appropriate, there will be information about what the code is you are looking at in the upper-right hand corner. Typically, for this course, this will be one of;

- **p5**
    - This is general p5 code.
- **sketch.js**
    - This is p5 code that is specifically in the `sketch.js` file.
- ***.js/p5**
    - This is p5 code in another file, which will be specified in place of the '*' wildcard.
- **JS**
    - or JavaScript, which specifies the code you are looking at is general JavaScript.
- **HTML**
    - This is HTML code.
    - You will not see this very often.
- **BASH**
    - This is code for the command line application of your choice or OS.
    - Please remember that, you will copy or type text that comes after the dollar sign (`$`).

# Code Results / Sketch Output

Whenever possible and appropriate, I will also work to show you what the code output we are working on should look like. These sections will be surrounded with a big magenta/pink border.

<div class="displayed_code_example">
    <h1 style="">Code Results are Displayed in These Sections</h1>
</div>

# Playing with Code

Also, whenever possible, I will try to provide code output in a way that is editable, changeable, and playable, by you. These will still occur in the magenta code blocks, but will also include a tab'd bar within, that at a minimum will include;

- "Result"
- "JavaScript"

If you see one of these sections, you can;

1. click on the other tabs,
2. change the code,
3. go back to "Results"
4. and see the changes live!

Try it below with the "Hello World!" example.

To do this;

- click the "JavaScript" tab,
- change the `"Hello World!"` bit in line 2,
- and go back to Results. You should now see your changes!

<div class="displayed_jotted_example">
    <div id="jotted-demo-1" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/03/01_hello-world_01/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>


# Code Links

Below many code examples, there will also be a number of links. These are, and do the following;

- [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/02/01_hello-world_02/01_hello-world_02.zip)
    - This will be a zip'd folder, containing all of the code for the example.
    - This is a way for you to easily download code examples, to play with on your own computers.
- [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/02/01_hello-world_02/)
    - This link will take you directly to the GitHub entry for this code, so that you can look at it there.
- [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/02/01_hello-world_02/)
    - This will take you to a webpage that only has the code in question presented.

These links will occur underneath code examples when appropriate and available.


# All Together

Within this course website, you might see long blocks, like the following. This is an example of pulling together all of these details with the "p5 Hello World" example.

<div id="code-heading">sketch.js</div>

```js
{% remote_include https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/03/01_hello-world_02/sketch.js %}
```
<div id="code-ruler"></div>

<div id="code-heading">index.html</div>

```html
{% remote_include https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/03/01_hello-world_01/index.html %}
```

<div class="displayed_jotted_example">
    <div id="jotted-demo-2" class=""></div>
</div>
<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/master/lecture_code/03/01_hello-world_02/sketch.js"
        },
        {
            type: "html",
            url:"../../../p5_resources/index.html"
    }],
    // plugins: [ "codemirror", "console" ]
    plugins: [ "codemirror" ]
});
</script>

| [**[Code Download]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/02/01_hello-world_02/01_hello-world_02.zip) | [**[View on GitHub]**](https://github.com/Montana-Media-Arts/120_CreativeCoding_Fall2017/raw/master/lecture_code/02/01_hello-world_02/) | [**[Live Example]**](https://montana-media-arts.github.io/120_CreativeCoding_Fall2017/lecture_code/02/01_hello-world_02/) |
