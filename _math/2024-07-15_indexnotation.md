---
layout: post
title: Index Notation
date: 2024-07-15
collection: math
---
#### Introduction
&nbsp;&nbsp;&nbsp;&nbsp; You can go far in understanding plasmas on the back of Magnetohydrodynamics ([MHD](./2024-06-15_mhd)), and you can go far in MHD on the back of understanding vector calculus. However, the more vector calculus you do, the more you run into a fundamental issue with the discipline. When you're flinging nabla's ($\nabla$), your state variables, inner products, cross products, dyadic products, etc., together, you start having to do a lot of writing, a lot of memorizing of identities in order to manipulate them, and you start losing insight into the underlying equations under the mask of all the symbols. Einstein came up with a brilliant way of addressing all three of these problems by developing a shorthand notation for expressing these kinds of equations.      

#### Index and Einstein Notation
&nbsp;&nbsp;&nbsp;&nbsp; If you wanted to write an inner product, between two vectors, then you could do so in the following way,

$$
\begin{equation}
\vec{a} \cdot \vec{b} = \sum_{i} a_{i}b_{i}
\end{equation}
$$

While pioneering quantum theory through his explanation of the photoelectric effect, developing his field equations, and just otherwise dominating the field of physics, Einstein worked with inner products frequently. Eventually, he grew tired of writing $\sum$ over and over, and just dropped it, choosing instead to communicate its presence implicitly whenever there was a repeated index. For example, using *index notation*, you would write the inner product between vectors as, 

$$
\begin{equation}
\vec{a} \cdot \vec{b} = a_{i}b_{i}
\end{equation}
$$

&nbsp;&nbsp;&nbsp;&nbsp; Now, before continuing, it is necessary to draw a distinction between *index notation*, and *Einstein notation*. Strictly-speaking, Einstein notation is what Einstein used when working on general relativity, and it's what's used to teach the subject in universities, and textbooks, around the world. In relativity, we work with 4-vectors, and higher-order tensors, which are defined on spacetime instead of the 3-vectors, and dyads, that are encountered in nonrelativistic settings. Consequently, to keep all the math straight, and the two fields separate, Einstein notation uses greek letters, instead of the english alphabet, and additionally, uses whether a greek letter is a subscript or superscript to communicate the dimension along which a contraction is happening. For example, in Einstein notation, you would write an inner product between two 4-vectors, as,

$$
\begin{equation}
\vec{a} \cdot \vec{b} = a_{\mu}b^{\mu}
\end{equation}
$$

To keep the scope of this post appropriate, that is all I will say on relativity, and Einstein notation.

