---
title: Program Logic
module: 7
jotted: false
---

# Program Logic

In general, _program logic_ is a concept where the desired outcomes for a program (social, computer, institutional, etc.) are used to derive the "how-to" of getting there. [Program logic](http://www.ghd.com/pdf/4.%20Program%20Logic.pdf) is then used to evaluate the effectiveness of a program, plan, or system.

For our purposes, we will consider _program logic_ to be goals for a software program, that are then used to derive instructions towards their end.  We can describe the program logic of software based on _what it is suppose to do_, and _how we are making it do that_.

## Control Flow

[_Control flow_ (also known as _program flow_)](https://en.wikipedia.org/wiki/Control_flow), is the set of instructions defining _how to_ accomplish the program's goals. In computer science, a program is typically comprised of a set of instructions (aka, _statements_), which _flow_ from one to the next based on their order and any sets of _conditions_.

### Sequential Flow

In all of the code programs we have written or studied so far, the control flow has been _sequential_. That is, each statement (essentially, each line of code), is executed in order. When one statement is finishes, the next is then executed.

![Demonstration of "Sequential Program Flow"](../imgs/SequentialProgramFlow.png 'Demonstration of "Sequential Program Flow".')

### Conditional Flow

In addition to _sequential flow_, there is _conditional flow_ or _choice flow_ in programs. In _conditional flow_, the program is presented with a choice which allows it to execute one statement or another. Following the execution of the chosen statement, the program continues with _sequential flow_.

![Demonstration of "Conditional Program Flow"](../imgs/ConditionalProgramFlow.png 'Demonstration of "Conditional Program Flow".')

The path of a condition statement is determined through [Boolean logic](http://www.i-programmer.info/babbages-bag/235-logic-logic-everything-is-logic.html) (i.e. is some condition _true_ or _false_). If the condition statement or test results in a _true_ value it chooses one way. Likewise, if the condition statement results in a _false_ value, it chooses the other way.
