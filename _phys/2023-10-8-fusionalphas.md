---
layout: post
title: Fusion Alphas and Relativistic Electrons
---
First-generation fusion reactors will almost certainly be based on the Deuterium-Tritium (DT) reaction. Why is this? Fundamentally, the reasons have to do with what's the easiest to engineer, but that is not the subject of this post. This post is about working through a calculation using the Lienard-Wiechert potentials to demonstrate the acceleration of electrons to relativistic speeds in a DT fusion reactor. Before we get to the main content, let's first describe the DT reaction[^1],

\\[
_{1}^{2}H^{+} + \, _{1}^{3}H^{+} \longrightarrow \, _{2}^{4}He^{++} + \, _{0}^{1}n + 17.6 MeV 
\\]

$\hspace{1cm}$ The above nuclear reaction may look imposing, but the bit we care about is the very last term, representing the energy that is liberated when a Deuterium ion, \(D = \, _{1}^{2}H^{+}\), overcomes the Coulomb barrier and fuses with a Tritium ion, \(T = \, _{1}^{3}H^{+}\), producing an alpha particle, \(\alpha = \, _{2}^{4}He^{++}\) and a fast neutron, \(\, _{0}^{1}n\). Together, these reaction products have a combined energy of 17.6 million electronvolts. 

$\hspace{1cm}$ Unless you are a fusion scientist, you might feel overwhelmed by the above paragraph and the concepts and notation it introduces. \(\textit{Coulomb barrier}\)? \(\textit{Electronvolt}\)? If you are a fusion scientist, then you might be beginning to wonder why you're reading a basic primer on nuclear fusion that seems aimed at the educated public, in a post that seeks to describe a relativistic aspect of alpha heating. Please, forgive me for trying to have it both ways. I merely want to be approachable to a wide audience. It is my intention to write posts explaining the Coulomb barrier, the concept of an electronvolt, the engineering that goes into a fusion reactor, and more, so that there will be a 'trail of breadcrumbs' for someone to follow who wishes to learn about nuclear fusion.

$\hspace{1cm}$ However, what I want to do now is describe what is known as the \(\textit{Lienard-Wiechert}\) fields, analytical solutions to the electromagnetic fields radiated by an accelerating charge[^2]. 

$$
\begin{aligned}
    \vec{E} &= \frac{q}{4\pi\epsilon_{0}r^{2}}\frac{1}{(1 - \frac{v}{c}\cos(\theta))^{3}}\left(\hat{\textbf{e}}_{r} - \frac{v}{c}\hat{\textbf{e}}_{z}\right)(1 - \frac{v^{2}}{c^{2}}) + \frac{q\sin(\theta)}{4\pi\epsilon_{0}c^{2}r}\frac{\dot{u}}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{2}}\hat{\textbf{e}}_{\theta} \\
    \vec{B} &= \frac{q}{4\pi\epsilon_{0}c^{2}r^{2}}\frac{v\sin(\theta)}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{3}}\left(1 - \frac{v^{2}}{c^{2}}\right)\hat{\textbf{e}}_{\phi} + \frac{q\sin(\theta)}{4\pi\epsilon_{0}c^{3}r}\frac{\dot{u}}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{2}}\hat{\textbf{e}}_{\phi}
\end{aligned}
$$

These fields have two components, the velocity field, and the acceleration field
It can be shown by a straightforward conservation of momentum and energy analysis, the bread and butter of a physicist, that the \(\alpha\)-particle is born with 3.5 MeV of kinetic energy, and the fast neutron is created with 14.1 MeV of kinetic energy.

$\hspace{1cm}$ A fusion plasma is a soup of charged particles. The neutron, having no electric charge, travelling extremely fast, and therefore possessing a vanishingly-small chance of interacting with the fully-ionized medium in any way, leaves the domain almost immediately. Exiting stage right as it does, this player is nonetheless critical to the operation of an economic fusion reactor since it carries away most of the energy to be caught in a wall of molten Lithium. The \(\alpha\) has no such luck. In the turbulent environment of the magnetically-confined fusion plasma, this charged particle is unable to escape the magnetic confines. 

$\hspace{1cm}$ Instead, with its large amount of random kinetic energy, the \(\alpha\) heats the plasma. Given our knowledge of how much energy it has to begin with, energy that will quickly begin radiating away to interact with the electrons in its shielding cloud, we can determine how fast the \(\alpha\) is initially going. 

$$
\begin{aligned}
    KE_{\alpha} &= \frac{1}{2}m_{\alpha}v_{\alpha}^{2} \\
    m_{\alpha} &= 3.727 GeV / c^{2} \\
    \therefore v_{\alpha} = 0.0433c
\end{aligned}
$$



[^1]: Freidberg, Jeffrey P. Plasma Physics and Fusion Energy. Cambridge University Press, 2007. 
[^2]: Cooray, Vernon, et al. Lightning Electromagnetics. Volume 1, Return Stroke Modelling and Electromagnetic Radiation. The Institution of Engineering and Technology, 2022. 