#### Levi-Civita
&nbsp;&nbsp;&nbsp;&nbsp; Index notation is a wonderful tool. Trying to do vector calculus without index notation is like trying to walk when you could be running. The great filter of mastering index notation is understanding the [**Levi-Civita**](https://en.wikipedia.org/wiki/Levi-Civita_symbol) tensor, $\epsilon_{ijk}$[^1]. The first time I saw this symbol in undergraduate classical dynamics, I was confused, and frustrated. *What the hell is this*, I thought in consternation, *bring back the ODEs*. It wasn't until becoming immersed in vector calculus in graduate school that I became enamored with its utility. 

&nbsp;&nbsp;&nbsp;&nbsp; I called it a tensor, and wrote it in it's rank-3 tensorial form above, but the Levi-Civita (LV) *symbol* can actually be defined for any number of dimensions, $D$. With a space complexity of $\mathcal{O}(3^{D})$ needed in order to write down all of its terms, trying to do so becomes very inefficient, very quickly. However, it is very easy to describe what the value of any single term of the LV symbol is based on the order of the indices. If the indices are *cyclic*, that is, from left to right they are ordered numerically in a modular fashion, then the value of is 1. If they are *anti-cyclic*, meaning they are are ordered numerically in a modular fashion from right to left, then the value is -1. Anything else, and the value is 0. These are very loose definitions for cyclicity, and anti-cyclicity, so they bear illustration. Furthermore, because the context in which the LV symbol is being used here is index notation, the rank-3 form will be used.

&nbsp;&nbsp;&nbsp;&nbsp; For indices $i$, $j$, $k$ $\in \\{ 1,2,3 \\}$, there are $3^3 = 27$ different permutations that can be chosen without replacement. For example, $ijk = 123$, being one of them. Reading this example from left to right, we can see that the indices are in numerical order, so this is an example of a cyclic permutation. Now, consider $ijk = 321$. Reading this example from left to right, we can see that the indices are in reverse numerical order, a.k.a, numerical order when read from right to left, so this is an example of an anti-cyclic permutation. There is another element to the loose definition that I gave, and this is that the reading occurs in a modular fashion. For example, if $ijk = 312$, then we consider this a cyclic permutation as starting from 1, we read left to right, wrapping around to the beginning once we reach the end of the tuple, and find that it is in numerical order. Hopefully, by applying the same logic, it is evident why $ijk = 213$ is an anti-cyclic permutation. Another way of capturing these notions is with the idea of *even* and *odd* permutations.

#### Kronecker Delta
&nbsp;&nbsp;&nbsp;&nbsp; By itself, the Levi-Civita symbol is a mathematical curiosity, what makes it so powerful to the practice of vector calculus is its connection to the *Kronecker Delta*. If you have studied math, physics, or engineering to an intermediate degree, then you have certainly encountered the concept of a delta function (or perhaps distribution). For example, in physics and engineering there is the [*Dirac delta*](2024-07-16_diracdelta), $\delta(\vec{x} - \vec{x}_{0})$, defined in the following manner,

$$
\delta(\vec{x} - \vec{x}_{0}) = \begin{cases}
    1 & \text{if } \vec{x} = \vec{x}_{0} \\
    0 & \text{else } 
\end{cases}
$$

Here, we are interested in the *Kronecker delta*, $\delta_{ij}$ (which you might recognize as just the rank-2 identity tensor shortly), defined in the following manner,

$$
\delta_{ij} = \begin{cases}
    1 & \text{if } i = j \\
    0 & \text{else }
\end{cases}
$$

which yields,

$$
\delta_{ij} = \begin{pmatrix}
    1 & 0 & 0 \\
    0 & 1 & 0 \\
    0 & 0 & 1 
\end{pmatrix}
$$

#### The Vector (Cross) Product
Besides the inner product, previously described, which maps two vectors to a scalar, there are other products which can be formed from a binary operation on vectors. A scalar is a rank-0 tensor, so the natural progression is to come up with an operation that forms a vector (rank-1 tensor). You might know this as the *cross product*. 

$$
\begin{equation}
\vec{a} \cross \vec{b} = \epsilon_{ijk}a_{j}b_{k}\hat{e}_{i}
\end{equation}
$$

Remember that in index notation, repeated indices indicate summation, so the above expands to,

$$
\begin{align}
\vec{a} \cross \vec{b} &= \left(\epsilon_{123}a_{2}b_{3} + \epsilon_{132}a_{3}b_{2}\right)\hat{e}_{1} 
                            + \left(\epsilon_{231}a_{3}b_{1} + \epsilon_{213}a_{1}b_{3}\right)\hat{e}_{2}
                            + \left(\epsilon_{312}a_{1}b_{2} + \epsilon_{321}a_{2}b_{1}\right)\hat{e}_{3} \\
                    &= \left(a_{2}b_{3} - a_{3}b_{2}\right)\hat{e}_{1} 
                        + \left(a_{3}b_{1} - a_{1}b_{3}\right)\hat{e}_{2}
                        + \left(a_{1}b_{2} - a_{2}b_{1}\right)\hat{e}_{3} \\
                    &= \left(a_{y}b_{z} - a_{z}b_{y}\right)\hat{e}_{x} 
                        + \left(a_{z}b_{x} - a_{x}b_{z}\right)\hat{e}_{y}
                        + \left(a_{x}b_{y} - a_{y}b_{x}\right)\hat{e}_{z}
\end{align}
$$

as evident from the last line, it is straightforward to convert from $ijk \in \\{123\\}$ to $ijk \in \\{xyz\\}$, and see that the above is equivalent to the standard, determinant-based, formulation of the vector product.   

#### Deriving Vector Identities
&nbsp;&nbsp;&nbsp;&nbsp; Vector calculus is the basis for almost every field of classical physics, e.g., electromagnetism, dynamics, fluid mechanics, etc.. Acquiring an understanding of these fields that is more than just surface level frequently requires manipulating expressions that feature combinations of vector and cross products involving the state variables characterizing the physical system, e.g., $\vec{E}, \vec{B}, \vec{J}$, in electromagnetism, or $\rho, \vec{u}, p$, in fluid dynamics, and their gradients, $\nabla$. 

&nbsp;&nbsp;&nbsp;&nbsp;


<!-- References -->
[^1]: https://en.wikipedia.org/wiki/Levi-Civita_symbol