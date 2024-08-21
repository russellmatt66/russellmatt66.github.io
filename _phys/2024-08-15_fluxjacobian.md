---
layout: post
title: The Flux Jacobians of the Ideal MHD System 
date: 2024-08-15
collection: phys
---
### A Brief Primer on Ideal MHD
Ideal Magnetohydrodynamics (MHD), is the simplest possible framework for modelling a plasma as a fluid. In conservative form, meaning there are no external sources of mass, momentum, energy, or magnetic field, it can be written as,

$$
\pdv{\vec{Q}}{}{t} + \div \mathbf{T} = 0
\label{eq:imhd_consform}
$$

stating that the evolution of the Ideal MHD variables, 

$$
\vec{Q} = \begin{bmatrix}
\rho \\ 
\rho u \\
\rho v \\
\rho w \\
B_{x} \\
B_{y} \\
B_{z} \\
e
\end{bmatrix}^{T}
$$

is balanced by the divergence of the respective fluxes, expressed by the rank-2 tensor, $\mathbf{T}$,

$$
\mathbf{T} = \begin{bmatrix}
\vec{F} \quad \vec{G} \quad \vec{H} 
\end{bmatrix}^{T}
$$

The components of $\mathbf{T}$ are the fluxes of Ideal MHD variables in the x-, y-, and z-directions, respectively. The x-directed fluxes, $\vec{F}$, are expressed as,

$$
\vec{F} = \begin{bmatrix}
\rho u \\ 
\rho u^{2} - \frac{B_{x}^{2}}{\mu_{0}} + p + \frac{B^{2}}{2\mu_{0}} \\
\rho uv - \frac{B_{y}B_{x}}{\mu_{0}} \\
\rho uw - \frac{B_{z}B_{x}}{\mu_{0}} \\
0 \\
vB_{x} - uB_{y} \\
wB_{x} - uB_{z} \\
(e + p + \frac{B^{2}}{2\mu_{0}})u - \frac{\vec{B} \cdot \vec{u}}{\mu_{0}}B_{x}
\end{bmatrix}
$$

the y-directed fluxes, $\vec{G}$, 

$$
\vec{G} = \begin{bmatrix}
\rho v \\ 
\rho uv - \frac{B_{y}B_{x}}{\mu_{0}} \\
\rho v^{2} - \frac{B_{y}^{2}}{\mu_{0}} + p + \frac{B^{2}}{2\mu_{0}} \\
\rho vw - \frac{B_{y}B_{z}}{\mu_{0}} \\
uB_{y} - vB_{x} \\
0 \\
wB_{y} - vB_{z} \\
(e + p + \frac{B^{2}}{2\mu_{0}})v - \frac{\vec{B} \cdot \vec{u}}{\mu_{0}}B_{y}
\end{bmatrix}
$$

and the z-directed fluxes, $\vec{H}$,

$$
\vec{H} = \begin{bmatrix}
\rho w \\ 
\rho uw - \frac{B_{x}B_{z}}{\mu_{0}} \\
\rho vw - \frac{B_{y}B_{z}}{\mu_{0}} \\
\rho w^{2} - \frac{B_{z}^{2}}{\mu_{0}} + p + \frac{B^{2}}{2\mu_{0}} \\
uB_{z} - wB_{x} \\
vB_{z} - wB_{y} \\
0 \\
(e + p + \frac{B^{2}}{2\mu_{0}})w - \frac{\vec{B} \cdot \vec{u}}{\mu_{0}}B_{z}
\end{bmatrix}
$$

Finally, the internal energy, $e$, of the plasma is given by,

$$
e = \frac{p}{\gamma - 1} + \frac{B^{2}}{2\mu_{0}} + \frac{\rho \norm{u}^{2}}{2}
$$

where $p = nk_{B}T$ is the plasma pressure, and $\gamma = \frac{5}{3}$ is the adiabatic constant for a gas with 3 degrees of freedom.  

### The Flux Jacobians
The Ideal MHD model in conservative form, Equation (\ref{eq:imhd_consform}), can  be expanded,

$$
\label{eq:imhd_expanded}
\pdv{\vec{Q}}{}{t} + \pdv{\vec{F}}{}{x} + \pdv{\vec{G}}{}{y} + \pdv{\vec{H}}{}{z} = 0
$$

Physicists frequently like to wave their hands, and perform such mathematical chicanery as saying things like 

$$
\dv{y}{x}dx = dy
$$

which frustrates mathematicians. Regardless, we can play that kind of trick here, to Equation (\ref{eq:imhd_expanded}), and expand it further,

