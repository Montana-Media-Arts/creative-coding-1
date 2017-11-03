---
title: Manipulating Arrays
module: 9
jotted: true
---

# Manipulating Arrays

In addition to creating prefilled arrays, you will find many times where you need to dynamically manipulate the values stored within an array's elements. In this page, we will talk about some of the ways you can do that. 

# Set an Array Element

In addition to being used to get the element stored, the square bracket notation can also be used to _set_ the values of a specific array element. 

In the following, the element at index 2 is replaced with the String, `"Sue"`.

```js
let arrReplace = [ "orange", "banana", "grape", "strawberry" ];

arrReplace[2] // <- returns "grape"

arrReplace[2] = "Sue";
// the array -> [ “orange”, “banana”, “Sue”, “strawberry” ]

arrReplace[2] // <- returns “Sue"
```

#### The Setter in Empty Arrays

You can also use the square bracket setter notation to add values to an empty array. For example, we can place an element at index 0 with;

```js
let myArr = []; // create an empty array

myArr[0] = "Harry";

// myArr -> [ "Harray" ]
```

You can use this same technique to add elements that are beyond the length of the current array. If we continued on our above example, and added "Sally" at index 4, then JavaScript will fill the remaining elements in with `nil` values. 

```js
myArr[4] = "Sally";

// myArr -> [ "Harry", nil, nil, nil, "Sally" ];
```
