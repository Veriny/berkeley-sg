# Asymptotics

## Scaling

The **scaling** of an algorithm refers to its behavior in terms of speed and resource consumption as the number of things it has to process increases. 

We want our "interpretation" of how long an algorithm takes to be mathematical, as well as consider only the worst case.

## Notation

| Symbol | Use |
| :--- | :--- |
| $$\Theta(N)$$  | Denotes the _family of functions_ that grow with the order specified in the notation. Mathematically, it means that given $$R(N) \in \Theta(f(N))$$ , there are two positive constants $$k_1,k_2$$ , where $$k_1f(N)\leq R(N)\leq k_2f(N)$$. |
| $$O(N)$$  | If you think of big theta as equals, you can think of big O as less than or equal. This just means that $$R(N) \in O(f(N))$$ , then $$R(N)\leq k_2f(N)$$ for some positive integer $$k_2$$. |

{% hint style="success" %}
TODO: Big o and big theta notation
{% endhint %}

