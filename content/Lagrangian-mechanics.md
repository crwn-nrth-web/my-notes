---
title: Lagrangian-mechanics
draft: false
tags:
  - physics
aliases:
  - Euler-Lagrangian-equation
---
[The Lagrangian Method, Morin](https://www.ipcms.fr/uploads/2021/06/chap6.pdf)

the **Lagrangian** can be defined for a monogenic system as:
$$\boxed{\mathcal{L} = T(q_{i}, \dot{q_{i}}, t) - V(q_{i}, \dot{q_{i}}, t)}$$
with initial conditions $q_i(t_1)$ and $q_i(t_2)$ 

The equation of motion of the system is given by the **Euler-Lagrange Equation:**
$$\boxed{\frac{\partial{\mathcal{L}}}{\partial q} - \frac{d}{dt} \left(\frac{\partial{\mathcal{L}}}{\partial \dot{q}}\right) = 0}$$
**cyclic coordinates** = when the Lagrangian doesn't depend on coordinate $q_i$ then $q_{i}$ is a cyclic coordinate

$$\frac{d}{dt} \frac{\partial \mathcal{L}}{\partial \dot{q_{i}}} = 0 , \frac{\partial \mathcal{L}}{\partial \dot{q_{i}}} = c$$

The canonical momentum conjugate of $q_i$ is conserved $$\frac{\partial \mathcal{L}}{\partial \dot{q_{i}}} = p_{i}$$
**Time independent Lagrangian** means that the system's properties and constraints do not change wit time
- in this case, the hamiltonian is a conserved quantity and is equal to the total energy of the system

##### Noether's theorem
According to Noether's theorem, for every continuous symmetry in a physical system, there exists a conservation law.

$$Q = \sum_{i} p_{i} δq_{i} - F$$

In physics, **symmetry** of a physical system is any transformation that leaves a system physically unchanged and is mathematically defined as a transformation that only changes the Lagrangian up to a total time derivative. 

i.e.
$$δ \mathcal{L} = \frac{dF}{dt}$$

| conservation law                 | symmetry                     |
| -------------------------------- | ---------------------------- |
| conservation of linear momentum  | spatial translation symmetry |
| conservation of angular momentum | rotational symmetry          |
| conservation of energy           | time translation symmetry    |

Noether’s theorem can be naturally described using Lagrangian mechanics.

## Equilibrium analysis

In general, to find equilibrium points, set $q = q_{0}$ and $\dot{q} = \ddot{q} = 0$

By setting $\ddot{q} = 0$ in the equation of motion, we see that each equilibrium point must be a stationary point of the potential energy i.e. $V'(q_{0}) = 0$
- **Stable equilibrium point** = objects returns to its original position after a small push and $$\frac{d^2 V}{dx^2} > 0$$
- **Unstable equilibrium point** = object moves increasingly further away from its original position after a small push and $$\frac{d^2 V}{dx^2} < 0$$
#### Phase portrait
A phase portrait plots $q$ vs $\dot{q}$, so each point corresponds to the mechanism of being in a certain configuration and moving at a certain rate.

[[python-for-physics#Phase Portraits|Plotting Phase portraits in python]]