# SVD/PCA

## SVD

Eigenvectors and eigenvalues are incredibly useful, but the problem is that non-square matrices do not have eigenvalues or eigenvectors. The solution to this is **singular value decomposition.** 

Given a matrix$$\textbf{M}$$, we want to find $$\textbf{M}\textbf{V}=\textbf{U}\Sigma$$ where $$\textbf{V}$$ \(n x n\) and $$\textbf{U}$$\(m x m\) are orthonormal and $$\Sigma$$ is sort of diagonal, in that the nonzero entries are along a diagonal but the matrix is not necessarily square. SVD is then written as 

$$
\textbf{M} = \textbf{U}\Sigma\textbf{V}^{\intercal}
$$

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

Because $$\textbf{M}^\intercal\textbf{M}$$ is square, we choose our $$\textbf{V}$$ matrix to be its orthonormalized eigenvectors, corresponding to non-zero and zero eigenvalues as mentioned earlier.

Along with these cheese strats, we claim that the columns of $$\textbf{V}_{col}$$ where $$\textbf{V}_{col}$$ is the left side of the matrix we split into two earlier is an orthonormal basis for the column space of $$\textbf{V}$$ .  This makes our $$\textbf{V}$$ matrix useful for calculations since it splits it up into a portion that's a basis for a column space \(the useful part\) and the portion that is a basis for the null space \(useless\).

As for the $$\textbf{U}$$ matrix, we have 

$$
\vec{u}_i = \frac{\textbf{M}\vec{v}_i}{\sqrt{\lambda_i}}
$$

for each $$\vec{v_i}$$ in $$\textbf{V}_{col}$$.

So far, we have $$\textbf{M}\textbf{V}=\textbf{U}\Sigma$$, where the LHS is split can be split into two sections, one part for the column space $$\textbf{M}\textbf{V}_{col}$$ and another for the null space $$\textbf{M}\textbf{V}_{null}$$, while the RHS is split into the diagonal portion $$\textbf{U}\Sigma_\alpha$$and the rest of the matrix which is just zeroes. The two sections of each side correspond to each other.

Now, we just need to decide the values of $$\Sigma$$. We choose that, in order for the equation to be true, $$\sigma_i=\sqrt{\lambda_i}$$. \(where $$\lambda_i$$ is an eigenvalue of $$\textbf{M}^\intercal\textbf{M}$$\)

### Procedure of determining SVD

Here is a summary of the above for finding the SVD.

* Compute $$\textbf{S} = \textbf{M}^\intercal\textbf{M}.$$ 
* Find the orthonormalized eigenvectors of $$\textbf{S}$$to be cols of$$\textbf{V}.$$
* Compute $$\textbf{U}$$ where the columns of it are $$\vec{u}_i = \frac{\textbf{M}\vec{v}_i}{\sqrt{\lambda_i}}$$, $$\lambda_i\neq0.$$ \(If there aren't enough for it to be a square, fill the rest with gram-schmidt\)
* Compute $$\Sigma$$ where the items on the diagonal are $$\sigma_i=\sqrt{\lambda_i}.$$ 

The result is $$\textbf{M} = \textbf{U}\Sigma\textbf{V}^{\intercal}.$$ 

{% hint style="info" %}
If the matrix is not full rank, your diagonal just gets cut off in your $$\Sigma$$ matrix and there will be some zeroes along the diagonal.
{% endhint %}

### Compact form of SVD

Having all of those zeroes is kind of cringe, so instead of the full SVD we can use a compact form. It basically cuts down the SVD so that, given $$r$$ is the rank of $$\textbf{M},$$ we have sizes $$\textbf{U}_{m\times r}, \Sigma_{r\times r},$$and $$\textbf{V}_{r\times{n}}.$$ Unfortunately, this means that our squareness is gone, which is also cringe.

## PCA

"Principal components" are the lower-dimensional structures in 2D data. For example, the principal component of a line in a 2D graph is the underlying 1D structure of the line. 

We can see this "collapse of dimensionality" by looking at $$\Sigma$$ and the number of singlular values there are. Of course, in real world applications, dimensionally-lost singular values won't perfectly be zero, but really close. I.E., if some of the singlular values are really small, don't pay attention to them. 

To find the principal component is to find some vector $$\vec{w}$$ that, when projected onto the data, gives the least error. Note that w would be a matrix for multiple principal components. 

If $$\vec{q_i}$$ was one data point, we would be minimizing

$$
\sum_{i=1}^n||\vec{q_i} - <\vec{q_i}, \vec{w}>\vec{w}||^2
$$

which simplifies to

$$
\sum_{i=1}^n||\vec{q_i}||^2 - <\vec{q_i}, \vec{w}>^2
$$

which is the same as wanting to maximize $$<\vec{q_i}, \vec{w}>^2.$$ 

We further simplify as 

$$
\text{max}\left[\vec{w}^\intercal\left(\sum_{i=1}^n \vec{q}_i\vec{q}_i^\intercal\right)\vec{w}\right]
$$

which can be written in matrix form as 

$$
\text{max}\left[\vec{w}^\intercal\textbf{Q}\textbf{Q}^\intercal\vec{w}\right]
$$

We can then substitute the $$\textbf{Q}$$ matrices with their SVDs. Doing, so, we can simplify and find that:

* If we want  $$i$$ principal components along the rows, we pick $$\vec{u}_1 ... \vec{u}_i.$$
* If we wanted them along the rows, we pick $$\vec{v}_1 ... \vec{v}_i.$$ 

{% hint style="success" %}
TODO: PCA
{% endhint %}



