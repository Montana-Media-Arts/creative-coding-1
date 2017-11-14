---
title: OOP Terminology
module: 11
jotted: false
---


# OOP Terminology

This page will go into some of the terminology of object oriented programming a bit more.

The first thing to know is the name of the paradigm itself. Again, _object oriented programming_ is a shift from _procedural programming_ in which every line flows to the next, or even _structural programming_ which encapsulates some information or common tasks as things to do after certain events (we started to explore this last week informally). _Object oriented programming_ is a shift towards the encapsulation of ideas, data, and digital things as objects, whose _properties_ and _methods_ are _encapsulated_ away from the main program. After _instantiating_ or creating a new object, this object can then interact with other objects or the program itself.

This will be a shift in thinking for many of you. Away from a line-by-line approach, towards an _abstracting_ of ideas into separate parts of your code. Again, this is a difficult switch, and that is recognized.


## Object

An **_object_**, in computer code, is a digital _thing_. In JavaScript, we have seen one, simple way, of how to create objects, using the curly-bracket notation. This is technically known as an _object literal_.

```js
let myObj = { property1: someValue, property2: someOther Value };
```

However, starting this week, we will start to create objects using _classes_. These objects will be the digital representation of some class "blueprint" or "recipe" as the videos alluded to.

An _object_ is often described as an _instance_ of a _class_.


## Class

A **_class_** is an _abstract_ representation that _encapsulates_ what it means for something to be "that thing".

Let me unpack that...

- A class is set of instructions, comprised of _properties_ and _methods_.
- Together, these properties and methods can be used to define a digital object. Whether that is a digital representation of an employee (low-level, assistant, manager, CEO, etc.), or some set of data.
- The class is not the actual "thing" but rather a set of instructions describing the potential for that "thing".
- This is an abstract representation of an object. It is the potential of an object. Or, it is a description of what is necessary for an object to actually exist, along with a set of instructions for how that object would exist in the digital world. Rather, the data and ways of acting on the data are _encapsulated_ together in a single objet.


## Encapsulation

**_Encapsulation_** is the gathering of data or properties that define an object, along with the methods or functions that are used to enact change on these properties.

_Encapsulation_ is what allows _objects_ to be created from _classes_. The _encapsulation_ of both properties and methods in a single object allows programmers to treat the object as a self-contained unit.


## Abstraction

**_Abstraction_** is the reduction of code by a programmer, such that an object can be treated as a "black box". The programmer who "uses" an object of class type _X_ simply needs to know about its _properties_ and _methods_ NOT how these are implemented. In this way, the class abstracts away or hides the complexity of the object.


## Property

An object or class **_property_** is a piece of data used to define the resulting _object_.

For example, if we have two "car objects", the parent class might have a property that defines `color`. The `color` property of the first car may be `red` and the second `blue`.

In this way, the _properties_ of classes are used to define the specifics of a resulting _object_.

NOTE: Class/object _properties_ are also sometimes referred to as;

- _attributes_
- _data_
- _fields_


## Method

An object or class **_method_** is a function that defines something to do with an object, or some way of processing an objects data/properties.

For example, if we were writing a car class in p5, we may want to add a _method_ that would `display` the car the web canvas. This _method_ would query the objects _properties_ to determine things like, `color`, `speed`, `direction`, and maybe `size`. This _method_ would then use these _properties_ along with other information that helps define a car, to draw an image of a car on the canvas.


## Instantiation (aka. `new`)

When we create a new _object_ from a _class_, we are **_instantiating_** the _new_ object.

As we will see throughout this week's content, to create a new _instance_ of a class, we will use the JavaScript keyword `new`.


## this

A potentially confusing idea is the reference to "specific instances" of an object. When referring to a specific instance of an object, or, when referring to an object's own instance (from within the object) we will use the term **_this_**.

The `this` keyword in JavaScript is used throughout the language, and can be very confusing (hence why it has remained anonymous until now). Before we dive deep into `this`, just try and accept that `this` refers to a specific instance of an object from within that object itself. 
