---
title: non-inertial-reference-frame
draft: false
tags:
  - physics
---
Newton's second law $F = ma$ is only valid in an *inertial reference frame* (one that isn't accelerating or rotating). 

In order to use Newton's second law in a *non-inertial reference frame*, correction terms are required called **fictious forces** (these are forces that are not caused by any physical interaction).

For a frame that translates with acceleration $A$ and rotates with angular velocity $\ohm$ relative to an inertial frame, 

the equation of motion for a particle as measured in the non inertial frame is:
$$ma_{r} = F -mA - m\ohm \times (\ohm \times r) - 2m(\ohm\times\dot{r})-m(\dot{\ohm} \times r)$$
where F is the real force (gravity, external forces, tension, normal force, etc.)

| fictious force          |                                  | when it matters                                       |
| ----------------------- | -------------------------------- | ----------------------------------------------------- |
| translational force     | $-mA$                            | frame's origin accelerating                           |
| centrifugal force       | $- m\ohm \times (\ohm \times r)$ | particle has non zero position $r$ from rotation axis |
| coriolis force          | $- 2m(\ohm\times\dot{r})$        | particle is moving within rotating frame              |
| azimuthal (Euler) force | $-m(\dot{\ohm} \times r$         | rotation rate is changing                             |
In cases (like Earth's rotation) $A=0$ and $\dot{\ohm} = 0$ (constant rotation rate), the equation is reduced to
$$F_{r} = F - m\ohm \times (\ohm \times r) - 2m(\ohm\times\dot{r})$$
