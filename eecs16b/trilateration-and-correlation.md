---
description: Adapted from UC Berkeley's EECS 16A notes.
---

# Trilateration and Correlation

## Trilateration

**Trilateration** is a technique that involves using the geometry of circles to find an approximate or exact location of an object. 

![Source: https://www.researchgate.net/figure/The-Trilateration-algorithm\_fig4\_224144937](../.gitbook/assets/image%20%284%29.png)

Geometrically, this means that if you know the position of three points and each of their distances to a point that you want to find, you can create three circles, the intersection of which is the location that you want to find.

Here's how it works mathematically. Let's take the distances and points below, and assume that we know the positions of the points and the distances to our desired object.

![Credit: EECS 16A course staff](../.gitbook/assets/image%20%285%29.png)

We can write the distances as a set of vector equations.

$$
||\vec{x}  - \vec{a}_1||^2 = d_1^2\\
||\vec{x}  - \vec{a}_2||^2 = d_2^2\\
||\vec{x}  - \vec{a}_3||^2 = d_3^2
$$

We can use distance formula with the components.



## 



