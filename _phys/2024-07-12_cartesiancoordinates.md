---
layout: post
title: Coordinate Systems in Physics - Cartesian Coordinates
date: 2024-07-12
collection: phys
---
### Some Introductory Musings
&nbsp;&nbsp;&nbsp;&nbsp;In Algebra I, we learn about the variable, $x$. After this introduction, we learn about some basic mathematical rules and structures that help us to determine what it is in certain situations, giving us the ability to study a variety of equations. In college-level physics, we start to apply the concept of $x$ by studying motion in one dimension. The range of physical behavior we can meaningfully study is very limited if we are restricted purely to the tools of algebra so, in order to expand our horizons, we loop in calculus, differential equations, and linear algebra. This point represents a great filter in the education of many students as many unfortunately don't have the interest in acquiring these skills, or labor under the yoke of negative attitudes from their peers, or instructors. 

&nbsp;&nbsp;&nbsp;&nbsp;Since the subject has arisen, I don't personally believe in Great Filters as the primary explanation for why we have not yet interacted with extraterrestrial intelligent life. Earth is located in the KBC supervoid, an underdense region of the universe approximately 1 billion light years across (lya). We live in the cosmical equivalent of the North Pole, capable of communicating with the outside only by sending pulses of light, like an eskimo reflecting the rays of the sun off of a chunk of ice.    

&nbsp;&nbsp;&nbsp;&nbsp;Acquiring a working understanding of calculus, differential equations, and linear algebra gives us the ability to study a much wider range of physical systems. At some point, to acquire an even deeper understanding of these systems, mastery with these tools, and others, will eventually be necessary. Roughly-speaking, this need is related to the extra dimensions which we begin to encounter the deeper we go into physics. For example, if we wanted to describe ballistic motion, which humans have wanted to do for millenia in order to lob projectiles at other hominids with greater accuracy, and destructive energy, one dimension is not enough. Fortunately, as our species' capacity for destruction has increased, it seems that our interest in it has begun to wane, and we can use the same theory to describe the motion of a basketball.      

#### Cartesian Coordinates - A Basis for Ballistic Motion
&nbsp;&nbsp;&nbsp;&nbsp;A projectile that has been lobbed at a target requires at least two-dimensions to obtain a description of its motion, so in addition to $x$, we also have a $y$. A complete analysis of the motion of a ballistic particle would actually require a third dimension, $z$. This third dimension also involves an expansion to the range of phenomena we are capturing with our model, so to a reasonable level we just start with two. Newton's *Principia*, in the late 17th-century, provided the first major successful attempt to describe the dynamics of nature using mathematics. In this work, Isaac Newton stated some laws of motion, and used calculus to analyze the motion of rigid bodies. Newton was a very strange man, and his notation is somewhat cumbersome, so today, we use a calculus that is intellectually descended from Leonhard Euler, one of the greatest mathematicians in history. Newton's three laws of motion are enduring, however, and we can state them as follows:

(1) An object in motion stays in motion, and an object at rest stays at rest, unless acted upon by a net external force

(2) $\vec{F} = \dv{\vec{p}}{t}$

(3) Every force has an equal and opposite reaction force

&nbsp;&nbsp;&nbsp;&nbsp;In practice, the second law is the one utilized the most, and that is what we are going to do here in two dimensions. In doing so, we are going to neglect some physical effects that are important to many ballistic situations, e.g., the Coriolis force, and in the spirit of further simplification, we are also going to neglect many others, e.g., the Magnus force, Drag force, etc., and consider only the force of gravity with strength, $g$, acting on a point particle with fixed mass, $m$. Then, we can write a system of linear, second-order, differential equations describing the motion of the particle,

$$
\begin{align}
\vec{F} &= -mg \hat{y} \\
\therefore F_{x} &= m a_{x} = m \ddot{x} = 0 \\
F_{y} &= m a_{y} = m \ddot{y} = -mg \\
\rightarrow \ddot{x} &= 0 \\
\ddot{y} &= -g 
\end{align}
$$

To solve this system of ODEs, we just integrate twice, yielding,

$$
\begin{align}
x(t) &= x_{0} + v_{0,x}t \\
y(t) &= y_{0} + v_{0,y}t - \frac{g}{2} t^{2}
\end{align}
$$

<!-- References -->
<!-- https://en.wikipedia.org/wiki/Local_Hole -->
<!-- https://en.wikipedia.org/wiki/Philosophi%C3%A6_Naturalis_Principia_Mathematica -->
<!-- https://en.wikipedia.org/wiki/Leonhard_Euler -->