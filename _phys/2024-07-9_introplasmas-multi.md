---
layout: post
title: Multiscale Phenomena in Plasmas
date: 2024-07-09
collection: phys
---
&nbsp;&nbsp;&nbsp;&nbsp; Their multiscale nature is a trademark of plasmas. There is never just one thing happening in a plasma. For example, in a fusion reactor plasma, at macroscopic length scales, say, $L \sim 1 \left[\text{m}\right]$, the evolution of the magnetic configuration is described by a [magnetohydrodynamic](./2024-07-15_mhd) equilibrium. Zoom in with a microscope, and you'll find a much different environment full of turbulent eddies, current sheets, and reconnecting magnetic topologies. Zoom in even further, and you would find individual particles moving in electromagnetic fields, and radiating their own away. The limited nature of [plasma diagnostics](../fusion/2024-07-18_plasmadiagnostics) limits what we can do in practice, however, especially when we are talking about the hot and energetic environment of a fusion reactor plasma.      

#### The Debye Length
&nbsp;&nbsp;&nbsp;&nbsp; Before we proceed any further, we have to start by talking about the fundamental spatial scale in a plasma, namely, the *Debye Length*. A plasma is a gas of charged particles. When charged particles move freely, they radiate electromagnetic fields. The form of these fields actually has an analytical solution, known as the [*Lienard-Wiechert fields*](./2024-07-18_lienardwiechert),

$$
\begin{equation}
\text{Lienard-Wiechert goes here}
\end{equation}
$$

Fundamentally, at the lowest level of a plasma, the electromagnetic field at any point can be said to be a superposition of all the Lienard-Wiechert (LW) fields of all the plasma particles. However, continuing in this vein would be unproductive, not just because of the formidable appearance of the LW fields, but also because of the classic statistical mechanics problem of very large numbers that would render this system intractable. [Simulating it](../gpu/2024-07-18_lwsim) is also impossible in practice.  

#### Plasma Frequency


#### Cyclotron Frequency
In the presence of a magnetic field, the particles in a plasma will find themselves "tied" to the field lines, and begin gyrating at an angular rate,

$$
\begin{equation}
\omega_{cs} = \frac{\abs{q_{s}}B_{0}}{m_{s}}
\end{equation}
$$

#### Collision Frequencies

#### Mean Free Path

#### Hybrid Timescales

#### MHD Timescales

<!-- References -->
