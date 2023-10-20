---
layout: post
title: Best In Class Parallel Performance
collection: hpc
---
### Introduction
&nbsp;&nbsp;&nbsp;&nbsp;Tensor-based algorithms are frequently encountered in computing, and are also located firmly in the category of "embarassingly-parallel". Algorithms of this class are called as such because, once the basic concepts behind parallelism are understood, it is obvious--almost embarassingly so--how to parallelize them. That does not mean the implementation is easy, however. Like many things, the devil is in the details. First, a brief primer on parallellism and tensors, i.e., the generalization of scalars, vectors, and matrices. 

### Parallelism: A First Course 
&nbsp;&nbsp;&nbsp;&nbsp;There are two basic kinds of parallelism:
1. Task-based parallelism
2. Data-based parallelism

&nbsp;&nbsp;&nbsp;&nbsp;"Task-based" parallelism occurs when there are independent tasks to be done that do not depend on each other. For a real-world example from the field of cooking, when making bacon and eggs, there's no need to wait for the bacon to finish before beginning to cook the eggs (unless, of course, you wish to fry the eggs in the bacon grease). This analogy is imperfect, not just because of the pathological example, but also because a single chef making a meal is a sequential context. However, even with only a single chef (thread), the appearance of concurrency can be implemented provided the worker moves fast enough.  

&nbsp;&nbsp;&nbsp;&nbsp;"Data-based" parallelism occurs when there is independent data that can be operated on. What's a real world example of this? Well, how about grading an exam? Let's say the exam has 4 questions. Each question is independent of the other questions, so there's no real need to have graded question A before grading question B, question B before question C, etc.. Therefore, we can partition the task of grading the questions amongst a set of graders, and speed the completion of the process up.  

### Tensors: The Generalization of a Matrix 
&nbsp;&nbsp;&nbsp;&nbsp;When you have a single piece of atomic numerical data, for example, the number $6$, that can be thought of as a scalar. Add another number to the collection, say $5$, and now you've got a vector,

$$
\vec{a} = \colvec{6\\5}
$$

In the process, you've increased the dimensionality of the object from 0D (just a single point), to 1D (just a single column). There's nothing particularly special about representing our vector as a column, we could just as easily represent it as a row. The way we switch a vector between the two is by using the transposition operator,

$$
\vec{b} = \rowvec{6 \quad 5} = \vec{a}^{T}
$$

&nbsp;&nbsp;&nbsp;&nbsp;What happens if we increase the dimensionality of our object again? Well, we go from 1D to 2D. Now, our object has both rows and columns, and is identified by the name of "matrix". When we constructed our vector, $\vec{a}$, we did so by specifying the elements directly. There's nothing inherently wrong about doing it this way, but imagine if our vector was larger than just two elements, for example, if it was 10,000. It would be quite cumbersome to write down every single one of those elements. This is why we use computers.

&nbsp;&nbsp;&nbsp;&nbsp;Vectors are rarely that long, however. Exceptions exist, of course, but macroscopic physical systems of interest to engineers and applied physicists are typically based on 3-vectors, e.g., the magnetic field of a plasma,

$$
\vec{B} = \colvec{B_{x}\\B_{y}\\B_{z}}
$$

