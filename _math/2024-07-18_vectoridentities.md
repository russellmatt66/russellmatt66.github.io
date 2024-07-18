---
layout: post
title: Vector Calculus Identities
date: 2024-07-18
collection: math
---
&nbsp;&nbsp;&nbsp;&nbsp; This post uses [index notation](./2024-07-15_indexnotation), so please consult the linked post for context, if you feel it is necessary, or experience confusion. 

#### Irrotationality
An irrotational vector field is one with a vanishing curl,

$$
\begin{equation}
\curl \vec{A} = 0 \tag{1} \label{eqn:irroty}
\end{equation}
$$

Irrotational vector fields frequently appear in physical applications, e.g., potential flow, electrostatics, etc.. The reason is that they permit a simplification from needing to solve a linear system of coupled PDEs, to needing to solve only a single linear PDE because one can write $\vec{A} = -\grad \phi$ for a sufficiently smooth scalar function, $\phi$. Inserting this into the above, we would have,

$$
\begin{equation}
\curl \grad \phi = 0 \tag{2} \label{eqn:curlgradphi}
\end{equation}
$$

which we can take the determinant of in order to verify that Eqn. (\ref{eqn:curlgradphi}) is a valid mathematical statement,

$$
\begin{align}
\curl \grad \phi &= 
\begin{vmatrix}
\hat{x} & \hat{y} & \hat{z} \\
\partial_{x} & \partial_{y} & \partial_{z} \\
\partial_{x}\phi & \partial_{y}\phi & \partial_{z}\phi
\end{vmatrix} \\
&= \hat{x}\left(\partial_{y}\partial_{z}\phi - \partial_{z}\partial_{y}\phi\right) - \hat{y}\left(\partial_{x}\partial_{z}\phi - \partial_{z}\partial_{x}\phi\right) + \hat{z}\left(\partial_{x}\partial_{y}\phi - \partial_{y}\partial_{x}\phi\right) \\
&= 0 
\end{align}
$$

Where we have used the fact that for a sufficiently smooth $\phi$ $\partial_{i}\partial_{j} = \partial_{j}\partial_{i}$. This was not so demanding, but we can also do the same with index notation, and avoid having to take a determinant,

$$
\begin{align}
\curl \grad \phi = \epsilon_{ijk}\partial_{j}\partial_{k}\phi 
\end{align}
$$