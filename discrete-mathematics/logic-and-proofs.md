---
description: >-
  A short introduction to proofs and mathematical logic. Written as notes for
  the course CS 70.
---

# Logic and Proofs

## Propositions

Propositions are statements that are either true or false. In examples, they are usually represented by the letters $$P, Q,$$and $$R.$$Here are some propositions.

* Steven is bald.
* 4 + 1 = 1000

## Truth Tables

Truth tables are a way of visualizing the possible outcomes of a statement. Here is an example of a truth table that shows the possible outcomes of $$(P \land Q).$$ 

| $$P$$  | $$Q$$  | $$(P \land Q)$$  |
| :--- | :--- | :--- |
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

{% hint style="warning" %}
If you don't know what $$\land$$ means, see [this page.](https://veriny.gitbook.io/berkeley/discrete-mathematics/set-notation)
{% endhint %}

## Quantifiers

If you've seen anything written by a mathematician, you've probably read the words "there exists" or "for all." There are two symbols for these, $$\exists$$ and $$\forall,$$ and they are called quantifiers. They are used to write most propositions. For example, here is a proposition that uses a quantifier.

$$
(\exists x\in \mathbb{N})[x + 1 = 2]
$$

This roughly translates to "there exists a natural number $$x$$ such that $$x + 1 = 2.$$" Of course, using basic algebra, we know what that number is.

## De Morgan's Laws

De Morgan's laws are used to negate propositions. To negate a statement, walk the negation through the statement, switching symbols as you go.

$$
\neg(P \land Q) = \neg P \lor \neg Q\\
\neg (P \lor Q) = \neg P \land \neg Q
$$

This follows pretty well logically. In the first example, if we know that in order for $$\neg(P \land Q),$$ then either $$P$$ or $$Q$$must be false, which is exactly what is written on the LHS of the equation.

Applying De Morgan's laws to quantifiers is just as simple.

$$
\neg(\forall x P(x)) = \exists x \neg P(x)
$$

This makes sense. Assuming that we are using both sides being true as our basis, if "for all $$x$$, $$P(x)$$ is true" is false, then the LHS is true. In order for the statement to be false, there needs to be some $$x,$$ at least one, that makes $$P(x)$$false. This is exactly what the RHS is saying.

{% hint style="info" %}
The negation of an implication $$(P \implies Q)$$ is a conjunction, $$(P \land \neg Q).$$ In order for the implication to be false, it must be the case that when $$P$$is true, $$Q$$is false.
{% endhint %}

## C and C

### The Contrapositive

The contrapositive of an implication $$(P \implies Q)$$ is $$(\neg Q \implies \neg P).$$ If one is true, the other is also true.

### The Converse

The converse of an implication $$(P \implies Q)$$is $$(Q \implies P).$$ If one is true the other is not necessarily true. If both are true, they have a  **iff** \(if and only if\) relationship.

## Tautologies

A **tautology** is a propositional statement/formula that is always true no matter what the result of the propositional variables is. For example, an obvious one would be $$(P \lor \neg P).$$ Whether $$P$$is true or false, the statement is always true. It's like saying "Steven is bald or he has hair."

## Direct Proof

The direct proof is probably the most common type of proof. The goal is to prove a statement, $$(P \implies Q).$$ The steps are as follows.

* Assume that $$P$$ is true.
* Show that under the above condition, $$Q$$is also true.

## Proof by Contraposition

In some cases, proving a statement $$(P \implies Q)$$might become overly complicated and annoying to think about. However, since the contrapositive $$(\neg Q \implies \neg P)$$ is true if the original statement is true, we can just do a direct proof of the contrapositive instead.

## Useful Tools for Proofs

| Thing | Tool |
| :--- | :--- |
| $$n$$ is even | $$\exists x \in \mathbb{Z}: 2x = n$$  |
| $$n$$ is odd | $$\exists x \in \mathbb{Z}: 2x + 1= n$$  |
| $$n$$ is rational | $$\exists x, \exists y \in \mathbb{Z} : \frac{x}{y} = n$$  |

{% hint style="warning" %}
 If you can't read that right column, see [this page.](https://veriny.gitbook.io/berkeley/discrete-mathematics/set-notation)
{% endhint %}

{% hint style="success" %}
TODO: Proof by contradiction, proof by cases, add more tools to useful tools section
{% endhint %}

 

