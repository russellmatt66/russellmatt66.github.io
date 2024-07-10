---
layout: post
title: Introduction to Plasmas - Single Particle Motion
collection: phys
---
### Single Particle Motion  
&nbsp;&nbsp;&nbsp;&nbsp;Plasma physics is the study of the behavior of plasmas. This study frequently begins with the question "What is a plasma?" Roughly-speaking, it is a gas of charged particles. These particles interact primarily through long-range electromagnetic forces, and all-together, can exhibit a wide spectrum of behavior across multiple scales. As a collection of charged particles, understanding of a plasma's behavior can be gleaned by studying the motion of charged particles in an electromagnetic field. In the majority of interesting plasmas, this motion is governed by Newtonian mechanics subject to the impact of the Lorentz Force,

$$
\vec{F} = q_{s}(\vec{E} + \vec{v} \times \vec{B})
$$

&nbsp;&nbsp;&nbsp;&nbsp;The above equation represents a system of three coupled ordinary differential equations (ODEs) that describe the forces which a charged particle of species, $s$, feels

$$
\begin{align}
F_{x} &= m_{s}\ddot{x} = q_{s}E_{x} + q_{s}(v_{y}B_{z} - v_{z}B_{y}) \\
F_{y} &= m_{s}\ddot{y} = q_{s}E_{y} + q_{s}(v_{z}B_{x} - v_{x}B_{z}) \\
F_{z} &= m_{s}\ddot{z} = q_{s}E_{z} + q_{s}(v_{x}B_{y} - v_{y}B_{x})
\end{align}
$$

In a textbook on plasma physics, this is the point where the author would begin to assume various forms for the $\vec{E}$, and $\vec{B}$, fields, and demonstrate the corresponding solution. 

