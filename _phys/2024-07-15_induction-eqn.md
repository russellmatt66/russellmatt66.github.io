---
layout: post
title: The MHD Induction Equation
date: 2024-07-15
collection: phys
---
#### A Notational Prologue 
I have previously written about [index notation](../math/2024-07-15_indexnotation). In my estimation, it is the single most useful tool that one can have in their arsenal if they wish to do vector calculus seriously. If you know index notation then feel free to continue, but if you do not, then you can follow the link above and refer to the information where it leads as you continue reading. Index notation is an immensely useful shorthand for writing vector equations that allows you to [derive vector identities](../math/2024-07-15_indexnotation#deriving-vector-identities) such as 

$$
\begin{equation}
\curl \curl \vec{B} = \nabla (\div \vec{B}) - \laplacian \vec{B}
\end{equation}
$$

which would otherwise require rote memorization, or a tedious amount of algebra to prove, much less derive. The [NRL Plasma Formulary](https://library.psfc.mit.edu/catalog/online_pubs/NRL_FORMULARY_13.pdf) is a brilliant resource which catalogues these identities, including the one above. 

#### Deriving The MHD Induction Equation
When there is a plasma with a finite resistivity that we wish to analyze with MHD, we must use a flavor known as [Resistive MHD](./2024-07-15_mhd#resistive-mhd) to incorporate the impact of the non-ideal plasma properties. Written in [cgs units](./2024-07-9_maxwell#cgs-units), the relevant parts look like the following,

$$
\begin{align}
\pdv{\rho}{}{t} + \div \rho\vec{u} &= 0 \tag{1} \label{eqn:masscont} \\
\rho \left(\pdv{\vec{u}}{}{t} + \vec{u}\cdot\nabla\vec{u}\right) &= \frac{\vec{j}\cross\vec{B}}{c} - \nabla p \tag{2} \label{eqn:momcont} \\
\dv{}{t}\left(\frac{p}{\rho^{5/3}}\right) &= 0 \tag{3} \label{eqn:eos} \\ 
\vec{E} + \frac{\vec{u} \cross \vec{B}}{c} &= \eta\vec{j} \tag{4} \label{eqn:gohmlaw} \\
\end{align}
$$

Together with (1) - (4), we also incorporate Faraday's Law, and Ampere's Law under the assumption of a steady electric field,

$$
\begin{align}
\curl \vec{E} &= -\frac{1}{c}\pdv{\vec{B}}{}{t} \tag{5} \label{eqn:flaw} \\
\curl \vec{B} &= \frac{4\pi}{c}\vec{j} \tag{6} \label{eqn:alaw}
\end{align}
$$

A frequent strategy when working with Maxwell's equation is to eliminate one of the fields by taking the curl of an equation, here, we do that on Eqn. (\ref{eqn:gohmlaw}), giving,

$$
\begin{equation}
\curl \vec{E} + \curl \left(\frac{\vec{u} \cross \vec{B}}{c}\right) = \eta \curl \vec{j}
\end{equation}
$$

note that, in the process of creating the above, we have assumed a plasma with a uniform resistivity, $\eta(\vec{x}, t) = \eta$. Next, we insert Faraday's Law, Eqn. (\ref{eqn:flaw}), and use Ampere's Law, Eqn. (\ref{eqn:alaw}), to obtain,

$$
\begin{align}
-\frac{1}{c}\pdv{\vec{B}}{}{t} + \curl \left(\frac{\vec{u} \cross \vec{B}}{c}\right) &= \eta \curl \vec{j} \\
\therefore \pdv{\vec{B}}{}{t} - \curl \left(\vec{u} \cross \vec{B}\right) &= - \frac{c^{2}\eta}{4\pi} \curl \curl \vec{B} \tag{7}
\end{align}
$$

Rather than proceed via appeal to the venerable [NRL Plasma Formulary](https://library.psfc.mit.edu/catalog/online_pubs/NRL_FORMULARY_13.pdf), we will decide instead to represent, and manipulate, the above using index notation, so that it first becomes, 

$$
\begin{align}
\partial_{t}B_{i} - \epsilon_{ijk}\partial_{j}\epsilon_{klm}u_{l}B_{m} &= -\bar{\eta} \epsilon_{ijk}\partial_{j}\epsilon_{klm}\partial_{l}B_{m} \\
\end{align}
$$

where $\bar{\eta} = \frac{c^{2}\eta}{4\pi}$. 

&nbsp;&nbsp;&nbsp;&nbsp; If the above expression is unclear to you, I highly recommend you review the relevant parts of [this post going over index notation](../math/2024-07-15_indexnotation) before continuing. Due to the wondrous nature of index notation, the $\epsilon$ being rendered here represent scalars, so we can freely slide them through the partial derivatives, allowing us to eventually write the expression in a simplified form after applying a well known relationship between the [Levi-Civita symbols](../math/2024-07-15_indexnotation#levi-civita), and the [Kronecker delta](../math/2024-07-15_indexnotation#kronecker-delta),

$$
\begin{align}
\partial_{t}B_{i} - \epsilon_{ijk}\epsilon_{klm}\partial_{j}u_{l}B_{m} &= -\bar{\eta} \epsilon_{ijk}\epsilon_{klm}\partial_{j}\partial_{l}B_{m} \\
\implies \partial_{t}B_{i} - \left[\delta_{il}\delta_{jm} - \delta_{jl}\delta_{jm}\right]\partial_{j}u_{l}B_{m} &= - \bar{\eta} \left[\delta_{il}\delta_{jm} - \delta_{jl}\delta_{jm}\right]\partial_{j}\partial_{l}B_{m}
\end{align}
$$