$$
\begin{align}
(\ref{eq:imhd_expanded}) \rightarrow \pdv{\vec{Q}}{}{t} + \pdv{\vec{F}}{}{\vec{Q}}\pdv{\vec{Q}}{}{x} + \pdv{\vec{G}}{}{\vec{Q}}\pdv{\vec{Q}}{}{y} + \pdv{\vec{H}}{}{\vec{Q}}\pdv{\vec{Q}}{}{z} &= 0 \\
\therefore \pdv{\vec{Q}}{}{t} + \mathbf{A}\pdv{\vec{Q}}{}{x} + \mathbf{B}\pdv{\vec{Q}}{}{y} + \mathbf{C}\pdv{\vec{Q}}{}{z} &= 0
\end{align}
$$

The rank-2 tensors, $\mathbf{A}, \mathbf{B}, \mathbf{C}$, are known as the $\textit{Flux Jacobians}$, and their components are defined in the following manner,

$$
\begin{align}
A_{ij} &= \pdv{F_{i}}{}{Q_{j}}\left.\right|_{Q_{k}} \\
B_{ij} &= \pdv{G_{i}}{}{Q_{j}}\left.\right|_{Q_{k}} \\
C_{ij} &= \pdv{H_{i}}{}{Q_{j}}\left.\right|_{Q_{k}} \\
\end{align}
$$

where the $\left.\right|_{Q\_{k}}$ notation indicates that the derivative is taken *while holding all other fluid variables constant*. 
This point is italicized, because it is crucially important for computing the flux jacobians, which is necessary to do in order to understand the properties, and stability, of the Ideal MHD system. 

To illustrate, consider the $A_{11}$ term,

$$
A_{11} = \pdv{\rho u}{}{\rho}\left.\right|_{Q_{k}}
$$

On the surface, this looks like it should evaluate to $A_{11} = u$, however, because $\rho u$ itself is one of the fluid variables, which is being held constant in this case since it is not the variable that is being differentiated with respect to, $A_{11} = 0$ is the *actual* correct answer.There are eight flux terms, eight variables, and three flux jacobians, so in total there are one-hundred, and ninety-two, derivatives which must be carefully taken in this manner in order to fully compute them. 

### Motivation
&nbsp;&nbsp;&nbsp;&nbsp; Besides curiosity, the mathematical exercise, or to better understand the properties of the Ideal MHD equations, one of the primary reasons to calculate the flux jacobians is to understand the stability of a numerical simulation. All information is transmitted via modes, e.g., the sound waves that we hear, the light waves that we see, the variations in density that we smell, the pressure waves that we feel, etc.. In fluid dynamics, and more broadly in magnetohydrodynamics, we make various assumptions, and approximations, about the properties of a system in order to derive a set of governing equations. These governing equations capture various aspects of the system, and discard others. What information is transmitted, and how, is determined by the *fluid characteristics*, i.e., the different modes that the system supports, which are encoded by the flux jacobians, namely they are the eigenvalues. 

&nbsp;&nbsp;&nbsp;&nbsp; To visualize this, fluid dynamicists use *characteristic curves*, which are essentially graphs with $t$ as the ordinate (on the "y-axis"), and $x$ as the abscissa (on the "x-axis"). This kind of graph shows where in the domain information from a given mode, at a certain event, will have propagated to by a given time, also known as the *domain of influence*, as well as where in the domain the information of a given mode will have come from which influences the state of a given event at a given time, known as the *domain of dependence*. These characteristics have a finite, fixed, velocity so their curves are straight lines with the slope equal to the inverse of the characteristic's velocity, and which sweep out two cones when revolved 360 degrees around the time-axis, at a fixed event. The volume of these cones, one forwards, and one backwards, are the aforementioned domains.        

&nbsp;&nbsp;&nbsp;&nbsp; When we discretize the governing equations of a fluid system, on a mesh, in order to either solve them either explicitly (marching the state of the variables forward in time according to some method), or implicitly (inverting a matrix at each timestep in order to update the state of the variables), we introduce a synthetic characteristic speed to the solution, which is based on our choice of timestep, $\Delta t$, and the spacing of the mesh, $\Delta x$. Just like any characteristic, this numerical construct sweeps out a zone of dependence, and a zone of influence. In order for our simulation to remain stable, this numerical volume MUST contain all the information of the physical volume. In other words, the slope of the numerical characteristic, $\frac{\Delta t}{\Delta x}$, must be smaller than the slope associated with the fastest physical characteristic. Mathematically, in 1D,    

$$
\frac{\Delta t}{\Delta x} 
$$