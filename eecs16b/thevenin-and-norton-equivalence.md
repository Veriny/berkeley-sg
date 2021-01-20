---
description: Adapted from 16B notes.
---

# Thevenin and Norton Equivalence

## Resistors in Series and in Parallel

Resistors in parallel and in series can be simplified as follows.

$$
R_{\sum series} = R_1 + R_2 + R_3 + ... + R_n \\
R_{\sum parallel} =  (\frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3} + ... +  \frac{1}{R_n})^{-1}
$$

## Thevenin Equivalent Circuits

Thevenin equivalent circuits are circuits that contain a voltage source and a resistor.

![Credit: EECS 16B Note 0B](../.gitbook/assets/image%20%287%29.png)

You can find the values, $$R_{Th}$$ and $$V_{Th}$$, as follows. Assume that you're finding the Thevenin equivalent of Ckt A.

* Find the voltage across the terminals of Ckt A. This is $$V_{Th}$$.
* Find the equivalent resistances of the elements in Ckt A.  This is the value of $$R_{Th}$$.

{% hint style="success" %}
Resistors in series have equivalent currents across them.
{% endhint %}

## Norton Equivalent Circuits

Norton equivalent circuits are circuits that contain a current source and a resistor in parallel. 

![Credit: EECS 16B Note 0B](../.gitbook/assets/image%20%286%29.png)

You can find the values, $$R_{No}$$ and $$I_{No}$$, as follows. Assume that you're finding the Norton equivalent of Ckt A.

* Find the voltage across the terminals of Ckt A. This is $$R_{No}$$. Note that$$R_{Th} = R_{No}$$!
* Find the current flowing into Ckt A. This is $$I_{No}$$.

{% hint style="success" %}
Resistors in parallel have the same voltage.
{% endhint %}

