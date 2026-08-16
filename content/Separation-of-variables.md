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

$$\begin{align}
X'' + \lambda X=0 \tag{1}\\
T' + \alpha \lambda T = 0 \tag{2}
\end{align}$$
*Imposing Boundary conditions*: The boundary conditions determine $\lambda$ (eigenvalues)

When $\lambda > 0$: the general solution of eq (1) is $X = A\cos(kx) + B\sin (kx)$

Supposing Dirichlet boundary conditions $u(0,t) = u(L, t) = 0$ i.e. $X(0) = X(L) = 0$ gives the eigenvalue and eigenfunctions as 

$$\begin{align}
\lambda_{n} = \left( \frac{n\pi}{L} \right)^2  \\
X_{n} = \sin\left( \frac{n\pi x}{L} \right)
\end{align}$$

Once we determine the eigenvalue from one of the equation (usually the one with the Strum-Liouville form), we can substitute that into the second equation to find eigenfunctions of T

General solution of eq (2) is $T = Ce^{-\alpha \lambda t}$

So, 
$$u_{n}(x,t) = \sum_{n=1}^{\infty} C_{n}e^{-\alpha (n\pi x/L)^2t} \sin\left( \frac{n\pi x}{L} \right)$$
To find the coefficient for the time equation, we need the initial condition, such as $u(x,0) = f(x)$

This would give us 
$$f(x) = \sum C_{n} \sin\left( \frac{n\pi x}{L} \right)$$
Since this is the Fourier sine series,$$C_{n} = \frac{2}{L} \int_{0}^L f(x) \sin\left( \frac{n\pi x}{L} \right)$$








