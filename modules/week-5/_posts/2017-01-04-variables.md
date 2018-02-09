---
title: Defining Variables
module: 5
jotted: true
---

# Defining & Using Variables

In addition to using pre-defined, reserved word variables from p5, you can define your own variables!

As mentioned on the [previous page]({{site.baseurl}}/modules/week-5/p5-variables/), a _variable_ is a _storage location_, paired with a _symbolic name_. For example, the constant `PI` is a _symbolic name_, that is used to reference data in a storage location, in the computers memory. In the current case, that data is a number, which equals `3.14159265359`. Whenever the variable name `PI` is placed in code, the computer instead grabs the specific data, in this case the above number, and replaces it in the code, in place of the variable name.

To define our own variables, we first need to tell the computer that we are doing so. The computer will then set that word aside to be used to reference some piece of data. Then, we can tell the computer _what_ that data should be. The computer will then store this data in its memory, and make a connection between the variable's _symbolic name_ and the piece of data.

## Declaring a Variable

To _declare_ a variable, you will need to use the `let` keyword, followed by the _symbolic name_ you want your variable to have.

```js
let myVar;
```

> JavaScript is a "weakly-typed" language. This means we simply need to use the `let` keyword when defining variables. We can then associate any type of data we want with the variable.
>
> NOTE: There are other languages, such as Java, which Processing (p5's sibling) is built on, that are "strongly-typed" languages. In these types of languages, you will need to declare the variable type when creating a variable. Such as, Number, or String.

## Associating Data with a Variable

After declaring a variable name space, data can then be associated with the variable. This is called "_initializing_" the variable. To do this, we use the assignment symbol, which is the equal sign (`=`).

In the following example, we associate the Number `20` with the variable `myVar`. If we were discussing this code, we might say "The variable 'myVar' _gets_ assigned the Number 20." (Notice, we specifically did not say "equals". That is a very specific term in programming. So when assigning or initializing variables, say "_gets assigned_").

```js
myVar = 20;
```

## Using Variables

We could then use the variable `myVar` anywhere that a Number could be used. For example, we could pass it as the size parameter to the `ellipse()` function.

```js
ellipse( 30, 200, myVar );
```

In the following example, open the JavaScript tab, and change the value assigned to `myFirstVar`. Notice how this changes the size of the ellipse in the result tab.


<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/05_variables_01/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/05_variables_01/05_variables_01.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/05_variables_01/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/05_variables_01/) |


### Shorthand

It is also possible, to declare a variable, and assign it some data in the same line. To do this, combine the declaration, and assignment operators.

In the below example, a variable named `another_variable` is declared, and the string "some data" is assigned to it.

```js
let another_variable = "some data";
```

## Re-Assigning Variables

It is also possible, and quite common to re-assign variables new data values after they have been initially declared, or used. To do this, you will simply write another assignment statement in your code.

The following example, re-assigned the variable `point_pos` after using it the first time.

<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/05_variables_02/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/05_variables_02/05_variables_02.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/05_variables_02/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/05_variables_02/) |


In the next example, the 3 variables are used to define a series of repeating lines. This example, from the p5 ["Examples" page](https://p5js.org/examples/), demonstrates how variables can be used repeatedly, overwritten (discussed in a moment), and used in math.

Open the JavaScript tab, change the Numbers assigned to the variables, and notice the sketch change.

<div id="jotted-demo-3" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-3"), {
    files: [
        {
            type: "js",
            hide: false,
            url:"https://raw.githubusercontent.com/Montana-Media-Arts/120_CreativeCoding/master/lecture_code/05/05_variables_03/sketch.js"
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

| [**[ Code Download ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/05_variables_03/05_variables_03.zip) | [**[ View on GitHub ]**](https://github.com/Montana-Media-Arts/120_CreativeCoding/raw/master/lecture_code/05/05_variables_03/) | [**[ Live Example ]**](https://montana-media-arts.github.io/120_CreativeCoding/lecture_code/05/05_variables_03/) |

> Why are the line sections repeating in the above example?
