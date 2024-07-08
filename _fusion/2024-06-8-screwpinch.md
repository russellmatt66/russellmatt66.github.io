---
layout: post
title: Ideal MHD
collection: phys
---
### Introduction   
&nbsp;&nbsp;&nbsp;&nbsp;Ideal Magnetohydrodynamics (MHD) is the simplest model for describing the behavior of a fluid plasma. Due to this simplicity there are some restrictions on when we, strictly-speaking, can apply it. Funnily enough, in practice Ideal MHD applies more than it should. The reason why plasma scientists care so much about Ideal MHD is that it describes the equilibrium of magnetic fusion reactors. Although it is the simplest fluid model of a plasma, it is still quite complicated. In the absence of source terms, this is what it looks like,

$$
\pdv{\vec{Q}}{}{t} + \div \textbf{T} = 0
$$ 

If source terms were present, then they would show up on the right-hand side (RHS) of this expression, instead of 0. Without source terms, the above is what's known as a $\textit{homogeneous}$ partial differential equation (PDE), i.e., one that is zero everywhere. Homogeneous PDEs are by no means easy to solve, but $\textit{heterogeneous}$ PDEs, ones that are not zero everywhere, are even harder. PDEs are ubiquitous in science, and engineering. 

&nbsp;&nbsp;&nbsp;&nbsp;$\vec{Q}$ is the vector of Ideal MHD variables. These are the physical quantities which characterize the state of the plasma being studied by the Ideal MHD model. There are eight of them,

$$
\vec{Q} = \colvec{\rho \\ \rho u \\ \rho v \\ \rho w \\ B_{x} \\ B_{y} \\ B_{z} \\ e}^{T}
$$

$\rho = m_{i}n$ is the fluid density, the $\rho\vec{u}$ terms are the fluid momentum in the x-, y-, and z-directions, $\vec{B}$ is the magnetic field, and $e = \frac{p}{\gamma - 1} + \frac{\rho v^{2}}{2} + \frac{B^{2}}{2\mu_{0}}$ is the internal energy of the plasma, which is the sum of the plasma's thermal energy, kinetic energy, and magnetic energy. $p = nk_{B}T$ is the pressure, which can be expressed using the Ideal Gas Law, and $\gamma = 5/3$ is the adiabatic index which corresponds to a gas where the particles have three translational degrees of freedom, meaning we think of them as just zooming about without spinning.  

$\textbf{T}$ is the rank-2 tensor which describes the fluxes of these variables. You can think of a "tensor" as a way of storing information in multiple dimensions. If this sounds just like a matrix, or a vector, that's because those data structures are just lower dimensional forms (rank-2, and rank-1, respectively) of the more general tensor! The information that $\textbf{T}$ stores are terms that describe how the Ideal MHD quantities are transported through space. 

&nbsp;&nbsp;&nbsp;&nbsp;We're not string theorists here, so for us space has three-dimensions. Consequently, $\textbf{T}$, has three terms as well, each one of which is a vector that describes how the physical quantities are transported in a given direction.

$$
\textbf{T} = \rowvec{\vec{F} \\ \vec{G} \\ \vec{H}}
$$

&nbsp;&nbsp;&nbsp;&nbsp;Lastly, $\nabla$ is the gradient. The gradient is a special kind of vector that points in the direction of a function's maximum possible change. If you are familiar with vector calculus, then you are familiar with $\nabla$. There are all kinds of mathematical tricks that we can play with $\nabla$, and these tricks are the sleight of hand that makes up the shell game which is classical physics.  