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
**general solution strategy** =
1. set up rotating coordinates basis
	- pick unit vectors fixed to the rotating frame (e.g. local east, North, up on the Earth's surface) and express $\ohm$ in that basis
2. write down all forces acting, real + fictious
3. identify the small parameter
	- if $\ohm$ is small compared to other rates in the problem, treat $\ohm$ as a perturbation parameter and expand the solution as a series: $$r(t) = r^{(0)}(t) + r^{(1)}(t) + r^{(2)}(t)+ \dots $$
	where $r^{(n)}$ collects all terms of order $\ohm^n$ 
4. solve by order
	- *zeroth order* ($\ohm \rightarrow 0$) = drop all fictious terms and solve $ma = F$ with the initial conditions $r(0), \dot{r}(0)$ 
	- *first order* (terms linear in $\ohm$ i.e. Coriolis) = plug $\dot{r}^{(0)}(t)$ from the zeroth order into the Coriolis term. To find the position and velocity integrate $$ma^{(1)} \approx -2m\ohm \times \dot{r^{(0)}}(t)$$
	- *second order* (centrifugal) = plug $r^{(0)}$ into the centrifugal term

**Example** = You drop a ball from height h above the Earth's surface. Because the Earth is rotating, the reference frame you're standing in (fixed to the Earth's surface with $\hat{x}$ = East, $\hat{y}$ = North, $\hat{z}$ = Up) is a non-inertial frame. 