---
draft: false
title: Formalism-of-quantum-mechanics
tags:
  - physics
---
 
**Dirac notation** or *bra-ket notation* is a way of writing quantum
in [[#Position representation]] =
$$
\braket {\psi_1 | \psi_2} = \int \ dr \ \psi^* _1 (x) \ \psi_2 (x)
$$
in [[#momentum representation]] =
$$
\braket {\psi_1 | \psi_2} = \int \ dp \ \  \bar{\psi^* _1 (p)} \ \ \bar{\psi_2 (p)}
$$
- *bra* $\bra{\psi}$ = linear function of a vector
- *ket* $\ket{\psi}$ = vector

*Properties* = associative, distributive and commutative
- if a system is associative and distributive, then the system is linear

$\psi_1$ and $\psi_2$ are **orthogonal** $\braket {\psi_1 | \psi_2} = 0$
$\psi_1$ and $\psi_2$ are **normalized** $\braket {\psi| \psi} = 1$
$\psi_1$ and $\psi_2$ are **orthonormal** (both orthogonal and normalized)  
$$
\int \ dr \ \psi^* _1 (x) \ \psi_2 (x) = 0
$$


**Hilbert space** Hilbert space is similar to a vector space 
- Hilbert space is linear
- inner product exists 
$$
\braket {\psi_1 | \psi_2} = \int \ dr \ \psi^* _1 (x) \ \psi_2 (x)
$$
- length of vector = $\braket {\psi| \psi}$

**Kronecker delta** shows *orthonormality* 
$$
\int \ dr \ \psi^* _1 (x) \ \psi_2 (x) = \delta_{nm} = \braket{n|m}
$$
where
- when n $=$ m , $\delta = 1$
- when n $\neq$ m, $\delta = 0$

**Projection**
the coefficient $c_n$ is the projection of $\psi$ onto the vector $\ket{n}$ 
$$
\psi (r) = \sum_{n} \ c_n \ \psi_{n} (r) \ \ \textrm{ or } \ \ \ket{\psi} = c_n \ket{n}
$$
**Dirac delta function** $\delta (r - r')$ or $\sum_n \ket{n} \bra{n} = \delta (r - r')$ 

*closure relation* An orthonormal basis set $\{ \ \ket{n} \ \}$ is a basis set if for every function $\psi(r)$, the function can be expressed in 
$$
\sum_{n} \psi_{n}^* (r') \ \psi_n(r) = \delta (r - r')
$$
*sifting property of the dirac delta function*
$$
\int \ d\beta \ c(\beta) \ \delta(\alpha - \beta) = c(\alpha) 
$$

**Discrete orthonormal basis set**
orthogonal = 
$$ 
\int \ dr \ \psi^* _1 (r) \ \psi_2 (r) = \delta_{nm} \ \ \textrm{ or } \ \ \braket{n|m} = \delta_{nm}
$$
spans the space =
$$
\sum_{n} \psi_{n}^* (r') \psi_{n} (r) = \delta (r - r') \ \ \textrm{ or } \ \ \sum_{n} \ket{n} \bra{n} = I
$$
**Continuous orthonormal basis set**
orthogonal =
$$ 
\int \ dr \ \omega^* _{\alpha} (r) \ \psi_{\beta} (x) = \delta (\alpha - \beta) \ \ \textrm{ or } \ \ \braket{\alpha|\beta} = \delta (\alpha - \beta)
$$
spans the space =
$$
\int \ d\alpha \ \psi_{\alpha}^* (r') \psi_{\beta} (r) = \delta (r - r') \ \ \textrm{ or } \ \ \int \ d\alpha \ \ket{\alpha} \bra{\alpha} = I
$$
**generalization of continuous basis set**
the wave function can be expressed as 
$$ 
\psi (r) = \int \ d\alpha \ c(\alpha) \ \omega_{\alpha} (r)
$$
where $c(\alpha) = \int \ dr \ \omega_{\alpha}^* (r) \ \psi (r)$

In dirac notation =
$$
\ket{\psi} = \int \ d\alpha \ c(\alpha) \ \ket{\omega}
$$
where $c(\alpha) = \braket{\alpha | \omega}$

##### Position representation
$$
\Omega_{r'} (r') = \delta (r - r') = \ket{r'}
$$
**Position space**  is the set of all position vectors *r* in Euclidean space, and has the dimensions of length, where a position vector defines a point in space.

The wave function is represented as $\braket{r|\psi} = \psi(r)$

**Position operator** ($X$)
$$
\braket{r| X | \psi} = x\braket{r|\psi} \ \  \textrm{ or } \ \ X \psi(r) = x \ \psi (r)
$$
The position operator $X$ has the position $x$ of a quantum mechanical particles as eigenvalues

*expectation value* of the position components of a particle = 
$$
\braket{\psi | X | \psi} = \braket{X} = \int \ dr \ \psi^* (r) \ x \ \psi (r) = \int \ dr \ x \ |\psi (r)|^2 
$$
##### momentum representation
$$
\mu_{p'} (r) = (2\pi \hbar) ^{-3/2} e^{\frac{i}{\hbar} \ p' \cdot r} = \ket{p'}
$$
wave function in momentum representation =
$$
\braket {p | \psi} = \frac{1}{(2\pi \hbar)^{3/2}} \int \ dr \ e^{\frac{i}{\hbar} \ p \cdot r} \ \psi(r) = \bar{\psi}(p)
$$
inner product in momentum representation = 
$$
\braket{\psi_{1}|\psi_{2}} = \int \ dp \ \bar{\psi}_{1}^* (p) \ \bar{\psi_{2}} (p)
$$

**momentum operator** $\hat{P}$
- in the momentum representation = 
$$
\braket{p|\hat{P}|\psi} = \mathbf{p} \braket{p|\psi}
$$
- in position representation = 
$$
\braket{r|\hat{P}|\psi} = \frac{\bar{h}}{i} \nabla \ \psi(r) = \frac{\bar{h}}{i} \frac{ \partial \psi(r) }{ \partial x } 
$$
*expectation value* 
$$
<P_{x}> \ = \int dr \ \psi (r) \ \frac{\bar{h}}{i} \frac{ \partial \psi(r) }{ \partial x } 
$$
$$
<P> \ = \ m \frac{ \partial <x> }{ \partial t }  
$$

