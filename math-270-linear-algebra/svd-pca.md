# SVD/PCA

## SVD

Eigenvectors and eigenvalues are incredibly useful, but the problem is that non-square matrices do not have eigenvalues or eigenvectors. The solution to this is **singular value decomposition.** 

Given a matrix$$\textbf{M}$$, we want to find $$\textbf{M}\textbf{V}=\textbf{U}\Sigma$$ where $$\textbf{V}$$ and $$\textbf{U}$$ are orthonormal and $$\Sigma$$ is sort of diagonal, in that the nonzero entries are along a diagonal but the matrix is not necessarily square. 

{% hint style="info" %}
$$\textbf{V}$$ and $$\textbf{U}$$ being orthonormal is because we want the same matrix-vector relationship that we would have if $$\textbf{M}$$ was symmetric.
{% endhint %}

Assuming that we have $$p$$ nonzero eigenvalues and $$q$$ eigenvalues that are just zero, we can rewrite the RHS of the equation as follows.

$$
\textbf{M}
\begin{bmatrix}
\vec{v_1} ...\vec{v_p} | \vec{v}_{p + 1} ...\vec{v}_{p + 1 + q}
\end{bmatrix}
$$

The right side of that matrix that we just split into two is a basis for the null space of $$\textbf{C}$$.

Now, we need to cheese our equation enough to the point where it can sort of become a scuffed symmetric matrix. We will use the following properties to do so.

$$
\text{Null}(\textbf{M}^\intercal\textbf{M}) = \text{Null}(\textbf{M})\\
(\textbf{M}^\intercal\textbf{M})^\intercal = \textbf{M}^\intercal\textbf{M}\\
\text{Eigenvalues of }\textbf{M}^\intercal\textbf{M} \text{ are real and non-negative.}
$$



{% hint style="success" %}
TODO: PCA
{% endhint %}



