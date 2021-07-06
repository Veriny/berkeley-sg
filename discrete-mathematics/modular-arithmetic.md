# Modular Arithmetic

## Primes and Greatest Common Divisors

We know that a divides b, written as a\|b, if there exists an integer such that b = ak. As for the greatest common divisor, it is the greatest integer d such that d\|a and d\|b.      

### The Fundamental Theorem of Arithmetic

This states that every integer greater than 2 can be expressed uniquely as a product of primes. A property of this is that 

$$
GCD(a, b) = \sum p_n^{min(\alpha_n, \beta_n)}
$$

Where alha and beta are the exponents of the primes.

### The Division Algorithm

Let a and b be integers. This means that there are unique integers q and b wuth 0 leq r less than b such that a is equal to qb .+ r. 

### GCD Algorithms

The Euclidean algorithm: take the GCD of a and b, if b is zero return a, else return teh gcd of b, a mod b,

Bezout's theorem states that there exists coeffiecent integers x and y such that ax + by = GCD \(a, b\).

```python
def gcd(a, b):
    if b == 0:
        return a
    return gcd(b, a mod b)
```

## Modular Equivalences

Let a, b be integers and m be a positive integers. if m divides a - b, we say that a is congruent to b modulo m.

Two integers are congruient if they have the same remainders.

Another corollary is that if a is congruent to b mod m, we know that there exists some integer k such that a = km + b.

If a is congruent to b mod m, and c is congruient to d mod m, then a + c = b + d mod m.

## Inverses

We say that if ax = 1 mod m, x is an inverse of a mod m, written as a^-1 mod m. 

## Exponentiation

We want to compute a^n mod m. We can split a^n into its constituents, which is a^k a^k if n is even, and a^k a^k a if it is odd.

## Linear Congruences

A linear cogruence is of the fform ay = b \(mod m\). 

If ax is congruent to 1 \(mod m\) we say that x is the inverse of muodule m.

The inverse can be found iusing the extended euclidean algorithm

Given an equation, ax cong b mod m, check for solutions by seeing if gcd \(a, m\) = 1

## Chinese Remainder Theorem



