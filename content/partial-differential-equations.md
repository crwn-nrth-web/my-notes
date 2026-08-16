---
title: partial-differential-equations
draft: false
tags:
  - physics
  - math
---
A **partial differential equation** involves a function of multiple variables and its partial derivates

A two-variable second order PDE:
$$Au_{xx} + Bu_{xy} + Cu_{yy} + . . . = 0$$ For example, for $u= u(x,t)$, the heat equation is $$\frac{\partial u}{\partial t} = \alpha \frac{\partial^2 u}{\partial x^2}$$
[[Separation-of-variables]] is a method to easily solve partial differential equation.
#### Initial and Boundary conditions
Suppose we are solving a PDE on an interval $0 \leq x\leq L$. 

The initial conditions specifies what is happening at a particular time (e.g. $t=0$), while boundary conditions specifies what is happening at the spatial boundaries (e.g. at $x=0$ and $x=L$).

*Types of boundary conditions*
1. **Dirichlet conditions**: fixes the actual value of the boundary $u=c$
2. **Neumann conditions** fixes the flux, slope or normal derivate at the boundary $\frac{\partial u}{\partial x} = g$
3. **Periodic conditions**: the value and derivate on one boundary equal the value and derivate on the other boundary $u(x_{start}) = u(x_{final})$ and $u'(x_{start}) = u'(x_{final})$

E.g. For heat transfer, a Dirichlet boundary condition means setting a wall to a constant fixed temperature, while a Neumann boundary condition means setting a specific heat flux or making the wall perfectly insulated.

It is possible to have a Dirichlet condition at one boundary and a Neumann condition at the other. 
#### Classification of second order partial differential equations (PDEs)

| PDE type   | physical idea                                 | example                               | characteristics                                              | typical information                    |
| ---------- | --------------------------------------------- | ------------------------------------- | ------------------------------------------------------------ | -------------------------------------- |
| Elliptic   | describes steady-state or equilibrium states  | Laplace equation $\nabla^2 u = 0$     | contains no time derivate                                    | Boundary conditions                    |
| Parabolic  | describes diffusion or evolutionary processes | Heat equation $u_{t} = \alpha u_{xx}$ | contains first derivate in time and second derivate in space | Initial + boundary                     |
| Hyperbolic | describes wave or transport phenomena         | wave equation $u_{tt} = c^2 u_{xx}$   |  contains second derivate in time                            | Initial position + velocity + boundary |
# Strum Liouville Problem
This is a particular type of eigenvalue problem for a differential equation.

Standard form =
$$\frac{d}{dx}\left[ f(x) \frac{dy}{dx} \right] + g(x)y + \lambda w(x)y = 0$$
where 
- f(x), g(x) and w(x) are given
- w(x) = weight function
- $\lambda$: eigenvalues, and $y(x)$: corresponding eigenfunctions

The boundary conditions determine the eigenfunctions allowed

| boundary condition                         | eigenfunction                                 |
| ------------------------------------------ | --------------------------------------------- |
| Dirichlet $X(0)=X(L)=0$                    | $X_{n} = \sin\left( \frac{n\pi x}{L} \right)$ |
| Neumann  $X'(0)=X'(L)=0$                   | $X_{n} = \cos\left( \frac{n\pi x}{L} \right)$ |
| Periodic $X(0) = X(L)$ and $X'(0) = X'(L)$ | $X_{n} = e^{-\frac{2n\pi x}{L}}$              |

**Strum Liouville eigenfunction orthogonality**
For two eigenfunctions ($y_n(x)$ and $y_{m}(x)$) corresponding to two different eigenvalues, 
$$\int_{a}^{b} w(x) y_{m}(x) y_{n}(x) dx = 0$$
When $w(x) =1$:
$$\int_{a}^{b} y_{m}(x) y_{n}(x) dx = 0$$
