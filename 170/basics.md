# Basics

## Asymptotic Notation

Suppose we have two functions $$f$$ and $$g$$which map positive integers to positive integers. 

| Name | Notation | Definition |
| :--- | :--- | :--- |
| "Big-O" |  | Less than or equal to |
| "Little-O" |  | Less than |
| "Big-Omega" |  |  |
| "Little-Omega" |  |  |
| Theta |  |  |

## Master Theorem

A general formula to solve recurrence relation.\`Suppose we have a recurrence relation that resembles the following.

$$
T(n) = aT\left(\frac{n}{b}\right) + cn^d
$$

Then, we have $$\Theta(n^d)$$ if $$a < b^d$$, $$\theta(n^d\log(n))$$ if $$a = b^d$$, and $$\Theta(n^{\log_ba})$$ for the final case.



