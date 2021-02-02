---
description: Adapted from EECS 16B notes.
---

# RC Circuits & Transient Analysis

## Piecewise-Constant Input

A capacitor charging to an applied voltage can be modeled by the following equation.

$$
V(t) = V_0(1 - e^\frac{-t}{\tau})
$$

where $$\tau$$ is the time constant $$RC$$ . 

Likewise, a capacitor discharging can be modeled as follows.

$$
V(t) = V_0(e^\frac{-t}{\tau})
$$

In terms of a piece-wise constant input, we can use the two equations to model the discharging and charging of the capacitors if we are given some initial conditions. 

## Solutions for General Input Functions

Given the general input function

$$
\frac{d}{dt}V(t) = -\lambda V(t) - \lambda u(i\Delta)
$$

where $$u(i\Delta)$$ is a constant, the value of the input function at $$t = i\Delta$$, we have a solution.

$$
x(t) = x_0e^{\lambda t} + \int_0^te^{\lambda(t-\theta)}u(\theta)d\theta
$$

