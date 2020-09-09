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

When a name is created in the frame of a function that shares the name of its parent, it is used over the one in the parent. However, it does not modify the parent name.

```python
peego = 100
def malding(x):
    peego = 399
    return x + peego

print(malding(21))
print(peego)
```

In this case, the interpreter would print the following.

```bash
420
100
```

Here's the environment diagram for what we just ran. 

![Image Created By PythonTutor](../.gitbook/assets/image%20%283%29.png)

{% hint style="danger" %}
Note that the a function can only have a function as its parent frame if that function is nested inside another function. If a function is called inside another function,  the function's parent frame is STILL the frame it was defined in. 
{% endhint %}

