---
layout: post
title: High-Thrust Fusion Propulsion with Bennett Vortices
date: 2026-1-18
collection: phys
---
*Reading time ~ 5 min, Word Count ~ 250*

&nbsp;&nbsp;&nbsp;&nbsp; Propelling a fuselage with fusion energy is one of the most challenging engineering tasks that an intelligent society can be faced with. This is not just because of the enormous thermal, and mechanical stresses that must be confronted, but also because the operation of a jet engine powered by fusion reactions is "bass-ackwards" from how you'd want it if you'd like the engine to be effective for more than just in the depths of space. 

&nbsp;&nbsp;&nbsp;&nbsp; Consider the power of the exhaust jet,

$$
\begin{equation}
    P_{jet} = \frac{1}{2}\dot{m}u_{e}^{2} = \eta P_{fusion}
\end{equation}
$$

which assumes a steady flow of exhaust, and an efficiency factor, $\eta$, that describes how  much thermal fusion power gets turned into directed kinetic energy. The thrust,

$$
\begin{equation}
    T = \dot{m}u_{e}
\end{equation}
$$

then becomes,

$$
\begin{equation}
    T = \frac{2\eta P_{fusion}}{u_{e}}
\end{equation}
$$

which presents a fundamental problem. Namely, that the faster the fusion plasma exhaust is travelling, then the lower the thrust of the jet engine will be. 

&nbsp;&nbsp;&nbsp;&nbsp; For example, consider a 10 MW fusion plasma, $P_{fusion} = 10 \ [MW]$, with an exhaust velocity of $u_{e} = 10^{6} \ [m s^{-1}]$, and an efficiency of $\eta = 0.5$. This sounds like a very powerful plasma that would produce a lot of thrust, but you can readily see that the thrust level from this example will only be ~10 Newtons, which is about the weight of a human baby in the third trimester of a pregnancy. However, unlike a human baby who grows very fast, this value will remain steady for a long time as the specific impulse of the engine is very large,

$$
I_{sp} = \frac{u_{e}}{g} \sim  10^{5} [s] 
$$

Meaning, a fusion jet engine with high exhaust speeds would be very effective for a deep-space mission where its high efficiency and steady thrust would allow the acceleration of the craft to high speeds over long periods of time. However, for leaving the planet, or powering an atmospheric flight vehicle, this thrust just doesn't cut it. These applications demand low exhaust speeds. 

&nbsp;&nbsp;&nbsp;&nbsp; Getting a fusion plasma jet engine to have a low exhaust speed seems an impossible task. However, there is a way that can be found by studying a family of analytic Shear-Flow Stabilized Z-Pinch equilibria which are derived by exchanging the Bennett profile from the plasma number density to the plasma flow velocity, known as [Bennett Vortices](https://russellmatt66.github.io/phys/2025_12-16_bennettvortex). These vortices hinge on a smallness parameter,

$$
\begin{equation}
    C_{B,T}^{(n)} \simeq 10^{-22}\frac{n_{0}u_{z,0}^{2}r_{p}^{n}}{T_{p}}
\end{equation}
$$

to create strongly-degenerate flows where the edge speed is equal to $u_{z,0}$. Otherwise, an algebraic equation's roots determine the possible values for the flow constant. Setting this speed to unity, and considering a "squat" pinch where, 

$$
\begin{align}
    r_{p} = 10L = 1 \ [m]
\end{align}
$$

we see that, for any power of vortex, which is just the exponent of its power-law temperature,

$$
\begin{equation}
    T(r) = \frac{T_{p}}{r_{p}^{n}}r^{n}
\end{equation}
$$

there is a wide range of operating densities and temperatures available to this configuration,

$$
C_{B,T} \simeq 10^{-22}\frac{n_{0}}{T_{p}}
$$

Consider a DD fusion plasma operating at a temperature of 50 million degrees Kelvin, and with a plasma number density of $n_{0} = 10^{22} - 10^{24}$. The vortex parameter then falls into the range of,

$$
C_{B,T} \sim 10^{-5} - 10^{-7} \ [m]
$$

which is sufficiently small for the flow speed constant of a cubic, pure-flow ($\chi = 2$) vortex,

$$
\begin{equation}
    u_{z,0} = u_{edge} \frac{(r_{p} + C_{B,T})^{2}}{r_{p}^{2}}
\end{equation}
$$

to nearly be the edge flow speed. Then the thrust level of the hypothetical fusion plasma from before becomes,

$$
T_{bv} \simeq 10^{6} \ [N]
$$

and the thermal confinement time is, for an $n$-vortex, where again $n$ is just the exponent of a power-law temperature,

$$
\begin{align}
    \tau_{E}^{(n)} &= \frac{3}{2}\frac{p_{0}V_{p}}{\int_{A_{L}}\vec{q}\cdot d\vec{A_{L}}} \\
    &= \frac{3}{4}p_{0}\frac{r_{p}}{|-\kappa_{\perp}\dv{T}{r}|_{r=r_{p}}} \\
    &= \frac{3}{4n\kappa_{\perp}}\frac{p_{0}r_{p}^{2}}{T_{p}}
\end{align}
$$

This value can be calculated analytically using Spitzer coefficients and compared to the Alfven time, and other important timescales for a Shear-Flow Stabilized Z-Pinch, like the flow-through time. However, these calculations are involved, and dinner time is swiftly approaching in my local manifold of flat spacetime on the Earth's surface, so my own energy confinement must be looked to first :) 