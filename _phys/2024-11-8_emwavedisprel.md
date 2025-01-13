---
layout: post
title: The Dispersion Relation for Plane Electromagnetic Waves
date: 2024-11-8
collection: phys
---
The dispersion relation is a function that determines the frequency of a wave, $\omega$, from its wavenumber, $\vec{k} = k_{x}\hat{x} + k_{y}\hat{y} + k_{z}\hat{z}$. In physics this is very important as information related to the propagation characteristics of the wave is contained within. For example, the group velocity, which is the speed at which the wave packet travels,

$$
v_{g} = \dv{\omega}{k}
$$

and the phase velocity, which is the rate at which the modulated signal changes, 

$$
v_{\phi} = \frac{\omega}{k}
$$

When a system exhibits a dispersion relation that has a $v_{\phi}$ which is dependent on $\vec{k}$ we say that it is *dispersive*.

&nbsp;&nbsp;&nbsp;&nbsp; Ordinarily, we derive dispersion relations starting from a wave equation. For example, in electromagnetism, we can take Faraday's Law, and Ampere's Law, and derive a wave equation for the magnetic field,

$$
\begin{align}
\curl \vec{E} &= - \pdv{\vec{B}}{}{t} \\
\curl \vec{B} &= \frac{1}{c^{2}}\pdv{\vec{E}}{}{t} \\
\rightarrow \curl \curl \vec{B} &= -\frac{1}{c^{2}}\pdv{\vec{B}}{2}{t} \\
\therefore -\laplacian \vec{B} &= \frac{1}{c^{2}}\pdv{\vec{B}}{2}{t} \\
\rightarrow \pdv{\vec{B}}{2}{t} &= c^{2} \laplacian \vec{B}
\end{align}
$$

It is important to note that in the above we have assumed the electromagnetic field varies smoothly in space and time, and that there are no currents which are present. Next, we would assume a form to $\vec{B}$, such as $\vec{B}(\vec{r}, t) \sim exp(\mathrm{i}(\vec{k}\cdot\vec{r} - \omega t))$, and insert this into the wave equation. In moments like this there is a "symbolic" correspondence that will emerge between ($\omega, \vec{k}$) and ($\pdv{}{}{t}, \nabla$),

$$
\mathrm{i}\omega \leftrightarrow \pdv{}{}{t} \\
-\mathrm{i}\vec{k} \leftrightarrow \nabla
$$

You might notice this is also the same pattern that emerges when [Fourier Transforming](../_math/2024-11-8_fouriertransform) derivatives. Consequently, by carrying this math through, and noticing that we can cancel the exponentials because they will never be equal to zero, we will arrive at the following dispersion relation,

$$
\omega^{2} = c^{2}k^{2}
$$

which has two solutions,

$$
\omega = \pm ck
$$

that describe two waves propagating, one to the left, and one to the right. Both travel at the speed of light in vacuum, and both are non-dispersive because their phase velocities are independent of $k$. \\

<!-- &nbsp;&nbsp;&nbsp;&nbsp; This is just the beginning of where you can go with dispersion relations. One of the coolest things I learned in graduate school for computational physics is how to derive PDEs *starting* from the Taylor Series for $\omega(\vec{k})$. It takes a little bit of legwork to do this, so if you're interested check out the posts where this is done!

[The Advection Equation](../_phys/2024-11-8_advdisprel) \\
[The Schrodinger Equation](../_phys/2024-11-8_sedisprel) \\
[The Korteweg de Vries Equation](../_phys/2024-11-8_kdvdisprel) -->
