---
title: Constructor Method
module: 11
jotted: false
---

# Class Constructor Methods

In every class definition written, there should be at least one method; that is the `constructor` method. Furthermore, typically this should be the first method defined.

The constructor method **is always** called by JavaScript when creating a new object from a class. Therefore you **must** have a constructor method. You can think about it as; "JavaScript must 'construct' or build a new object. The _constructor_ method is how a new object gets built."

## The Purpose of the Constructor Method

JavaScript uses the _constructor method_ to build new objects of a class type. Although have not seen how to instantiate a new object from a class yet, you need to accept, that the _constructor method_ is called by JavaScript.

#### So what goes in a _constructor method_?

The constructor method should be used to setup or _initialize_ an objects _properties_.

As an example, if we were creating a digital car, we may want to specify properties such as;

- `color`
- `make`
- `model`
- `year`

You will learn more specifically how to do this on the next page.

## Pseudo Code

As mentioned, the _constructor method_ should be the first method in a _class definition_.

Furthermore, if there is data that needs to be shared with the newly created object, this should be represented as _input parameters_ to this function.

Roughly, this may look like;

```js
// a class definition
class ClassName {

    // constructor method
    constructor( inputParameter1, inputParameter2 ) {
        // method function block
        // Do stuff here to create an object
        console.log(inputParemeter1);
    }
}
```
