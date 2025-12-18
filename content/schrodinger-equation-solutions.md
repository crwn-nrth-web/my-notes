---
title: schrodinger-equation-solutions
draft: false
tags:
  - physics
---
#### CASE 1: Infinite square well (Particle in a box)
Choosing a 1D "box" as the potential where
$$
V(r) = \begin{cases}
0   & when \ \ 0 \leq x \leq a \\ \infty  & otherwise
\end{cases}
$$
Outside the box, $\psi(x,t) = 0$

We solve the differential equation with $V(x) = 0$ between $x=0$ and $x=a$ for the eigenfunctions and eigenvalues of $\mathbb{H}$

Time independent Schrodinger equation for infinite square well =
$$
-\frac{\hbar^2}{2m} \frac{\partial^2 \psi(x)}{\partial x^2} = E \psi (x)
$$
##### Solutions for the infinite square well

**Discrete Energy values** (*eigenvalues of $\mathbb{H}$*) = 
$$
E_{n} = \frac{n^{2} \psi^{2} \hbar^{2}}{2ma^{2}}
$$
**Allowed states** (*eigenfunctions of $\mathbb{H}$*) = 
$$
\phi_{n} (x) = \sqrt{\frac{2}{a}} \sin\left( \frac{n\pi}{a} x \right)
$$
**Stationary states** =
The solutions to the time independent Schrodinger equation can be used to write the *time dependent stationary wave function* =
$$
\psi(x,t) = \sum_{n=1}^\infty c_{n} \sqrt{ \frac{2}{a} } \sin\left( \frac{n\pi}{a} x \right) e^{-i (n^2 \pi^2 \hbar^2 / 2ma^2) t}
$$
where 
$$
c_{n} = \sqrt{ \frac{2}{a} } \int_{0}^a \sin\left( \frac{n\pi}{a} x \right) \psi(x,0) \ \ dx
$$
**method of solving** =
Differential equation
$$
\frac{\partial^{2} \psi}{\partial x^2} = -k^2 \psi 
$$
where $\phi (n) = A\sin(kx) B\cos(kx)$

*general solution* = 
$$
\phi (x) = A \sin\left( \frac{n\pi}{a}x \right)
$$
*stationary states* =
$$
\psi(x,t) \sum_{n=1}^\infty c_{m} \phi_{m} (x) e^{-i Et/\hbar}
$$where 
$$
c_{m} = \sum_{n} c_{n} \braket{ m | n } = \braket{ m |\psi(0) }  
$$

#### CASE 2: Harmonic oscillator
The harmonic oscillator is represented by the force equation $F = -kx$ which gives the potential energy $V(x) = -kx^2 / 2$ 

Many potentials reduce to this form for small values of x, so many phenomena can be understood using the harmonic potential

For quantum systems, we want to solve the Schrodinger equation using the potential 
$$
V(x) = \frac{1}{2} m \omega^2 X^2 \ \ , \ \ \omega = \sqrt{ \frac{k}{m} }
$$
Time independent Schrodinger equation for harmonic oscillator =
$$
-\frac{\hbar^2}{2m} \frac{\partial^2 \psi(x)}{\partial x^2}  + \frac{1}{2} m \omega^2 X^2 \psi(x)  = E \psi(x)
$$
This can be solved using the same method as for [[#CASE 1 Infinite square well (Particle in a box)]] but can be solved quicker using [[harmonic-oscillator-ladder-operators]]

##### Solutions to the harmonic oscillator
The equation has an infinite number of discrete solutions

**ground state wave function** =
$$
\psi_{0} (x) = {\frac{m \omega}{\pi \hbar}}^{1/4} e^{- (m \omega / 2\hbar )x^2}
$$
**ground state energy** = 
$$
E_{0} = \frac{1}{2} \hbar \omega
$$

**High energy solutions** =
$$
\psi_{n} (x) = A_{n} (a_{+})^n \psi_{0} (x)
$$
where $A_n$ is the normalization constant
$$
E_{n} = \left( n+ \frac{1}{2} \right) \hbar \omega
$$
