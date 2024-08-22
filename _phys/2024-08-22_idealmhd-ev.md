---
layout: post
title: The Eigenvalues of Ideal Magnetohydrodynamics
date: 2024-08-22
collection: phys
---
### Introduction
&nbsp;&nbsp;&nbsp;&nbsp; Previously, I have written about [the Flux Jacobians of Ideal MHD](./2024-08-15_fluxjacobian). Recapping briefly, Ideal MHD is the simplest, meaningful, fluid description of a plasma. Its main application is in the field of fusion energy, where it is used to describe the equilibrium of magnetic configurations. In the absence of external sources of mass, momentum, energy, and magnetic field, we can write the system in the following form,

$$
\pdv{\vec{Q}}{}{t} + \mathbf{A}\pdv{\vec{Q}}{}{x} + \mathbf{B}\pdv{\vec{Q}}{}{y} + \mathbf{C}\pdv{\vec{Q}}{}{z} = 0
$$

where $\vec{Q}$ are the [Ideal MHD variables](./2024-08-15_fluxjacobian#eq:imhdvars), and $\mathbf{A}, \mathbf{B}$, and $\mathbf{C}$, are the [Flux Jacobians](./2024-08-15_fluxjacobian#the-flux-jacobians). These mathematical objects express how the fluxes vary with respect to the fluid variables, and they contain important information about the properties of the system.