#### Case 1: Uniform B
The simplest case is when the magnetic field is steady, and uniform, in a single direction. Convention in plasma physics is to take this to be in the z-direction. [Maxwell's Equations](./2024-06-9_maxwell) completely describe the behavior of an electromagnetic system, one which is characterized by charges, currents, and associated electric, and magnetic fields. Using Faraday's Law, we can see that a uniform, steady, magnetic field implies an irrotational electric field,

$$
\begin{align}
\vec{B} &= B_{0}\hat{z} \\
\rightarrow \pdv{\vec{B}}{}{t} &= 0 = \curl \vec{E} \\
\end{align}
$$

$$
\begin{align}
\therefore \partial_{y}E_{z} - \partial_{z}E_{y} &= 0 \\
\partial_{z}E_{x} - \partial_{x}E_{z} &= 0 \\
\partial_{x}E_{y} - \partial_{y}E_{x} &= 0 
\end{align}
$$ 

It is a common, and unfortunate, misconception that physics, and more broadly, mathematics, is an unimaginative, rote discipline. We have the freedom, and therefore the creativity, to specify the components of the electric field to be whatever we wish them to be, so long as they satisfy the above linear system of PDEs. 

&nbsp;&nbsp;&nbsp;&nbsp;There is another equation of Maxwell's that relates the electric and magnetic field directly, it is Ampere's Law,

$$
\begin{align}
&\curl \vec{B} = \mu_{0}\vec{J} + \frac{1}{c^{2}}\pdv{\vec{E}}{}{t} \\
&\vec{B} = B_{0}\hat{z} \rightarrow \mu_{0}\vec{J} + \frac{1}{c^{2}}\pdv{\vec{E}}{}{t} = 0 \\
&\rightarrow \vec{J} = -\epsilon_{0}\pdv{\vec{E}}{}{t}
\end{align}
$$

however, it takes more than a single particle to make up a current, so we treat the problem of single particle motion under the assumption that there are no currents or charge densities. Considering how small charged particles are, this is a good assumption. 

$$
\begin{align}
\therefore \pdv{\vec{E}}{}{t} = 0 \rightarrow \vec{E} = \vec{E}(\vec{x})
\end{align}
$$

We can choose $\vec{E}$ to be anything which satisfies the basic laws of electromagnetics, i.e., Maxwell's Equations, but the art of physics is all in selecting examples which lucidly demonstrate an aspect of how nature behaves. 

#### Case 1a: $\vec{E} = 0$
&nbsp;&nbsp;&nbsp;&nbsp;As it turns out, we can do this without having to churn through pages of algebra by selecting the "trivial case" where the electric field is zero. The governing equations then become,

$$
\begin{align}
\dot{v_{x}} &= \frac{q_{s}}{m_{s}}B_{0}v_{y} \\
\dot{v_{y}} &= -\frac{q_{s}}{m_{s}}B_{0}v_{x} \\
\dot{v_{z}} &= 0
\end{align}
$$

where it was helpful to recast the second-order ODEs in position as first-order ODEs in velocity because this leaves us with a system of coupled, first-order, linear ODEs with the simplifications that we input. Furthermore, we can observe there is a factor that has appeared which is common to both differential equations. You might recognize this factor as the **cyclotron frequency**, the number of radians that a particle in a magnetic field rotates through in one second,

$$
\begin{align}
\omega_{cs} \equiv \frac{\abs{q_{s}}B_{0}}{m_{s}}
\end{align}
$$

&nbsp;&nbsp;&nbsp;&nbsp;To solve the motion of a single charged particle in the fields we've specified, we take another time derivative of each of the differential equations that we have. Before proceeding with this, note that $\dot{v_{z}} = 0$ implies that $z = z_{0} + ct$, which you can prove by integrating twice. Wherever the particle was along the magnetic field line, and however fast it was moving in the local direction of the field line, it will maintain that motion without the influence of an electric field. For motion perpendicular to the field line this situation is different, because the particle feels the Lorentz force of the magnetic field bending it around in a circle. Oops! I just asserted the punchline, so let's prove it. 

$$
\begin{align}
\ddot{v_{x}} &= \pm\omega_{cs}\dot{v_{y}} \\ 
\ddot{v_{y}} &= \mp\omega_{cs}\dot{v_{x}}
\end{align}
$$

When I was first learning about single particle motion, I found the addition of the sign factors, $\pm$, and $\mp$, to be confusing. The reason for their inclusion has to do with our definition of the cyclotron frequency being in terms of the magnitude of the particle charge, instead of its value, which is what shows up in our equations. We choose to define $\omega_{cs}$ in this way because it precludes the quantity from being negative, as a negative cyclotron frequency makes no sense. However, since our equations are in terms of $q_{s}$, we must add the aforementioned sign factors to maintain consistency.

$$
\begin{align}
q_{s} &= \pm \abs{q_{s}} \\
-q_{s} &= \mp \abs{q_{s}}
\end{align}
$$

where it should be understood that the top sign is chosen when the particle charge is positive, and the bottom chosen when it is negative. 

&nbsp;&nbsp;&nbsp;&nbsp;Substituting $\dot{v_{x}}$, and $\dot{v_{y}}$, into the above, we obtain one of the most well-known equations in physics,

$$
\begin{align}
\ddot{v_{x}} + \omega_{cs}^{2}v_{x} &= 0 \\
\ddot{v_{y}} + \omega_{cs}^{2}v_{y} &= 0 
\end{align}
$$

the **Simple Harmonic Oscillator** (SHM). Specifically, these are examples of **homogeneous** differential equations, ones that are equal to zero, and which are generally easier to solve than **heterogeneous** differential equations, where the RHS is non-trivial. In the case of an SHM where there is a forcing function being applied, e.g., a child in a swing being pushed by their parent, we would have a heterogeneous ODE. The analytical solution in that case, if there even *is* one, would depend on the exact force being applied. Fortunately, the SHM is homogeneous, and has an analytical solution, namely a sinusoid!

$$
\begin{align}
v_{x} &= v_{\perp}cos(\omega_{cs}t + \phi) \\
v_{y} &= \mp v_{\perp}sin(\omega_{cs}t + \phi) 
\end{align}
$$

*Hold on*, you may be thinking, *why does $v_{y}$ have a $\mp$ attached to it?*