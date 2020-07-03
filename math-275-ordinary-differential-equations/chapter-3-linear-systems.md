# Chapter 3: Linear Systems

## Harmonic Oscillators

When Newton's second law is applied to a mass-spring system to create simple harmonic motion, we get the following equation.

$$
-ky-b\frac{dy}{dt}=m\frac{d^2y}{dt^2}
$$

The few terms to keep in mind are -ky, which comes from Hooke's law, the -b term comes from the force from damping. This differential equation is typically written with all the terms on one side of the equation equaling zero.

We can, of course, turn this into a linear system.

$$
\frac{dy}{dt}=v\\
\frac{dv}{dt}=-\frac{k}{m}y-\frac{b}{m}v
$$

## A Microeconomic Model

We'll just use the example of Cafés. Let's say there are two competing cafés. We can have the profits of one affect the other with a linear model of differential equations.

$$
\frac{dx}{dt}=ax +by\\
\frac{dy}{dt}=cx+dy
$$

Assuming that x\(t\) and y\(t\) are the daily profits from the café respectively and t is measured in days. 

You might have noticed that when a and d are zero, the solution curves are just circles, but when a and are nonzero, you get a spiral solution curve with an oscillating profit.

## Matrices and Linear Systems

Note: For reading on the basics about matrices, please see my notes on MATH 270 — Linear Algebra. If you do so the next few sections in these notes should be easier to understand.

The basic form of a linear differential equation as a matrix is the following.

$$
\boldsymbol{Y}(t)=
\begin{bmatrix}
ax+by\\
cx+dy
\end{bmatrix} 
\frac{d\boldsymbol{Y}}{dt}=
\begin{bmatrix}
\frac{dx}{dt}\\
\frac{dy}{dt}
\end{bmatrix}
$$

The matrix **A** created by the coefficients of the system \(a, b, c, d\). Note that the above two equations are separate and GitBook is showing them too close together.

### Equilibrium Solutions in Matrices

The most basic of matrix relationships is the following relationship, that which gives the solutions to the equilibrium points.

$$
\boldsymbol{AY}_0=
\begin{bmatrix}
0\\
0
\end{bmatrix}
$$

As we learned in linear algebra, this is the trivial solution of the matrix-vector equation.

In the context of differential equations, the determinant of the A matrix tells us that if det A exists there are equilibrium points other than the origin and vice versa.

A matrix with a determinant of zero is called a **degenerate matrix.** \(If you remember from linear algebra, this means that the inverse of the matrix in question does not exist.\)

## The Linearity Principle



