---
layout: post
title: The Eigenvalues of Ideal Magnetohydrodynamics
date: 2024-08-22
collection: phys
---
### Recap
&nbsp;&nbsp;&nbsp;&nbsp; Previously, I have written about [the Flux Jacobians of Ideal MHD](./2024-08-15_fluxjacobian), which are an idea that is central to this post. Recapping briefly, Ideal MHD is the simplest, meaningful, fluid description of a plasma. Its main application is in the field of fusion energy, where it is used to describe the equilibrium of magnetic configurations. In the absence of external sources of mass, momentum, energy, and magnetic field, we can write the system in the following form,

$$
\label{eq:imhd_system_fj}
\pdv{\vec{Q}}{}{t} + \mathbf{A}\pdv{\vec{Q}}{}{x} + \mathbf{B}\pdv{\vec{Q}}{}{y} + \mathbf{C}\pdv{\vec{Q}}{}{z} = 0
$$

where $\vec{Q}$ are the [Ideal MHD variables](./2024-08-15_fluxjacobian#eq:imhdvars), and $\mathbf{A}, \mathbf{B}$, and $\mathbf{C}$, are the [Flux Jacobians](./2024-08-15_fluxjacobian#the-flux-jacobians). These mathematical objects express how the fluxes vary with respect to the fluid variables, and they contain important information about the properties of the system related to the type of the equations, their characteristics, and stability.

### Eigenvalues and Eigenvectors
&nbsp;&nbsp;&nbsp;&nbsp; If you study physics, or engineering, to a serious degree, then you will eventually run into the concepts of an "eigenvalue", and an "eigenvector". If you are already familiar, and comfortable, with what these are, and just want to get to the meat of this post [where the eigenvalues of the Ideal MHD Flux Jacobians are calculated](#the-ideal-mhd-eigenvalues), then please follow this link, and feel free to skip this section as it will be a brief introduction to these concepts. 

&nbsp;&nbsp;&nbsp;&nbsp; These, somewhat intimidating, names bely deceptively simple ideas, but which are also devilishly rich with detail to understand the deeper you go, and understanding which begins by talking about the idea of a *system*. Intuitively, you can understand a system as something where input goes in, something happens to it, and output comes out. For example, the American education system takes in children around the age of five, obliges them to sit down and learn for seven hours a day, five days a week, asks them do homework for another three starting when they reach high school, and keeps them in this cycle for thirteen years. What comes out of this system is hopefully an educated, well-socialized populace of workers who can think critically, make informed decisions, and perform tasks which add value to society in exchange for a cut of this value in the form of monetary compensation which allows them to meet their basic needs, and do things which they find fulfilling.     

&nbsp;&nbsp;&nbsp;&nbsp; The difference in physics, and engineering, is that the systems which we study in these fields are rigorously defined mathematically, rather than just described qualitatively, meaning we have a clear idea of what the inputs, outputs, and transformation are. A **matrix** is the primary form in which a system is defined, and it is just a collection of numbers, (in the form of a rank-2 tensor, to be specific), that has two dimensions to its structure. For example, 

$$
\mathbf{R} = \begin{bmatrix}
2 & 1 & 3 \\
1 & 3 & -2 \\
0 & 5 & -1
\end{bmatrix}
$$

is the matrix which describes the transformation from one coordinate system, $(x_{1}, y_{1}, z_{1})$ to another $(x_{2}, y_{2}, z_{2})$, that is defined by the following system of equations,

$$
\begin{align}
x_{2} &= 2x_{1} + y_{1} + 3z_{1} \\
y_{2} &= x_{1} + 3y_{1} - 2z_{1} \\
z_{2} &= 5y_{1} - z_{1}
\end{align}
$$

What this means, in practice, is if we had a vector, which is a one-dimensional way of storing information, that we were looking at in the first coordinate system, where it was described by the numbers,

$$
\vec{u}_{in1} = \begin{bmatrix}
4 \\
-3 \\
1
\end{bmatrix}
$$

then, if we were to look at it in the second coordinate system, it would be described by a new triplet of numbers,

$$
\vec{u}_{in2} = \mathbf{R}\vec{u}_{in1} = \begin{bmatrix}
4*2 - 3*1 + 1*3 \\
4*1 - 3*3 + 1*(-2) \\
4*0 - 3*5 - 1*1
\end{bmatrix}
= \begin{bmatrix}
8 \\
-7 \\
-16
\end{bmatrix}
$$

All vectors can be boiled down to a magnitude, and a direction. The *magnitude* of a vector is a measure of how long it is, and its direction gives a sense for its orientation. If we compare the magnitude of these two vectors, and their orientations, we will notice they're different when viewed in these two coordinate systems, even though we're talking about the **same** underlying mathematical object. *Great*, you may be thinking, *when do we get to what eigenvectors, and eigenvalues, are?* 

&nbsp;&nbsp;&nbsp;&nbsp; For a given system, there is a set of vectors which *do not rotate* when the system is applied to it. Their lengths will change, but their orientations will not. These vectors are termed **eigenvectors**, and the factors by which their lengths change, are the **eigenvalues**. In principle, the eigenvalues, $\\{\lambda\\}$, of a system, $\mathbf{A}$, can be determined by solving for the roots of a *characteristic polynomial*, which is defined by the equation,

$$
det(\mathbf{A} - \lambda\mathbf{I}) = 0
$$

The *determinant* is a function, $det()$, which takes in an $N\times N$ matrix, and returns a scalar. The determinant of a $2\times 2$ matrix is defined in the following manner,

$$
det(\mathbf{A}_{2by2}) = \begin{vmatrix}
a & b \\
c & d 
\end{vmatrix} = ad - bc
$$

The determinant of a $3\times 3$ matrix can be expressed as a sum of determinants of $2\times 2$ sub-matrices,

$$
det(\mathbf{A}_{3by3}) = \begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix} = 
a \begin{vmatrix}
e & f \\
h & i
\end{vmatrix}
- b \begin{vmatrix}
d & f \\
g & i
\end{vmatrix}
+ c \begin{vmatrix}
d & e \\
g & h 
\end{vmatrix}
$$

The determinant of a $4\times 4$ matrix can be expressed as a sum of determinants of $3\times 3$ sub-matrices, 

$$
det(\mathbf{A}_{4by4}) = \begin{vmatrix}
a & b & c & d \\
e & f & g & h \\
i & j & k & l \\
m & n & o & p
\end{vmatrix}
= a \begin{vmatrix}
f & g & h \\
j & k & l \\
n & o & p
\end{vmatrix}
- b \begin{vmatrix}
e & g & h \\
i & k & l \\
m & o & p
\end{vmatrix}
+ c \begin{vmatrix}
e & f & h \\
i & j & l \\
m & n & p
\end{vmatrix}
- d \begin{vmatrix}
e & f & g \\
i & j & k \\
m & n & o
\end{vmatrix}
$$

and so on, and so forth (larger dimensions not rendered here for obvious reasons). It is apparent that computing the determinant is a very expensive, and time-consuming operation. In practice, instead of doing this, there are various *matrix decompositions*[^1] which can express the given matrix as a product of several other matrices, in one of which the eigenvalues are explicitly stored, that are employed. High-performance libraries exist to do these computations on CPU, and GPU, which can be useful for implementing an adaptive timestep in a simulation. 

### The Ideal MHD Eigenvalues
&nbsp;&nbsp;&nbsp;&nbsp; There are three matrices which are naturally relevant to Ideal Magnetohydrodynamics, namely, the Flux Jacobians, $\mathbf{A}, \mathbf{B}$, and $\mathbf{C}$. These matrices describe the rate at which the fluxes in the x-,y-, and z-directions, respectively, change with respect to a change in the fluid variables, $\vec{Q}$. From dimensional analysis of Equation (\ref{eq:imhd_system_fj}), you can see that the units of the Flux Jacobians must be that of velocity, distance over time, and so the eigenvalues of these matrices have a special interpretation as *characteristic speeds*.  

&nbsp;&nbsp;&nbsp;&nbsp; The stability of a numerical code that solves the Ideal MHD system [depends on the value of these characteristic speeds](./2024-08-15_fluxjacobian#motivation), in comparison to the characteristic speed of information propagation on the simulation mesh, namely, 

$$
\begin{align}
\frac{\Delta t}{\Delta x}\abs{\lambda_{A,max}} + \frac{\Delta t}{\Delta y}\abs{\lambda_{B,max}} + \frac{\Delta t}{\Delta z}\abs{\lambda_{C,max}} \leq 1
\end{align}
$$

&nbsp;&nbsp;&nbsp;&nbsp; The **equation type** of a system of PDEs is also defined by the eigenvalues of these matrices. There are three basic kinds of PDEs, *hyperbolic*, *parabolic*, and *elliptic*. Hyperbolic equations describe wave-like behavior, parabolic equations describe diffusion-like behavior, and elliptic equations describe steady-state behavior, or eigenvalue problems, where the challenge is determining a spectrum of numbers, instead of evolving the state of a dynamical system. What type a system of PDEs is has important implications for the kinds of numerical algorithms which are best suited to solving it. Furthermore, some PDEs can be of mixed-type, perhaps being hyperbolic in one part of the domain, and parabolic in another, due to nonuniformity in the coefficients. Fortunately, Ideal MHD does not have this problem, because the only coefficients in the system are two constants, $\gamma$, and $\mu_{0}$. As we will see, it is hyperbolic in the entire domain, which is based on its eigenvalues being real numbers with zero imaginary part. 

&nbsp;&nbsp;&nbsp;&nbsp; While there are numerical routines implemented in C, and C++, which compute the eigenvalues of a matrix, there is little recourse to symbolically computing them (except the expensive Mathematica software, of course). However, by looking at the previous examples of how to compute a determinant by hand, we can notice that the determinant of the sub-matrices are multiplied by a leading factor, which is a value in the primary matrix. If this value is 0, then the associated sub-matrix determinant does not need to be computed, which means that if we are clever, and the primary matrix is full of zeroes (like the Ideal MHD Flux Jacobians are), then things can be greatly simplified!  

<!-- &nbsp;&nbsp;&nbsp;&nbsp; Long ago, in Fortran77, high-performance libraries were written to implement numerical linear algebra routines that performed this kind of task, among others. Fortran77, or F77 as it is lovingly-referred to, is also the number of expletives one might utter when dealing with a language full of such idiosyncracies as requiring there to be a fixed number of leading whitespaces before every line (if you thought *Python* whitespace was bad). As the language matured, these routines were ported to Fortran90, a much more enjoyable version of Fortran, C, and C++. Now, bindings exist in many languages to access these high-performance libraries, as well as ports of them which run on a GPU.     -->

<!-- References -->
[^1]: Trefethen and Bau, *Numerical Linear Algebra*, SIAM, 1997
