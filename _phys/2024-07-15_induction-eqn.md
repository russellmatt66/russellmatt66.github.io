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
The existence of a finite resistivity in the bulk of a plasma results in the presence of bulk plasma currents. For context, when a plasma physicist says "bulk", they are talking about a plasma which is behaving as a fluid. When there is a plasma with a finite resistivity that we wish to analyze with MHD, we must use a flavor known as [Resistive MHD](./2024-07-15_mhd#resistive-mhd) to incorporate the impact. Written in [cgs units](./2024-07-9_maxwell#cgs-units), it looks like the following,

$$
\begin{align}
\pdv{\rho}{}{t} + \div \rho\vec{u} &= 0 \\

\end{align}
$$