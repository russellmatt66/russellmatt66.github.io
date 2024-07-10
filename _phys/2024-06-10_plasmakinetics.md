---
layout: post
title: Introduction to Plasmas - Plasma Kinetics
collection: phys
---
### Plasmas - They are Cool
&nbsp;&nbsp;&nbsp;&nbsp;If you're anything like me, what attracted you to plasmas, besides nuclear fusion, was the name. Coined by Irving Langmuir, one of the pioneers of plasma physics, during his study of electric discharges in the '20s, he imagined the positive and negative charges under his study to be entrained in a fluid medium, like the red and white blood cells in a human body are entrained in blood plasma. This idea has turned out to be false, although the name has stuck. In a plasma, there are only positive and negative charges. Oftentimes, the conditions are right for a plasma to behave like a fluid, but that is a subject for a [different post](./2024-06-10_fluidplasmas). 

&nbsp;&nbsp;&nbsp;&nbsp;The pressing issue that remains is *how* do you analyze such a system? [Plasmas can span many scales](./2024-06-9_introplasmas-multi), and one of the requirements for a collection of charged particles to behave as a plasma is that there be a very large number of particles in a Debye sphere. [Each of these single particles moves according to the electromagnetic field it experiences](./2024-06-8_introplasmas-spm), so, for a meter-long plasma with density $n = 10^{19}$ $m^{-3}$, this gives approximately $10^{19}$ coupled ODEs to solve!

#### Statistical Mechanics
&nbsp;&nbsp;&nbsp;&nbsp;This issue of very large numbers is a classic problem in dynamics that lead to the development of statistical mechanics. "Stat mech", as its known, comes up with measurable predictions about the behavior of physical systems by taking moments of a distribution function which is defined on a phasespace, $(\vec{r}, \vec{v})$. 

This distribution function, $f(\vec{r}, \vec{v}, t)$, is the density of particles in an infinitesimal volume of phase space centered at $(\vec{r}, \vec{v})$. By integrating over velocity-space we can obtain a value for the number density of particles,

$$
\begin{equation}
n(\vec{r}, t) = \int f(\vec{r}, \vec{v}, t)d\vec{v}
\end{equation}
$$