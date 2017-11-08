---
title: Functions
module: 10
jotted: true
---

# Functions

In the [first week of looking at p5, the idea of _functions_ were presented]({{site.baseurl}}/modules/week-3/what-is-going-on/). A slightly updated list of what was presented follows;


<br />


**A function is a;**

- re-usable pieces of code,
- which can be defined or created;
    - for you (a built-in function),
    - or by you (a self-defined function).

<br />


**Calling a function requires;**

- a single piece of text (no spaces.)
- followed directly by parenthesis `()`, without a space between them and the piece of text.
    - i.e. `nameOfFunction()`
- often times, input parameters that supply additional information to function are also required within the parenthesis.


<br />


**A function;**

- does _something_...
- and contains many instructions for how to do this something.


<br />

> The [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) defines functions as;
>
> Functions are one of the fundamental building blocks in JavaScript. A function is a JavaScript procedure—a set of statements that performs a task or calculates a value.


## Built-In Functions

At this point in the semester, you have presumably gotten quite good at using built-in functions provided by p5 or more broadly JavaScript.

You have also hopefully started to acquire the ability to look up and find functions that do that something that you need to do, but do not know of an existing function. This is the process of looking through the [p5 reference page](https://p5js.org/reference/) or the [JavaScript Documentation Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide). These searches will allow you to discover additional functions that you may not have known existed.

This is a skill you will continue to develop throughout your coding work. It is important to be able to look up documentation, and find functions or techniques that allow you to do, what it is you want/need to do.

You are able to do this, because you now understand enough of the basics of JavaScript, that you can see a new function, and through reading its documentation, figure out what it will do. This is also possible, because you know enough about JavaScript now to understand generally how _all_ functions are syntactically implemented in the language. That is, you know how to write a function into your code; provide that function with input parameters; and capture/utilize any returned data from that function.

But what do you do if you cannot find a function that does exactly what you are trying to do?

## Defining Your Own Functions

JavaScript, and almost every language, allow you to define your own functions to be used in your code in the ways you need.

There are many reasons why you might define and use your own functions;

1. To define a procedure for doing something that does not exist in another built-in function.
2. To reduce complexity, by encapsulating sets of statements that you call often.
3. To _modularize_ your code, so that it can be reused more easily throughout a project.
4. To increase code readability by breaking sets of procedures into easily digested building-blocks.

#### You Already Know How

We are going to look very specifically at how to define and use your own functions over the next few pages. But, just so you know, you have been defining your own functions every week this entire semester already. The process of writing the `setup()` and `draw()` functions is _function definition_. By writing these two functions every week, you are providing functions that the p5 interpreter can call/use, which _do something_. Most likely, you have been writing these functions so that something is drawn, moved, or interacted with.

Furthermore, as you will see, the syntax for defining these functions is the same to how you will define all function withins JavaScript. So you are already comfortable with the new syntax we will look at as well this week.
