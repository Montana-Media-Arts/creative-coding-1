---
title: Statements
module: 3
jotted: false
---

# Statements

So far, there has not been any extensive discussion of coding syntax, nor why the computer interprets code in the way it does. Now that our code sketches are getting more involved, this conversation needs to be started.

For the most part, every line of code that we have written between the function blocks for `setup()` and `draw()`, and the variable declarations outside of these functions, have been individual _statements_.

A _statement_ in code is a command or instruction for the computer to follow.

<br />


For example, calling the create canvas function inside `setup()` is a statement.

```js
createCanvas( 400, 200 );
```

This statement tells the computer to;

- create a new canvas element
    - that is 400 pixels in width
    - and 200 pixels in height

This statement is _terminated_ with a semicolon (`;`) at the end of the line.


<br />

Likewise, when declaring and assigning a variable, like the following;

```js
let myVar = 200;
```

This is a statement, that tells the computer to;

- create a new variable space
    - with the symbolic name `myVar`
- in memory,
    - store the Number value `200`
    - and associate it with the variable `myVar`

This statement, as with the create canvas statement above, is terminated with a semicolon (`;`) at the end of the line.

### The Semicolon

In JavaScript, the semicolon is used to tell a computer that this is the end of a statement.

> _YOU SHOULD GET IN THE HABIT OF TERMINATING EVERY CODE STATEMENT WITH A SEMICOLON ( `;` )_

Your code will _likely_ not break if you forget a semicolon at the end of a line. But it is good programming standard for you to follow. For a number of reasons;

1. It visually identifies the end of code statement to programmers, including yourself, and anyone else who might look at your code (me or collaborators).
2. It explicitly tells the computer "this is the end of a statement". Although the computer _might_ figure it out, it is always better to be explicit with the computer, then it has less of a chance of doing something unexpected.
3. If your code every gets "minified", that is all spaces and new-line returns removed, it will not break.


<br />

_YOU_ would never do the following, but it demonstrates what could happen, and why semicolon's are important.

It is possible to write multiple statements on a single line of JavaScript code. To do this, you must specify the end of each statement. The following sets the background, declares a variable (`der`), declares a variable (`duh`), and creates an ellipse dependent on `der` and `duh`;

```js
background(20); let der=2; let duh=der+100; ellipse(der,duh,der);
```

Again, _YOU_ should not write code like the above. BUT, it is legal code, and works since the statements are separated with semicolons.

The above would _technically_ also work, if written without semicolons, but on new lines, like;

```js
background( 20 )
let der=2
let duh=der+100
ellipse(der,duh,der)
```

Again, _YOU_ should not write code like this. BUT, it is legal code. The JavaScript interpreter, will _likely_ execute the code without error, as it will _assume_ that each new line is a new statement.


<br />

Of course though, we want to be explicit with the computer, and reduce our chances of it producing unexpected results. That is why the above should actually be written like;

```js
background( 20 );
var der = 2;
var duh = der + 100;
ellipse( der, duh, der );
```

<br />

There are specific instances when we do not want to add semicolon's. These will be identified to you as we progress this semester. In the meantime, please get in the habit of using semicolon's after your statements in your current p5 sketch code.
