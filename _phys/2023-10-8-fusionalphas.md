---
layout: post
title: Deuterium-Tritium Fusion Alphas and Relativistic Electrons
collection: phys
---
$\hspace{1cm}$ This post is about working through a calculation using the Lienard-Wiechert potentials to demonstrate the acceleration of electrons to relativistic speeds in a Deuterium-Tritium (DT) fusion reactor. Before we get to the main content, let's first describe the DT reaction[^1],

$$
_{1}^{2}H^{+} + \, _{1}^{3}H^{+} \longrightarrow \, _{2}^{4}He^{++} + \, _{0}^{1}n + 17.6 MeV 
$$

$\hspace{1cm}$ The above nuclear reaction may look imposing, but the bit we care about is the very last term, representing the energy that is liberated when a Deuterium ion, $D = \, _{1}^{2}H^{+}$, overcomes the Coulomb barrier and fuses with a Tritium ion, $T = \, _{1}^{3}H^{+}$, producing an alpha particle, $\alpha = \, _{2}^{4}He^{++}$ and a fast neutron, $\, _{0}^{1}n$. Together, these reaction products have a combined energy of 17.6 million electronvolts. Assuming the momentum and energy of the reactants is negligible, how does this energy get divvied up between the two?

$\hspace{1cm}$ By conservation of momentum, and energy, we can write the following from the perspective of the center-of-mass (COM) frame for the two particles in the instant after the reaction occurs,

$$
\begin{aligned}
KE &= \frac{1}{2}m_{\alpha}v_{\alpha}^{2} + \frac{1}{2}m_{n}v_{n}^{2} = E = 17.6 MeV \\
p &= m_{n}v_{n} + m_{\alpha}v_{\alpha} = 0
\end{aligned}
$$

The above (fairly simple) nonlinear system of equations can be solved for to obtain exact expressions for the partitioning of energy amongst the end-products,

$$
\begin{aligned}
p = m_{n}v_{n} + m_{\alpha}v_{\alpha} &= 0 \\
\implies v_{n} &= -\frac{m_{\alpha}}{m_{n}}v_{\alpha} \\
\therefore \frac{1}{2}m_{\alpha}v_{\alpha}^{2}(1 + \frac{m_{\alpha}}{m_{n}}) &= E \\
\implies \frac{1}{2}m_{\alpha}v_{\alpha}^{2} &= E \left(\frac{m_{n}}{m_{n} + m_{\alpha}}\right) \\
\therefore \frac{1}{2}m_{n}v_{n}^{2} &= E \left(\frac{m_{\alpha}}{m_{\alpha} + m_{n}}\right)
\end{aligned}
$$

<!-- $\hspace{1cm}$ Unless you are a fusion scientist, you might feel overwhelmed by the above paragraph and the concepts and notation it introduces. $\textit{Coulomb barrier}$? $\textit{Electronvolt}$? If you are a fusion scientist, then you might be beginning to wonder why you're reading a basic primer on nuclear fusion that seems aimed at the educated public, in a post that seeks to describe a relativistic aspect of alpha heating. Please, forgive me for trying to have it both ways. I merely want to be approachable to a wide audience. It is my intention to write posts explaining the Coulomb barrier, the concept of an electronvolt, the engineering that goes into a fusion reactor, and more, so that there will be a 'trail of breadcrumbs' for someone to follow who wishes to learn about nuclear fusion. -->

<!-- $\hspace{1cm}$ However, what I want to do now is describe what is known as the $\textit{Lienard-Wiechert}$ fields, analytical solutions to the electromagnetic fields radiated by an accelerating charge[^2]. 

$$
\begin{aligned}
    \vec{E} &= \frac{q}{4\pi\epsilon_{0}r^{2}}\frac{1}{(1 - \frac{v}{c}\cos(\theta))^{3}}\left(\hat{\textbf{e}}_{r} - \frac{v}{c}\hat{\textbf{e}}_{z}\right)(1 - \frac{v^{2}}{c^{2}}) + \frac{q\sin(\theta)}{4\pi\epsilon_{0}c^{2}r}\frac{\dot{u}}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{2}}\hat{\textbf{e}}_{\theta} \\
    \vec{B} &= \frac{q}{4\pi\epsilon_{0}c^{2}r^{2}}\frac{v\sin(\theta)}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{3}}\left(1 - \frac{v^{2}}{c^{2}}\right)\hat{\textbf{e}}_{\phi} + \frac{q\sin(\theta)}{4\pi\epsilon_{0}c^{3}r}\frac{\dot{u}}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{2}}\hat{\textbf{e}}_{\phi}
