---
layout: post
title: Plasmas as Fluids
date: 2024-07-27
collection: phys
---
&nbsp;&nbsp;&nbsp;&nbsp; Doing physics is an act of balancing tractability against fidelity. The more faithful that our model is to the "ground truth", i.e., an exact description of how nature would behave written down in the language of differential equations, and linear algebra, the less amenable it is to solution. The silver lining to this is that frequently, we don't need complete details.  

#### Deriving Multi-Fluid Equations
&nbsp;&nbsp;&nbsp;&nbsp; The single-particle distribution function, $f(\vec{x}, \vec{v}, t)$, is an example of this. A more complete representation of the phase-space dynamics would treat correlations between particles, and use a two-, three-, or even N-particle distribution function, $f_{2}(\vec{x}\_{1}, \vec{v}\_{1}, \vec{x}\_{2}, \vec{v}\_{2}, t)$, $f_{3}(\vec{x}\_{1}, \vec{v}\_{1}, \vec{x}\_{2}, \vec{v}\_{2}, \vec{x}\_{3}, \vec{v}\_{3}, t)$, $f_{N}(\vec{x}\_{1}, \vec{v}\_{1}, \vec{x}\_{2}, \vec{v}\_{2}, \ldots, \vec{x}\_{N}, \vec{v}\_{N}, t)$, to capture these. If our purposes were to study the collective behavior of a plasma, then this level of detail would be pointless, cumbersome, and distracting. In a plasma, particles behave collectively due to the presence of electromagnetic fields. Consequently, by analyzing the phase-space dynamics of a single particle, we can obtain insight into the dynamics of the whole.  

&nbsp;&nbsp;&nbsp;&nbsp; Doing so directly is the domain of [kinetic theory](./2024-07-10_plasmakinetics). There, we typically start with the Boltzmann equation for a species, $s$,

$$
\begin{align}
\pdv{f_{s}}{}{t} + \vec{v}\cdot\nabla f_{s} + \vec{a}\cdot\grad_{v}f_{s} = \left.\pdv{f_{s}}{}{t} \right|_{coll.}
\end{align}
$$

which describes the evolution of the distribution function subject to collisions between particles. By taking velocity-space moments of this equation, we can derive a series of fluid equations which describe the evolution of bulk physical quantities that describe the macroscopic behavior of the particle species, $s$.

<!-- References -->
<!-- Higher-particle distribution functions: Krall and Trivelpiece -->
<!-- Multi-fluid derivation: Fitzpatrick -->