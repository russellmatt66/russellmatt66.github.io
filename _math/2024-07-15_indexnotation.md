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

#### Back to Index Notation
&nbsp;&nbsp;&nbsp;&nbsp; Index notation is a wonderful tool. Trying to do vector calculus without index notation is like trying to walk when you could be running. The great filter of mastering index notation is understanding the [**Levi-Civita**](https://en.wikipedia.org/wiki/Levi-Civita_symbol) tensor, $\epsilon_{ijk}$[^1]. The first time I saw this symbol in undergraduate classical dynamics, I was confused, and frustrated. *What the hell is this*, I thought in consternation, *bring back the ODEs*. It wasn't until becoming immersed in vector calculus in graduate school that I became enamored with its utility. 

&nbsp;&nbsp;&nbsp;&nbsp; I called it a tensor, and expressed its rank-3 tensorial form above, but the Levi-Civita *symbol* can actually be defined for any number of dimensions, $D$. With a space complexity of $\mathcal{O}(D^{3})$ needed in order to write down all of its terms, trying to do so becomes very inefficient, very quickly. However, it is very easy to describe what the value of any single term of the LV symbol is based on the order of the indices. If the indices are *cyclic*, that is, from left to right they are ordered numerically in a modular fashion, then the value of is 1. If they are *anti-cyclic*, meaning they are are ordered numerically in a modular fashion from right to left, then the value is -1. Anything else, and the value is 0.   

<!-- References -->
[^1]: https://en.wikipedia.org/wiki/Levi-Civita_symbol