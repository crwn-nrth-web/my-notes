---
title: oscillations
draft: false
tags:
  - physics
---
**resonance** = timing such that the energy you put in a system adds to the total energy

**parametric resonance** = phenomena where a system's vibration grows exponentially. This happens when a system parameter (spring constant or length) changes periodically.
- the driving frequency must be twice the system's natural frequency

### Kapitsa's Pendulum
vertical oscillations of the pivot of a pendulum can lead to **parametric resonance** (by effectively modulating "g")

![[Pasted image 20260710092137.png|286]]

position of the mass:
- $X = l\sin \theta$
- $Y = -l\cos \theta + d\sin wt$

Resonance occurs when the modulation frequency is twice the natural frequency of the pendulum.

### Spring pendulum
Consider a pendulum where the string is replaced by an ideal spring with equilibrium length l and spring constant k. A mass is attached to the end of the spring.

Using x and $\theta$ as generalized coordinates, the position of the mass is given by:
- $X = (l+x) \sin \theta$
- $Y = -(l+x) \cos \theta$

$$\mathcal{L} = \frac{1}{2}m [\dot{x} + (l+x)^2 \dot{\theta}^2] + mg(l+x)\cos \theta -\frac{1}{2}kx$$

**auto parametric resonance** occurs as there is no control to the change in system parameter (in this case length).

### Coupled oscillators
**Coupled oscillators** = when two or ($n$ number of) oscillators are connected in such a way that energy can transfer among them

Using generalized coordinates gives $n$ number of coupled second order differential equations. 

To solve coupled differential equations,
1. write the equations of motion in matrix form
2. for oscillations, we expect the solution to be in the form of $q = Ce^{-i\lambda t}$ . Substitute this into the matrix equation
3. set the determinant to zero and find the eigenvalues $\lambda^2$
4. find the eigenvectors

The **normal modes** can be written using the eigenvalues and the eigenvectors. 
Given eigenvalue $\lambda_1$ and $\lambda_2$ and eigenvectors $\begin{pmatrix} 1 \\ 1\end{pmatrix}$ and $\begin{pmatrix} 1 \\ -1\end{pmatrix}$ respectively =
1.  $\begin{pmatrix}q_{1}  \\ q_{1} \end{pmatrix} = \begin{pmatrix}1 \\ 1\end{pmatrix}e^{-i \lambda_{1} t}$
2. $\begin{pmatrix}q_{1}  \\ q_{1} \end{pmatrix} = \begin{pmatrix}1 \\ -1\end{pmatrix}e^{-i \lambda_{2} t}$

Note that 
- **symmetric mode** refers to when the behavior of the system remains unchanged under symmetry (same signs in the eigenvectors). 
	- E.g. normal mode 1 in the above example is the symmetric mode
- **antisymmetric mode** refers to when the system changes sign under symmetry
	- E.g. normal mode 2 is the antisymmetric mode
- in 3 oscillator cases, the symmetry operator is reflection about the center mass

The **normal coordinates** can be used to describe the system in such a way that no coupling occurs, even though there is coupling in the generalized coordinates.
- Using the normalized eigenvectors, we can find the normal coordinates
