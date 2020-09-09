# Matrix Algebra

## The Basics of Matrix Algebra

If A is an **m x n** matrix and B is an **n x p** matrix, AB will result in an **m x p** matrix.

$$
Given\ that\ the\ columns\ of\ b\ are\ b_1,b_2,b_p\\
AB= [Ab_1, Ab_2, Ab_3, Ab_p]
$$

Here is an example using a 2x2 A matrix and a 2x3 B matrix.

$$
A = \begin{bmatrix}
2 & 3 \\
1 & 5
\end{bmatrix} 
B = \begin{bmatrix}
4 & 6 & 8\\
2 & 4 & 6
\end{bmatrix}
$$

$$
AB=
\begin{bmatrix}
\begin{bmatrix}
2 & 3 \\
1 & 5
\end{bmatrix} 
\begin{bmatrix}
4\\
2
\end{bmatrix} & \begin{bmatrix}
2 & 3 \\
1 & 5
\end{bmatrix} 
\begin{bmatrix}
6\\
4
\end{bmatrix} &
\begin{bmatrix}
2 & 3 \\
1 & 5
\end{bmatrix} 
\begin{bmatrix}
8\\
6
\end{bmatrix} 
\end{bmatrix}
$$

#### A few theorems of note:

Given A is a m x n matrix and B and C are matrices with sizes for which the following are defined, the following are true.

* A\(BC\) = \(AB\)C
* A\(B + C\) = AB + AC
* \(B + C\)A = BA + CA
* r\(AB\) = \(rA\)B = A\(rB\)

However, the following are typically not true.

* AB = BA
* AB = AC meaning B = C
* AB = 0 therefore A = 0 or B = 0

## Transposing Matrices

The transpose of A, denoted as A^T is a matrix whose columns are found by the rows of A.

$$
A= 
\begin{bmatrix}
1 & 5 & 6\\
2 & 0 & 7
\end{bmatrix}
A^T= 
\begin{bmatrix}
1 & 2\\
5 & 0\\
6 & 7
\end{bmatrix}
$$

Of course, there are a few theorems associated with transposing as well.

* \(A^T\)^T = A
* \(A + B\)^T = A^T + B^T
* \(rA^T\) = rA^T
* \(AB\)^T = B^T A^T

## Inverse Matrices

A square matrix is invertible if it satisfies the following conditions.

$$
CA=I_n\\
AC=I_n\\
The\ matrix\ is\ square\
$$

The matrix C is the inverse matrix of A. C is unique. Inverse matrices are denoted by ^-1. We can use the determinant to find out of a matrix has an inverse and what the inverse is.

The determinant is denoted as follows.

$$
Given\ matrix\ A\\
A=
\begin{bmatrix} 
a & b\\
c & d
\end{bmatrix}\\
The\ determinant\ is\\
ad-bc
$$

If the determinant does not equal zero, there exists an inverse.

$$
A^{-1}=
\frac{1}{ad-bc}
\begin{bmatrix}
d&-b\\
-c&a
\end{bmatrix}
$$

{% hint style="info" %}
If A has an inverse, then for each b in R^n, the equation Ax = b has a unique solution, x = A^-1b.
{% endhint %}

Also note the effects of inversion on the products of invertible matrices.

$$
(AB)^{-1}=B^{-1}A^{-1}
$$

{% hint style="info" %}
The order of the above theorem is important. It cannot be swapped.
{% endhint %}

## Inverses of non-square matrices

The inverse of a non-square matrix can be found by row-reducing the following matrix.

$$
[A\ |\ I_n]
$$

{% hint style="info" %}
Reminder that I\_n is an n x n identity matrix.
{% endhint %}

By row-reducing A to get I\_n, you should have this matrix.

$$
[I_n\ |\ A^{-1}]
$$

If A does not reduce to I\_n, A is not invertible.

## The Invertible Matrix Theorem

There are an absolute **slew** of logically equivalent statements to the invertible matrix theorem, which is simply that A is an invertible matrix.

If A^-1 exists, then the following also holds true.

* A is row equivalent to I\_n.
* A has n pivot positions.
* Ax = 0 only has the trivial solution.
* Columns of A are linearly independent.
* The transformation T: x -&gt; Ax is one-to-one.
* The equation Ax = b has at least one solution for each b in R^n \(the unique solution, A^-1b\).
* The columns of A must span all of R^n
* T: x-&gt; Ax is onto R^n
* There exists a matrix D that AD = I\_n
* The transpose of T is invertible.

## Subspaces

A subspace of R^n is defined as a set H in R^n that satisfies the following conditions:

* Vector O is in H
* H is closed under vector addition — meaning that if U and V are in H, then U + V must be in H.
* H is closed under scalar multiplication — meaning that if u is in H than Cu must be in H.

The **column space** of a matrix \(with the notation Col A\) is the set of all linear combinations of the columns of A. Col A is a set of vectors that live in R^m.

The **null space** of matrix A is denoted by all vectors x such that Ax = 0. Notation is **Nul A.**

**Nul A is the set of vectors that live in R^n.**

A basis for a subspace H in R^n is a set of vectors that do 2 things.

* The set of vectors is linearly independent in the subspace H.
* Those vectors span all of the subspace H.

The pivot columns of A forms a basis for Col A. **NOT the pivot columns of a row reduced version of A.**

