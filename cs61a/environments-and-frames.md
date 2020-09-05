---
description: These notes are adapted from Prof. John DeNero's notes.
---

# Environments and Frames

Having an understanding of environments and frames is important to creating clean, running python code. It is important to know what **names** are accessible and when. Take the following example.

```python
steego = 789
def peego(x):
    return x + steego
peego(333)
```

Whenever a function is called, it creates a new frame for itself, with the **parent** of that frame being the frame it was called in. In this case, two **names**, `steego` and `peego`, were bound to **objects,** `789` and a `function`, in the **global frame**. In line four, `peego` was called, creating a new frame. Its parent is the **global frame.** A child frame has access to all the names defined in its parent frame, so `peego` can safely use the name `steego`. However, a parent frame **cannot** use the name in its child. As such, we can not use `x` in the global frame. 

Let's look at an example with a higher-order function. The CS61A classic, `make_adder`.

```python
def make_adder(x):
    def adder(y):
        return x + y
    return adder

peego = make_adder(60)
peego(9)
```

The name `make_adder` is bound to the global frame. The name peego is bound to `adder` \(as it is a function that is returned by `make_adder`\) whose parent is `make_adder`. As such, when it evaluates `x + y`, it has access to both `x` \(in its parent frame, `make_adder`\) as well as `y` \(in its own frame\). 

