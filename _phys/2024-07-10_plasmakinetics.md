---
layout: post
title: Plasma Kinetics
date: 2024-07-10
collection: phys
---
#### Plasmas - They are Cool
&nbsp;&nbsp;&nbsp;&nbsp;If you're anything like me, what attracted you to plasmas, besides nuclear fusion, was the name. Coined by Irving Langmuir, one of the pioneers of plasma physics, during his study of electric discharges in the '20s when he imagined the dynamic positive and negative charges under his study to be entrained in a fluid medium, like the red and white blood cells in a human body are entrained in blood plasma, this idea has turned out to be false, although the name has stuck. In a plasma, there is no entraining medium, only positive and negative charges moving around under the influence of electromagnetic fields. Oftentimes, the conditions are right for a plasma to behave *like* a fluid, but that is a subject for a [different post](./2024-06-10_fluidplasmas). Even when this is the case, real plasmas never have phenomena happening at only one scale, i.e., the scalelength of the fluid behavior. For example, the equilibrium of a fusion plasma is readily described by the [Ideal MHD](../fusion/2024-07-8_idealmhd) model, but the important features of the nonequilibrium behavior, e.g., the deflagration mode (the shockwave that explodes through the device when fusion reactions begin), are based on kinetic phenomena happening at much a smaller scale.   

&nbsp;&nbsp;&nbsp;&nbsp;The pressing issue weighing on the mind of one who wants to study kinetic phenomena is *how* do you analyze such a system? [Plasmas can span many scales](./2024-06-9_introplasmas-multi), and one of the requirements for a collection of charged particles to behave as a plasma is that there be a very large number of particles in a Debye sphere. [Each of these single particles moves according to the electromagnetic field it experiences](./2024-06-8_introplasmas-spm), so, for a meter-long plasma with density $n = 10^{19}$ $m^{-3}$, this gives approximately $10^{19}$ coupled ODEs to solve! This issue of very large numbers is a classic problem in dynamics that lead to the development of statistical mechanics. "Stat mech", as it's known, solves this problem by coming up with measurable predictions about the behavior of physical systems by taking moments of a distribution function which is defined on a phasespace, $(\vec{r}, \vec{v})$. 

#### Distribution Functions
<!-- Start from the Klimontovich equation, and build down towards single-particle distribution function -->

<!-- &nbsp;&nbsp;&nbsp;&nbsp;This distribution function, $f(\vec{r}, \vec{v}, t)$, (strictly-speaking, the "single-particle" distribution function) is defined as the density of particles in an infinitesimal volume of phase space, which is centered at $(\vec{r}, \vec{v})$. 

By integrating over velocity-space we can obtain a value for the number density of particles,

$$
\begin{equation}
n(\vec{r}, t) = \int f(\vec{r}, \vec{v}, t)d\vec{v}
\end{equation}
$$ -->

<!-- References -->
<!-- Setsuo Ichimaru -->
<!-- Krall and Trivelpiece -->