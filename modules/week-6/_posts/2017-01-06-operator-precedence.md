---
title: Operator Precedence
module: 6
jotted: false
---

# Operator Precedence

You likely remember, from your studies in algebra, that arithmetic operators follow rules of "precedence". In other words, when looking at a mathematical statement, certain operators would be applied before other operators, independent of order. This is true in JavaScript as well.

In the following example, multiplication has a higher precedence than addition, which determines the outcome of the equation.

```js
// multiply 5 by 2, THEN add 5
var result = 5 + 5 * 2;

// result = 15
```

If instead, we need addition to occur first, we must isolate the portion with the highest precedence with parenthesis. In the following, parenthesis are used to force addition before multiplication.

```js
// add 5 to 5, THEN multiply by 2
var result = ( 5 + 5 ) * 2;

// result = 20
```

Just as in algebra, you must be explicit with your use of precedence, and parenthesis to specify precedence. A computer will do _exactly_ as you tell it to do. So make sure you are telling it the correct thing by double checking precedence.

If you are in doubt, use parenthesis to specify precedence. This can also be nice in making you code more "readable".

## Order of Precedence

The following list, shows the order of precedence that various operators are given. In other words, the computer works through equations according to the following order;

1. Parenthesis -- `( )`
2. Incrementation, Decrementation -- `++`, `--`
3. Exponentiation -- `**`
4. Multiplication, Division, Modulus -- `*`, `/`, `%`
5. Addition, Subtraction -- `+`, `-`
