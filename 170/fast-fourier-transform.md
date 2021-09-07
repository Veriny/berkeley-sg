---
description: Please let me off the waitlist for this class.
---

# Fast Fourier Transform

## Polynomial Multiplication

Suppose we have two input polynomials,

$$
A(x) = a_0 + a_1x + a_2x^2 ... a_{n-1}x^{n - 1}\\
B(x) = b_0 + b_1x + b_2x^2 ... b_{n-1}x^{n - 1}
$$

such that $$n = 2d - 1.$$ 

### Relationship Between Polynomial and Integer Multiplication

Given ints $$\alpha, \beta$$, and we want $$\gamma = \alpha\beta.$$ Given the coefficients, we want to compute the coefficients of the product polynomial. 

### Possible Algorithms:

First, we have the straight-forward algorithm. We have

$$
c_0 = a_0b_0\\
c_1 = a_0b_1 + a_1b_0\\
c_k = \sum_{j= 0}^ka_jb_{k - j}
$$

Total time to compute this is $$O(N^2)$$ since we need to loop over $$j = 0$$to $$N - 1$$. Computing each of $$\frac{c_n}{4}$$requires $$\geq \frac{N}{4}$$flops, meaning we're gonna have $$\Theta(N^2)$$flops. 

Second, we have a Karatsuba related approach. Recall that we have

$$
A(x) = a_0 + a_1x + a_2x^2 ... a_{n-1}x^{n - 1}\\
B(x) = b_0 + b_1x + b_2x^2 ... b_{n-1}x^{n - 1}
$$

We can split this up into lows and highs as we did for integer multiplication, that is 

$$
A(x) = A_l(x) + x^{\frac{n}{2}} + A_h(x)\\
B(x) = B_l(x) + x^{\frac{n}{2}} + B_h(x)
$$

It's the same as last time — you'd get four recursive polynomial multiplications to do with half the degree, but applying the Karatsuba trick, we'd only have three polynomial multiplications, meaning we'd have, just like Karatsuba, $$\Theta(N^{\log_23}).$$ 

Finally, we have an even faster approach using polynomial interpolation. 

{% hint style="info" %}
Polynomial intermolation states that a degree $$< N$$polynomial can be uniquely determined by its evaluation on $$N$$distinct points \(refer to CS 70, Lagrange interpolation\)
{% endhint %}

Instead of directly computing the coefficients of C, we can determine $$C(x_0) ... C(x_{n - 1})$$. We can therefore compute the evaluation of $$A(x)$$and $$B(x)$$on $$N$$distinct points each, then multiply them, and then just interpolate them to find $$C(x).$$

## Fast Fourier Transform

{% hint style="info" %}
Clarification: The Discrete Fourier Transform is a matrix, and the Fast Fourier Transform is an algorithm.
{% endhint %}

We view the algorithm as evaluating $$P(1) ... P(\omega) ... P(\omega^{N - 1})$$, in other words, applying DFT to the vector of P's coefficients. 

