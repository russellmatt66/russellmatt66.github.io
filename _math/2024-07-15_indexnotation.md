---
layout: post
title: Index Notation
date: 2024-07-15
collection: math
---
### Index Notation
&nbsp;&nbsp;&nbsp;&nbsp; You can go far in understanding plasmas on the back of Magnetohydrodynamics ([MHD](./2024-06-15_mhd)), and you can go far in MHD on the back of understanding vector calculus. However, the more vector calculus you do, the more you run into a fundamental issue with the discipline. When you're flinging nabla's, ($\nabla$), your state variables, inner products, outer products, dyadic products, etc., together, you start having to do a lot of writing, a lot of memorizing of identities in order to manipulate them, and you start losing insight into the underlying equations under the mask of all the symbols. Einstein came up with a brilliant way of addressing all three of these problems by developing a shorthand notation for expressing these kinds of equations.      

&nbsp;&nbsp;&nbsp;&nbsp; If you wanted to write an inner product, between two vectors, then you could do so in the following way,

$$
\begin{equation}
\vec{a} \cdot \vec{b} = \sum_{i} a_{i}b_{i}
\end{equation}
$$

While pioneering quantum theory through his explanation of the photoelectric effect, developing his field equations, and just otherwise dominating the field of physics, Einstein worked with inner products frequently. Eventually, he grew tired of writing $\sum$ over and over, and just dropped it, choosing instead to communicate its presence implicitly whenver there was a repeated index. For example, using this *index notation*, you would write Now, before I continue, because I anticipate 