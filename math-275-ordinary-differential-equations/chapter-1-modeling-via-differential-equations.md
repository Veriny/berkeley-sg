# Chapter 1: Modeling via Differential Equations

## The Basic Unlimited Population Growth Model

The basic unlimited population growth model states, simply, that the rate of growth of the population is proportional to the rate of growth of the population.

$$
\frac{dP}{dt}=kP
$$

Now, some vocabulary. The **equilibrium solution** is a solution to the differential equation in which the derivative is zero everywhere. In this case, it would be   
P = 0.

The **initial condition** of a differential equation is the initial value of P\(t\) at t = 0. In other words, the constant C we get from integration.

## The Logistic Population Model

The logistic population model states that if the population is small, the growth is proportional to size, and if it is too large and unsustainable, the population will decrease.

$$
\frac{dP}{dt}=k(1-\frac{P}{N})P
$$

The additional variable, N, is the carrying capacity. We observe that the equilibria positions are N and 0.

{% hint style="info" %}
Note that the above model is **non-linear.**
{% endhint %}

## Predator-Prey Systems

Notation wise, prey are denoted as rabbits \(R\) and predators are denoted as foxes \(F\). This type of model follows the following four assumptions.

* When there are no foxes present, rabbits reproduce at a rate proportional to their population.
* The rate at which rabbits are hunted is proportional to the rate at which rabbits and foxes interact.
* When there are no rabbits present, the foxes die at a rate proportional to the population.
* Foxes reproduce at a rate proportional to the number of rabbits eaten.

We also set the following four additional parameters.

* α = growth rate coefficient of rabbits
* β = constant of proportionality for the number of interactions in which the rabbit is eaten
* γ = death rate coefficient of foxes
* δ = constant of proportionality for the benefit to the fox population of an eaten rabbit.

With the above parameters and assumptions in mind, we can build the following model.

$$
\frac{dR}{dt}= \alpha R- \beta R F\ \ \ \ \ \ \ \ 
\frac{dF}{dt} = \gamma F + \delta RF
$$

## The Linearization Theorem

Suppose y\_0 is an equilibrium point of the differential equation dy/dt = f\(y\) where f is continuously differentiable. 

* Where f' is less than zero, then y\_0 is a sink \(stable\)
* Where f' is greater than zero, than y\_0 is a source \(unstable\)
* Where f' is zero, we need more information.

