---
title: Equations-of-motions
draft: false
tags:
  - physics
---
One of the fundamental concepts of mechanics is a **particle**, which is a body whose dimension can be neglected in describing its motion. 

The number of independent quantities which must be specified in order to uniquely define the position of any system is called the number of **degrees of freedom.** 

Any $n$ quantities $q_{1}, q_{2}, \dots$ which completely define the position of the system with $n$ degree of freedom are called the **generalized** coordinates of the systems, and the derivates are called the **generalized velocities**.

The relations between the accelerations, velocities and coordinates are called the *equations of motions*. They are second order differential equations and their integration, in principle, determines the path of the system 

A **monogenic** system is if all the forces acting on it (except the constraint forces) can be derived from a single generalized scalar potential.

For a monogenic system, the **Lagrangian** can be defined as:
$$\boxed{\mathcal{L} = T(q_{i}, \dot{q_{i}}, t) - V(q_{i}, \dot{q_{i}}, t)}$$
with initial conditions $q_i(t_1)$ and $q_i(t_2)$ 
### Hamilton's Principle (the Principle of least action)
This is the most general formulation of the law governing the motion of mechanical systems is the *principle of least action* or *Hamilton's principle*. The mechanical system is characterized by a definite function $\mathcal{L}(q_{i}, \dot{q}_{i}, t)$ where $\mathcal{L}$ is the *Lagrangian*. 

The path of a particle between two points A and B in a given time interval from $t_1$ to $t_2$ will take the least possible value: $$S = \int_{t_{1}}^{t_{2}} \mathcal{L}(q_{i}, \dot{q_{i}}, t) dt$$
where the integral is called the *action*.

The requirement that the action integral must be stationary implies the [[Lagrangian-mechanics|Euler-Lagrangian-equation]]:
$$\boxed{\frac{\partial{\mathcal{L}}}{\partial q} - \frac{d}{dt} \left(\frac{\partial{\mathcal{L}}}{\partial \dot{q}}\right) = 0}$$
Solving this partial differential equation gives the **equations of motions** in order to find how the coordinates vary with time. 

It can be seen that the [[Lagrangian-mechanics|Euler-Lagrangian-equation]] is simply the [[calculus-of-variations|Euler-equation]] with time as the independent variable and the coordinates that specify the position as the dependent variable. 


