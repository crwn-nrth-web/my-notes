---
title: postulates-of-quantum-mechanics
draft: false
tags:
  - physics
---
 
**Postulate #1** = To an ensemble of physical systems one can, in certain circumstances associate a wave function or state function which contains all the information that can be known about the ensemble. This function is in general complex; it can be multiplied by an arbitrary complex number without altering its physical significance

**Postulate #2 = Superposition principle** 
$$
\psi = c_{1} \psi_{1} + c_{2} \psi_{2}
$$
This is from the inference pattern observed from the double slit experiment

**Postulate #3** = every dynamic variable is associated with a linear operator
- dynamic variables are measurable (*observables*)[^1]
- observables exhibit wave like functions until a measurement is taken and causes the wave function to collapse

**Postulate #4** = the only result of a precise measurement of a dynamic variable A is one the eigenvalues $a_n$ of the linear operator $\hat{A}$ associated with A[^2]
- the set of eigenvalues of A = *spectrum of A*
- the spectrum can be discrete or continuous
- the spectrum of an operator representing a dynamic variable must be real because the results of the measurement are real = these operators are called *Hermitian operators*

**Postulate #5** = if a series of measurements are made of a dynamic variable A in an ensemble of systems described by a wave function $\psi$, then the *expectation value*, or average value, of the dynamic variable is 
$$
<A> = \frac{\braket{\psi|A|\psi}}{\braket{\psi|\psi}} = \frac{\int dr \ \ \psi(r)^* A \psi(r) }{\int dr \ \ \psi(r)^* \psi(r)}
$$
For a general case,
$$
<A> = \braket{\psi | A | \psi} = \int d \alpha \braket{\psi|\alpha} \braket{\psi|A|\psi} = \int d \alpha \ \ a(\alpha) \ \ |c(\alpha)|^2  
$$

**Postulate #6** = A wave functon representing any dynamic state can be expressed as a linear combination of the eigenfunctions of A, where A is the operator associated with the dynamic variable

In other words, for a continuous case = 
$$
\int d \alpha \ \  \ket{\alpha}\bra{\alpha} = I   
$$
where $\{\ket{\alpha} \}$ are the set of eigenfunctions of A

**Postulate #7** = the time evolution of the wavefunction of a system is determined by the *time dependent Schrodinger equation*
$$
i \hbar \frac{\partial \psi(r,t)}{\partial t} = \mathbb{H} \psi(r,t) 
$$
where $\mathbb{H}$ is the *Hamiltonian* (or total energy) operator
$$
\mathbb{H} = - \frac{\hbar^2}{2m} \nabla^2 + V(r,t)
$$
*Time independent Schrodinger equation* = when $V(r,t)$ is independent of time, the Schrodinger equation reduces to the time independent Schrodinger equation 
$$
\mathbb{H} \alpha_{n} (r) = E \alpha_{n} (r) \ \ or \ \ - \frac{\hbar^2}{2m} \nabla^2 \alpha_{n} (r) + V(r) \alpha_{n} (r) = E \alpha_{n} (r)
$$



[^1]: see [[Formalism-of-quantum-mechanics#Operators]]

[^2]: see [[Formalism-of-quantum-mechanics#Eigenvalue equations]]
