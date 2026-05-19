---
title: python-for-physics
draft: false
tags:
  - math
  - python
---
## Integration and Ordinary Differential Equations (ODE)
using `scipy.integrate`

**Solving initial value problems for ODE systems** = `solve_ivp(fun, t_span, y0, t_eval=None, dense_output=False, events=None, vectorized=False, args=None)`
- this numerically integrate a system of ordinary differential equations given an initial value: 
$$\begin{align}
\frac{dy}{dt} = f(t,y) \\
y(t_{0}) = y_{0}
\end{align}$$
- function: `fun(t,y)` where t is a scalar and y is ndarray
- limits of integration: `t_span`
- initial condition: `y0`
- times to store the computed solution within `t_span` : `t_eval`
	- If None (default), use points selected by solver
- *returns* = `t, y` = timepoints, values of solution at t

## Phase Portraits
A phase portrait is a special case of a parametric plot that displays a set of phase space trajectories, typically velocity (or momentum) vs. position as a function of time for different initial conditions.

