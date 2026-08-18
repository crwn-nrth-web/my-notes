---
title: Separation-of-variables
draft: false
tags:
  - math
---
 https://web2.ph.utexas.edu/~vadim/Classes/2024f-emt/sep.pdf

The basic idea of separation of variables is to turn one [[partial-differential-equations]] into multiple ordinary differential equations.

The coordinate system we use changes the separated differential ordinary conditions, leading to different eigenfunctions =
- [[#Cartesian coordinates]] → sine/cosine functions
- cylindrical coordinates → Bessel functions
- spherical coordinates → Legendre functions
### Cartesian coordinates
Suppose for the heat equation:
$$\frac{\partial u}{\partial t} = \alpha \frac{\partial^2 u}{\partial x^2}$$
we let $$u(x,t) = X(x)T(t)$$
so, $$\begin{align}
\frac{\partial (XT)}{\partial t} = \alpha \frac{\partial^2 (XT)}{\partial x^2}  \\
XT' = \alpha X''T  \\
\text{Dividing by } \alpha XT: \text{ } \frac{T'}{\alpha T} = \frac{X''}{X} 
\end{align}$$
This gives us a function of t = function of x

Introducing the separation constant, $\frac{T'}{\alpha T} = \frac{X''}{X} = - \lambda$ gives us two differential equations 

$$X'' + \lambda X=0 \tag{1.1}$$
$$T' + \alpha \lambda T = 0 \tag{1.2}$$
*Imposing Boundary conditions*: The boundary conditions determine $\lambda$ (eigenvalues)

When $\lambda > 0$: the general solution of eq $\ref{eq:1.1}$ is $X = A\cos(kx) + B\sin (kx)$

Supposing Dirichlet boundary conditions $u(0,t) = u(L, t) = 0$ i.e. $X(0) = X(L) = 0$ gives the eigenvalue and eigenfunctions as 

$$\boxed{\begin{align}
\lambda_{n} = \left( \frac{n\pi}{L} \right)^2  \\
X_{n} = \sin\left( \frac{n\pi x}{L} \right)
\end{align}}$$

Once we determine the eigenvalue from one of the equation (usually the one with the Strum-Liouville form), we can substitute that into the second equation to find eigenfunctions of T

General solution of eq $\ref{eq:1.2}$ is $T = Ce^{-\alpha \lambda t}$

So, 
$$u_{n}(x,t) = \sum_{n=1}^{\infty} C_{n}e^{-\alpha (n\pi x/L)^2t} \sin\left( \frac{n\pi x}{L} \right)$$
To find the coefficient for the time equation, we need the initial condition, such as $u(x,0) = f(x)$

This would give us 
$$f(x) = \sum C_{n} \sin\left( \frac{n\pi x}{L} \right)$$
Since this is the Fourier sine series,$$C_{n} = \frac{2}{L} \int_{0}^L f(x) \sin\left( \frac{n\pi x}{L} \right)$$
### Cylindrical coordinates
The cylindrical Laplacian
$$\nabla^2 u = \frac{1}{r} \frac{\partial}{\partial r} \left( r \frac{\partial u}{\partial r} \right) + \frac{1}{r^2} \frac{\partial^2 u}{\partial \theta^2}+ \frac{\partial^2 u}{\partial z^2} = 0$$
Separating variables $u = R(r) \Theta(\theta)Z(z)$


### Spherical coordinates
The spherical Laplacian
$$\nabla ^2 u = \frac{1}{r^2} \frac{\partial}{\partial r} \left( r^2 \frac{\partial u}{\partial r} \right) + \frac{1}{r^2 \sin \theta} \frac{\partial}{ \partial \theta}  \left( \sin \theta \frac{\partial u}{\partial \theta} \right) + \frac{1}{r^2 \sin^2 \theta} \frac{\partial^2 u}{\partial \phi^2} = 0$$
Separating variables $u = R(r) \Theta(\theta)\Phi (\phi)$

$$\frac{\Phi''}{\phi} = -m^2 \tag{3.1}$$
$$\frac{1}{R} \frac{\partial}{\partial r} (r^2 R') = k \tag{3.2}$$
$$\frac{\partial}{\partial \mu} \left[ (1- \mu^2) \frac{\partial \Theta}{\partial \theta} \right] - \frac{m^2}{1-\mu^2} \Theta+ k \Theta = 0 \tag{3.3}$$
where $\mu = \cos \theta$
#### Azimuthal equation $\ref{eq:3.1}$ 
Because of the periodicity condition $\Phi(\phi+2\pi) = \Phi(\phi)$, the solution is 
$$\boxed{\Phi(\phi) = e^{im \phi}}$$
#### Polar equation $\ref{eq:3.3}$ 

Eq $\ref{eq:3.3}$ the associated Legendre polynomial

*Case of azimuthal symmetry:* setting the rotational symmetry about the polar axis, means that $\Phi(\phi)$ is constant (i.e. $\Phi$ is independent of $\phi$)  → m = 0

Eq $\ref{eq:3.3}$ becomes
$$\frac{\partial}{\partial \mu} \left[ (1- \mu^2) \frac{\partial \Theta}{\partial \theta} \right] + k \Theta = 0$$
$$(1-\mu^2)\Theta''  - 2\mu \Theta + k \Theta = 0$$
This matches the standard Legendre equation $\ref{eq:1^{1}}$ : $(1-x^2)y'' -2xy' +l(l+1)y=0$

Hence, the eigenvalues and eigenfunction for $\Theta(\theta)$ when m=0 : 
$$\boxed{\begin{align}
k_{l} = l(l+1) \qquad l=0, 1, 2, \dots \\
\Theta_{l} = P_{l}(\cos \theta) \qquad \qquad \qquad \quad \\

\end{align}}$$
where $P_{l}$ are the Legendre polynomials

#### Angular equation $\ref{eq:3.2}$ + $\ref{eq:3.3}$ 

The complete angular solution is $\Theta(\theta)\Phi(\phi)$

So we define the **spherical harmonic** as
$$Y_{l}^m (\theta,\phi)=N_{lm} P_{l}^m(\cos \theta)e^{im\phi}$$
where 
- $m = 0, \pm 1, \pm 2, . . .$ 
- $l = 0,1,2, \dots$  
- $|m| \leq l$ 
so, for each $l$, there are $2l+1$ possible values of m


[^1]: [[Legendre-polynomials.md]]
