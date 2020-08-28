---
description: These notes are adapted from Prof. John DeNero's notes.
---

# Call Expressions, Names, etc.

An example of a call expression is the following.

```python
operator(operand, operand)
```

There is a specific evaluation procedure for call expressions.

* Evaluate the operator, and then the operand expressions.
* Apply the operator to the evaluated operand expressions.

{% hint style="info" %}
Note that you can **nest** call expressions. In other words, operands can be other operator with its own operands.
{% endhint %}

Things like numbers, names, etc are just called primitive expressions.

Evaluation rules for assignment statements.

* Evaluate all expressions to the right of = from left to right
* Then, bind the names.

Evaluation rules for assignment statements.

* Create a function with &lt;name&gt;\(&lt;parameters&gt;\)
* Set the body of the function to everything indented after the first line but do not execute it
* Bind the name to the function in the current frame.



