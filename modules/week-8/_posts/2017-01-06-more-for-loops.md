---
title: More for loops
module: 8
jotted: true
---

# More for loops

Let's look at some more examples of using _for loops_.


## Update Statement

The _update statement_ portion of _for loops_ creates lots of flexibility for how data, and the progression of the for loop can occur.

So far, we have only discussed and seen this statement utilize the _increment by 1_ syntax (i.e `i++`). But, any statement that returns a new value for the defined variable may be used. This might include any of the following;

```js
i++;
i--;
i+=2;
i-=2;
i = (i ** 10) / 3;
```

As long as the _update statement_ returns a valid Number, then anything can be used. NOTE: The only thing to be wary of is that the _update statement_ moves the Number variable towards completion of the loop. Be cautious of _update statements_ that cause an **infinite loop**. That is, statements that do not move the Number variable towards completion of the _for loop_. As this will result in your code locking up and breaking. For example, the following would cause a silent problem, as the Number variable is _decreasing_ in the _update statement_, but the _conditional statement_ will only cause an exit once the Number variable is greater than 10.

```js
for( let i=5; i < 10; i-- ) {
	// do something
	// never exits this loop
}
```

<br />

On the other hand, the following example increments by 60 every loop, until `i` is greater than 400. Notice how the diagonal lines are each 60 pixels apart?  This is because of the _update statement's_ use of increment by 60.

**{ TODO: }** Change the _update statement's_ value from 60 to some other values to see how the sketch changes.


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/03_for_loop_largeInc_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/03_for_loop_largeInc_01/03_for_loop_largeInc_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/03_for_loop_largeInc_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/03_for_loop_largeInc_01/) |



## Number Variable Declaration

The first statement of a _for loop_ is the _Number variable declaration and initialization_. As mentioned on the previous page, this tells the _for loop_ what variable to use and what it is initially set to. This value can be initialized to any Number. It is common to see it, or set it to 0, but, this is not a limitation.

Likewise, you will see the variable `i` often used in for loops, but any variable, following the rules described in [variable naming]({{site.baseurl}}/modules/week-6/naming-variables) can be used.

In the below example, the _declaration statement_ initializes the value `x` to 20. This is used to start drawing diagonal lines at 20px on the X-axis.



<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/04_for_declaration_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/04_for_declaration_01/04_for_declaration_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/04_for_declaration_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/04_for_declaration_01/) |


## Math With the _For Loop_ Variable

As has been shown, but should be highlighted, the variable used in _for loops_ is scoped such that it can be used within the _function block_ of the _for loop_. In the below example, the Number variable `i` is initialized to the value of 20. This variable is used to draw sets of connected lines, whose angles get progressively more ‘severe’. This is accomplished by multiplying the variable `i` by 1.5 at the “connection point”.There by creating larger value of difference between the starting point (`i`) and the connection point (`i*1.5`).


<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/08/05_for_loops_math_01/sketch.js"
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
        { name: 'play', options: { firstRun: true } },
        // { name: 'console', options: { autoClear: true } },
    ]
});
</script>

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/05_for_loops_math_01/05_for_loops_math_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/08/05_for_loops_math_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/08/05_for_loops_math_01/) |
