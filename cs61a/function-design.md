---
description: These notes are adapted from Prof. John DeNero's notes.
---

# Function Design

When designing functions, it is important to be aware of the set of all inputs **the domain** and set of all outputs **the range** that a function might return. This is largely conceptual.

### Short Guide to Designing Functions

* Give each function **exactly** one job.
* Don't repeat yourself. Define a process, then use that process many times. 
* Define functions generally.
* Find common structures to create shared implementations.

As for the syntax, here it is.

```python
def function_name(params):
    return <return expression>
```

Of course, you do not always have to return something. In which case, your function will return `None` by default.

### assert

Allows you to constrain the domain of a function.

```python
assert <boolean> <error message>
```

As an example, in the area function Prof. DeNero provided —

```python
def area(r, shape_constant):
    assert r > 0, 'Lengths must be positive'
    return r * r * shape_constant
```

It will throw an assertion error if r is not positive.