\end{aligned}
$$ -->

<!-- These fields have two components, the velocity field, and the acceleration field
It can be shown by a straightforward conservation of momentum and energy analysis, the bread and butter of a physicist, that the \(\alpha\)-particle is born with 3.5 MeV of kinetic energy, and the fast neutron is created with 14.1 MeV of kinetic energy. -->

$\hspace{1cm}$ A fusion plasma is a soup of charged particles. The fast neutron borne in the DT reaction, having no electric charge, and travelling extremely fast, 

$$
\begin{aligned}
\frac{1}{2}m_{n}v_{n}^{2} &= 14.1 MeV \\
m_{n} &= 939.565 \, MeV / c^{2} \\ 
\therefore v_{n} &= 0.173c \implies \gamma_{n} = 1.015 
\end{aligned}
$$

therefore possesses a vanishingly-small chance of colliding with other particles in the fully-ionized medium. As a consequence of these facts, it leaves the domain almost immediately. 

$\hspace{1cm}$ Exiting stage right as it does, this player is nonetheless critical to the operation of an economic fusion reactor since it carries away most of the energy of the reaction, where it can be caught in a wall of molten metal, typically Lithium (Li), and potentially used to breed new Tritium in a DT reactor. The $\alpha$ has no such luck. In the turbulent environment of the magnetically-confined fusion plasma, this charged particle is unable to escape the magnetic confines. 

$\hspace{1cm}$ Instead, with its large amount of random kinetic energy, the $\alpha$ heats the plasma. Given our knowledge of how much energy it has to begin with, energy that will quickly begin radiating away to interact with the electrons in its shielding cloud, we can determine how fast the $\alpha$ is initially going. 

$$
\begin{aligned}
    KE_{\alpha} &= \frac{1}{2}m_{\alpha}v_{\alpha}^{2} = 3.5 MeV \\
    m_{\alpha} &= 3.727 \, GeV / c^{2} \\
    \therefore v_{\alpha} &= 0.0433c \implies \gamma_{\alpha} = 1.0009  
\end{aligned}
$$

The next step is to figure out what's happening to the electrons. 

<!-- Cylindrical coordinates is not the correct basis for this, need spherical coordinates, but more importantly, need to read Zangwill. -->
<!-- The electromagnetic fields radiated by a charged particle in motion are given by the $\textit{Lienard-Wiechert}$ fields[^2],

$$
\begin{aligned}
    \vec{E} &= \frac{q}{4\pi\epsilon_{0}r^{2}}\frac{1}{(1 - \frac{v}{c}\cos(\theta))^{3}}\left(\hat{\textbf{e}}_{r} - \frac{v}{c}\hat{\textbf{e}}_{z}\right)(1 - \frac{v^{2}}{c^{2}}) + \frac{q\sin(\theta)}{4\pi\epsilon_{0}c^{2}r}\frac{\dot{u}}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{2}}\hat{\textbf{e}}_{\theta} \\
    \vec{B} &= \frac{q}{4\pi\epsilon_{0}c^{2}r^{2}}\frac{v\sin(\theta)}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{3}}\left(1 - \frac{v^{2}}{c^{2}}\right)\hat{\textbf{e}}_{\phi} + \frac{q\sin(\theta)}{4\pi\epsilon_{0}c^{3}r}\frac{\dot{u}}{\left(1 - \frac{v}{c}\cos(\theta)\right)^{2}}\hat{\textbf{e}}_{\phi}
\end{aligned}
$$ 

However, before we can determine, to an exact degree, the magnitude of the electromagnetic fields that the $\alpha$ is radiating away, we have to also know the rate at which its velocity is changing, $\dot{u}$.     -->

[^1]: Freidberg, Jeffrey P. Plasma Physics and Fusion Energy. Cambridge University Press, 2007. 
<!-- [^2]: Cooray, Vernon, et al. Lightning Electromagnetics. Volume 1, Return Stroke Modelling and Electromagnetic Radiation. The Institution of Engineering and Technology, 2022.  -->