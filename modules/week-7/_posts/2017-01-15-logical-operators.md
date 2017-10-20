---
title: Logical Operators
module: 7
jotted: false
---

# Logical Operators

[Boolean Algebra]() is used to describe "logical relations" in the same way that _Algebra_ is used to describe "numeric relations". Boolean algebra takes two or more conditional statements and compares their `truth` value against each other.

## Logical AND

The _Logical And Operator_ compares two Boolean expressions.

- If _both_ Boolean values/statements evaluate to _true_ than the operator _returns_ _true_.
- If either Boolean value/statement evaluates to _false_ than the operator _returns_ _false_.

The _Logical And Operator_ is expressed with 2 ampersand keys placed together (the 'and' character on the '7' key).

```js
&& // ← Logical And Operator
```

Let's look at all possible expressions and their results using Boolean values.

```js
true && true // ⇒ returns true
true && false // ⇒ returns false
false && true // ⇒ returns false
false && false // ⇒ returns false
```

As you can see, both of the operators Boolean values must be _true_ for the statement to return _true_.

## Logical OR

There is also a _Logical Or Operator_. This operator returns _true_ if **either* of the Boolean values being evaluated are true.

The _Logical Or Operator_ is specified using two pipe characters, This character is typically found on as the "shift character" on the backslash, which is the key above "return".

```js
|| // ← Logical Or Operator
```

Following the above example, let's look at all the possible statement combinations and the result.

```js
true || true // ⇒ returns true
true || false // ⇒ returns true
false || true // ⇒ returns true
false || false // ⇒ returns false
```

As you can see, only one of the Boolean values needs to be true for the statement to return _true_.
