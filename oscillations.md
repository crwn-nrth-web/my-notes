---
title: oscillations
draft: false
tags:
  -
---
**resonance** = timing such that the energy you put in a system adds to the total energy

**parametric resonance** = phenomena where a system's vibration grows exponentially. This happens when a system parameter (spring constant or length) changes periodically.
- the driving frequency must be twice the system's natural frequency

### Kapitsa's Pendulum
vertical oscillations of the pivot of a pendulum can lead to **parametric resonance** (by effectively modulating "g")

Resonance occurs when the modulation frequency is twice the natural frequency of the pendulum

### Spring pendulum
Consider a pendulum where the string is replaced by an ideal spring with equilibrium length l and spring constant k. A mass is attached to the end of the spring.

Using x and $\theta$ as generalized coordinates, the position of the mass is given by:
- $X = (l+x) \sin \theta$
- $Y = -(l+x) \cos \theta$

$$\mathcal{L} = \frac{1}{2}m [\dot{x} + (l+x)^2 \dot{\theta}^2] + mg(l+x)\cos \theta -\frac{1}{2}kx$$

**auto parametric resonance** occurs as there is no control to the change in system parameter (in this case length).
