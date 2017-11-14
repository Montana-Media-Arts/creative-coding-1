---
title: Creating Objects from Classes
module: 11
jotted: false
---

# Creating Objects from Classes

A lot of discussion has occurred about classes and objects, yet you still do not know how to create an object from a class definition!

To create a new object "of class type _X_", you need to call the `new` keyword, followed by the name of the class, including any constructor input parameters within parentheses trailing the class name. This can then be assigned to a variable for later reference.

The following creates a new object, of class type `ClassName`, and passes it two input parameters. This new object is stored in the variable `myObj`.

```js
let myObj = new ClassName( inputParam1, inputParam2 );
```

# Accessing an Objects Properties

To access an objects properties, we will use the same "_dot notation_" as we learned about with [_object literals_]({{site.baseurl}}/modules/week-6/js-objects/).

```js
myObj.property1; // ← returns the value of 'myObj's property1.
```

We can also set object properties using this same notation.

```js
myObj.anotherProperty = 23; // ← sets the value of the property to 23
```

**NOTE:** Typically, when using classes and OOP paradigms, setting object properties with this notation is considered poor style. This is because it can lead to errors in code. More on this will be discussed later.

# Calling Object Methods

_dot notation_ is also used to execute object methods. However, parenthesis are always added to the method name, regardless of whether there are input parameters being passed to the method or not.

```js
myObj.method1(); // ← executes myObj's method, 'method1'.

myObj.method2( inParam2, 57 ); // ← execute the method and pass it two input parameter values.
```
