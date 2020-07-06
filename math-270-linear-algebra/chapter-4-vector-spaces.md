# Chapter 4: Vector Spaces

## Introduction to Vector Spaces

A vector space V is a set on which vector addition and scalar multiplication are defined. In order to be considered a space, the following ten axioms must be fulfilled be **every vector u, v, and w as well as every scalar c and d.**

* u + v is in V
* u + v = v + u
* u + \(v + w\) = \(u + v\) + w
* There exists a zero vector in vector space V such that u + 0 = u.
* cu is in V
* for every u in V there exists a -u in v such that u - u = 0.
* c\(u + v\) = cu + cv
* c\(du\) = cd\(u\)
* Iu = u

We've already seen some important vector spaces — R, the set of all real numbers, R^2, the set of all ordered pairs, and R^n, the set of all n sized tuples.

Here are some others.

* C\(-inf, inf\) is the set of all continuous functions defined on the real number line.
* C\[a, b\] is the set of all continuous functions defined on a closed interval \[a, b\]
* P is the set of all polynomials. P\_n is the set of all polynomials of degree &lt;= n.
* M\_m, n is the set of all m x n matrices.

{% hint style="info" %}
Be careful when identifying subspaces v.s. subsets. As an example, a vector space with any vector in it that contains three entries is in R\_3. but if it does not contain the zero vector it is only a subset, not a subspace.
{% endhint %}

#### Theorem

If v\_1, v\_2, v\_p are in the vector space V, then span{v\_1, v\_2, v\_p} is a subspace of v.

## Back to Col A and Nul A

Given A is an m x n matrix, Nul A is a subspace of R^n. This make sense, when we think about What Nul A is.

As for Col A, we know that Col A = Span {a\_1, a\_2, a\_n}, so we know that R^m by the theorem we discussed above. Note that the column space of A is all of R\_m only if there is a **pivot in every row.**

The column space of A is the range of the mapping of x -&gt; Ax.

The Nul A is called the **kernel** of the associated linear transformation — T\(x\) -&gt; 0. All of the x's that make up Nul A also make up the Kernel T.

Recall that T is a linear transformation if the following conditions are met.

* T\(u + v\) = T\(u\) + T\(v\)
* cT\(u\) = T\(cu\)

## Polynomial Subspaces

First, an example of a "vector" that exists in P^2.

$$
p(t)= c_1 + c_2t + c_3t^2
$$

This, of course, resembles the quadratic polynomial. In order to check if a set of polynomials is a subspace/subset of P^n, you should check for closure under scalar addition/multiplication, as well as that the set contains the zero vector, just as usual.

The **kernel** of a linear transformation T is the set of all vectors v such that L\(v\) = 0.

Given a linear transformation from a vector space V to a vector space W, the **range** of transformation T is the set of all vectors w in W such that there is an x in V where T\(x\) = w.

Standard basis for polynomial set P^n is following.

$$
\{1, t, t^2, t^n\}
$$

## B-coordinates

Let's say we know two bases for a vector space V.

$$
B= \{b_1, b_1\}\ \ C=\{c_1, c_2\}
$$

Let's also suppose that we know a vector x is in V and has "b coordinates" \[-1, 6\]. Further suppose that we know the following.

$$
b_1 = 2c_1 - 3c_2\\
b_2=c_1 + c_2
$$

Our task is to find the c coordinates of x. This is pretty straightforward, as we know that x = -1b\_1 + 6b\_2 \(in accordance with us knowing the b-coordinates of x being -1, 6\) and we know what b\_1 and b\_2 are in terms of c constants, so we just plug in and solve for the c coefficients.

However, there is quicker way. There exist _change of coordinates matrix ****_ which appear as follows.

$$
P [C\Longleftarrow B]=[[b_1]_c, [b_2]_c]
$$

Which in our example is the following. So just matrix multiply it by b coordinate matrix and you get answer.

$$
\begin{bmatrix}
2&1\\
-3&1
\end{bmatrix}
\begin{bmatrix}
-1\\
6
\end{bmatrix}=
\begin{bmatrix}
4\\
9
\end{bmatrix}
$$



Also. realize the following.

$$
P [C\Longleftarrow B]=P [B\Longleftarrow C]^{-1}
$$

## Markov Chains

First we need definition. A stochastic matrix is a matrix whose columns are probability columns. Meaning that the elements in the columns add up to one.

You then have your initial state vector, which is a probability vector that is nx1 dimensions. Then you multiply that by the stochastic and get a resultant nx1 vector. You can then repeat that as much as you want.

However, it can be useful to find the result of the Markov chain towards infinity. We call this the steady state, and there is a way to find it. The method is as follows.

$$
[M-I \ |\  0]
$$

Solve augmented matrix to find the steady state vector. Keep row reduce, will result in one free variable, meaning Nul \[M-I\] will contain one vector. Divide each element in that vector by the sum of its parts, and done.

## Row A

A Row space is a space in which the basis for it is made up of the rows of the nonzero rows of the row reduced form of A. Note the important relationship below.

$$
Row\ A\ =\ Col \ A^T
$$

Of course, dimension are same as well. 

