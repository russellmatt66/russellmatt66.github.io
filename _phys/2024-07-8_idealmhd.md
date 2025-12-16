---
layout: post
title: Ideal MHD
date: 2024-07-08
collection: physics
---
### The Conservative Form
&nbsp;&nbsp;&nbsp;&nbsp;Ideal Magnetohydrodynamics (MHD) is the simplest model for describing the behavior of a fluid plasma. Due to this simplicity there are some restrictions on when we, strictly-speaking, can apply it. Funnily enough, in practice Ideal MHD applies more than it should. The reason why plasma scientists care so much about Ideal MHD is that it describes the equilibrium of magnetic fusion reactors. Although it is the simplest fluid model of a plasma, it is still quite complicated. In the absence of source terms, this is what it looks like,

$$
\pdv{\vec{Q}}{}{t} + \div \textbf{T} = 0
$$ 

If source terms were present, then they would show up on the right-hand side (RHS) of this expression, instead of 0. Without source terms, the above is what's known as a $\textit{homogeneous}$ partial differential equation (PDE), i.e., one that is zero everywhere. When a system of PDEs is written in the above fashion, it is referred to as being in "conservative form", as the above can be seen to be in the form of a conservation law. Homogeneous PDEs are by no means easy to solve, but $\textit{heterogeneous}$ PDEs, ones that are not zero everywhere, are even harder. PDEs are ubiquitous in science, and engineering, so the existence and uniqueness of solutions to them is a crucial matter. 

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

&nbsp;&nbsp;&nbsp;&nbsp; Lastly, $\nabla$ is the [gradient](../math/2024-07-16_gradients). The gradient is a special kind of vector that points in the direction of a function's maximum possible change. If you are familiar with vector calculus, then you are familiar with $\nabla$. There are all kinds of mathematical tricks that we can play with $\nabla$, and these tricks are the sleight of hand that makes up the shell game which is classical physics. People that like to memorize things study medicine, not physics, so the best way to play these tricks is to write them in [index notation](../math/2024-07-15_indexnotation) as this allows one to derive them just from a basic understanding of a [few mathematical tools](../math/2024-07-15_indexnotation/#deriving-vector-identities).  

#### Deriving Ideal MHD
&nbsp;&nbsp;&nbsp;&nbsp; All MHD models begin from a set of fluid equations, and all fluid equations begin by taking a set of moments of a kinetic equation, with a suitable means of closing this infinite process that involves relating higher-order variables together with lower-order ones, e.g., describing heat flow as the gradient of temperature. 

$$
\vec{q} = \kappa\nabla T
$$

&nbsp;&nbsp;&nbsp;&nbsp; The two most popular schemes for creating these fluid equations are the **5N-moment** model, and **13N-moment** model. The *N* in these names refers to the number of kinetic equations at the basis of this procedure, i.e., the number of species of particle your fluid is considered to be composed of, and the numeric literal refers to the number of fluid variables the model results in. [5N models](./2024-07-15_mhd#5n-moment) are the most basic kind, describing the flux of mass, momentum, and energy in the medium using variables for the density, velocity, and energy. [13N models](./2024-07-15_mhd#13n-moment) go a step further to model the flux of heat.        