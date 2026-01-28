---
draft: false
title: Formalism-of-quantum-mechanics
tags:
  - physics
---
Quantum theory is based on two constructs:
1. the state of a system is represented by its wave function
2. observables are represented by operators
Mathematically, wave functions satisfy the conditions for abstract vectors and operators act on them as linear transformations.
### Dirac notation
**Dirac notation** or *bra-ket notation* is a way of writing quantum
- *bra* $\bra{\psi}$ = linear function of a vector
- *ket* $\ket{\psi}$ = vector

$\psi_1$ and $\psi_2$ are **orthogonal** $\braket {\psi_1 | \psi_2} = 0$
$\psi_1$ and $\psi_2$ are **normalized** $\braket {\psi| \psi} = 1$
$\psi_1$ and $\psi_2$ are **orthonormal** (both orthogonal and normalized)  
$$
\int \ dr \ \psi^* _1 (x) \ \psi_2 (x) = 0
$$
**Kronecker delta** shows *orthonormality* 
$$\int \ dr \ \psi^* _1 (x) \ \psi_2 (x) = \delta_{nm} = \braket{n|m}$$where
- when n $=$ m , $\delta = 1$
- when n $\neq$ m, $\delta = 0$

**Projection** = the coefficient $c_n$ is the projection of $\psi$ onto the vector $\ket{n}$ 
$$
\psi (r) = \sum_{n} \ c_n \ \psi_{n} (r) \ \ \textrm{ or } \ \ \ket{\psi} = c_n \ket{n}
$$
**Dirac delta function** =  $\delta (r - r')$ or $\sum_n \ket{n} \bra{n} = \delta (r - r')$ 

*closure relation* An orthonormal basis set $\{ \ \ket{n} \ \}$ is a basis set if for every function $\psi(r)$, the function can be expressed in 
$$
\sum_{n} \psi_{n}^* (r') \ \psi_n(r) = \delta (r - r')
$$
*sifting property of the Dirac delta function*
$$
\int \ d\beta \ c(\beta) \ \delta(\alpha - \beta) = c(\alpha) 
$$
**Inner product**
in [[#Position representation]] =
$$
\braket {\psi_1 | \psi_2} = \int \ dr \ \psi^* _1 (x) \ \psi_2 (x)
$$
in [[#momentum representation]] =
$$
\braket {\psi_1 | \psi_2} = \int \ dp \ \  \bar{\psi^* _1 (p)} \ \ \bar{\psi_2 (p)}
$$
#### Hilbert space
**Hilbert space** is similar to a vector space but for wave functions.
- Hilbert space is linear
- inner product exists 
$$
\braket {\psi_1 | \psi_2} = \int \ dr \ \psi^* _1 (x) \ \psi_2 (x)
$$
- length of vector = $\braket {\psi| \psi}$

The state of a quantum system is characterized by its state vector $\ket{\alpha}$ which is an element of the **Hilbert space**. All physical information about the given system is in its state vector

To say that a quantum system characterized by an *n-dimensional Hilbert state* means that each possible state of the system can be represented by a state vector $\ket{\alpha}$ with n complex components, and can be written as

$$
\ket{\alpha} = \begin{bmatrix}
a_{1} \\ a_{2} \\ . \\ . \\ a_{n}
\end{bmatrix} 
$$
The n-dimensional Hilbert space will have n **basis**, so that the state vector can be represented as:

$$
\braket{\alpha} = a_1 \ket{\alpha_1} + a_2 \ket{\alpha_2} + . . . + a_n \ket{\alpha_n}
$$

While the state vector itself is basis-independent, the values of its components $\{a_i \}$ will depend on the choice of basis.

>**example** An electron spin (up and down) system is a two-dimensional Hilbert space with the two basis being “up” and “down”, so that a general element in the Hilbert space can be represented as $\ket{\alpha} = c_+ \ket{+} + c_- \ket{-}$ 

##### basis sets
A **basis** provides a way to write down quantum states in a defined matter. For e.g. a quantum coin has two outcomes (heads and tails) so the state of the quantum coin can be represented in the basis $\{\ket{H} , \ket{T} \}$, where the state is represented as the linear combination of the basis $\psi = a \ket{H} + b \ket{T}$. ^563fc4

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
#### Operators
state vectors are modified by linear operators that act upon them and that determine their physical properties

**observables =** a mathematical transformation between two elements of a given Hilbert space and are represented by operators

The *expectation value* associated to a measurement of the physical observable given a quantum state is: 
$$
\braket{O}   = \braket{\psi | \hat{O} \psi}
$$
Given that the outcome of any measurement is a real quantity, the expectation value is real for any operator in any given quantum state. In other words, operators representing physical observables must satisfy 
$$
\braket{O} = <O>^*
$$
$$
\braket{\psi | \hat{O} \psi} = \braket{\hat{O} \psi | \psi}
$$
these operators are called **Hermitian operators** which are by definition equal to their conjugate

- Hermitian operators have associated real eigenvalues
- The eigenvectors $\ket{\psi_1}$ and $\ket{\psi_2}$ associated to different eigenvalues ($\lambda_1 \neq \lambda_2$) are orthogonal
- The eigenvectors of a Hermitian operator span the complete Hilbert space and so represent a complete basis in the Hilbert space

The Heisenberg uncertainty principle is the consequence of the axiom that all physical observables in quantum physics are represented by Hermitian operators

#### Eigenvalue equations
**Eigenvalue equations =**  $A\vec{v} = \lambda \vec{v}$ where
- $A$ represents a square matrix of dimensions $n \times n$
- $\vec{v}$ is a column bector with dimensions n
- $\lambda$ is the **eigenvalue** of the equation and $\vec{v}$ is the **eigenvector**

To find the eigenvalues =
1. Find the _characteristic equation of the matrix A_
$$
Det (A - \lambda \cdot I ) = 0
$$
Where $I$ is the identity matrix and _det_ is the determinant. This gives the eigenvalues $\lambda$
2. Find the eigenvectors by solving $Av_i = \lambda v_i$

![[Pasted image 20251213175104.png]]
#### Position representation
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
#### momentum representation
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

