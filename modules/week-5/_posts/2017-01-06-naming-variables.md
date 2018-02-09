---
title: Naming Variables
module: 5
jotted: false
---

# Naming Variables

If you haven't gathered it yet, a lot of coding is about rules, standards, and guidelines.

we could informally consider;

- **Rules** as things you must do, that the computer expects. These are things that will throw errors, cause problems in your code, or mess things up.
- **Standards** as standardized norms that are followed by programmers.
- **Guidelines** as suggestions that will make coding easier for you.

The naming of variables includes all of these. There are certain rules you must follow in order for your variables to work (like considering global vs local scope), there are naming standards that programmers consider as proper and improper ways to name variables, and there are guidelines you should follow that will make your code easier to read.

## Variable Naming Rules

1. Variables can only contain;
    - letters (`a`-`z` and `A`-`Z`),
    - numbers (`0`-`9`)
    - or underscores (`_`)
2. Variable names cannot start with;
    - capital letters (`A`-`Z`)
    - or numbers
3. Variables cannot contain;
    - spaces,
    - or other special characters

## Variable Naming Suggestions

1. Although technically legal, variables should not start or end with an underscore (`_`).
2. Variable names should be meaningful and descriptive.

## Variable Naming Guidelines

1. Follow the same patterns for variable names throughout a code project.
    - This is especially true as it relates to multi-word variables.

# Examples and Further Info

Now that we have identified some rules, suggestions, and guidelines, let's talk through what that means.

The rules should be rather self explanatory. You are limited in the characters you can use to name variables. These should be only include letters, numbers, and underscores.

Furthermore, although technically legal, you should refrain from starting or ending a variable name with an underscore (i.e. `_myVar` or `myVar_`). Both of those instances are reserved for special situations.

## Meaningful Naming

Variables names should be meaningful and explanatory. Although technically legal, using single letters as variable names (i.e. `a`, `x`, or `y`) are not particularly descriptive. A variable name might give clues about what the data that it holds is, or how the variable will be used.

As an example, the reserved p5 variables, `width` and `windowWidth` are descriptive of the variable itself.

- `width` holds the value representing the canvas' width as specified by `createCanvas()`
- `windowWidth` holds the value of the width of the browser window.

Both of these variable names help the developer know what te variable is.


<br />

As another example, we may use a variable to represent the X position of an element or series of elements. An appropriate name for a variable might be something like `location_x`, `loc_x`, `loc_X`, `locationX`, or `locX`. All of these give some sense as to what the variable is and how it might be used.

## Variable Naming Patterns

The above examples, demonstrating the descriptive names for a variable holding an X location value also shed light on guidelines for naming.

Variable names will often be multiple words, as this can assist with descriptive variable names, and code readability.

As another example, perhaps you wanted to have a variable that held the center position, for a cat's face that you are drawing. Therefore, we ay want to use the words `cat`, `face`, and either `X` or `Y`. Even though you cannot use spaces, there are multiple ways of combining words, that are visually apparent, and increase code readability.

First, what you **SHOULD NOT DO** is run the words together, all lowercase, like so;

```js
// DO NOT DO THIS
let catfacex;
```

That is quite difficult to read, and prone to typos.

#### camelCase

One option for combining words is to use a style known as "camelCase". Camel Case involves removing the spaces between multiple words and then capitalizing the first letter of each word, like a camel's humps.

In the case of our cat face position, this might look like;

```js
let catFaceX;
```

That is easy to read, and allows you to visually distinguish the separate words still.

#### underscore_seperated

Another option is to seperate words with underscores (`_`). This also allows for easily readable code. This might look like;

```js
let cat_face_x;
// or
let cat_face_X;
```

### Consistency

 Which ever of these strategies you choose, you should use it for all of your variables for a project. That way you will not get confused when using variables later in your code.

 In fact, I would suggest, you pick one or the other of these two variable naming schemes, and use it throughout the semester. It will then reduce one more error you might have later on.
