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

##### Example: pendulum
the equation of motion for the angle $\theta$ of a pendulum of length $l$ 
$$\ddot{\theta} = - \left( \frac{g}{l} \right) \sin{\theta}$$

```py
g = 9.8
l = 1

## define eq
## y_1 = y , y_2 = y'

def system(t,y):
    y1, y2 = y
    dy1dt = y2
    dy2dt = - (g/l) * np.sin(y1)
    return [dy1dt , dy2dt]

t_span = [0,10]
t_eval = np.linspace(0,10,100)

y0_1 = [0.1, 0] # y(0) = y0 , y'(o) = 0
sol_1 = solve_ivp(system, t_span, y0_1, t_eval=t_eval)

plt.plot(t_eval, sol_1.y[0], label = '0.1 rad/s')
plt.show()

```

## Phase Portraits
A phase portrait is a special case of a parametric plot that displays a set of phase space trajectories, typically velocity (or momentum) vs. position as a function of time for different initial conditions.

For any second order ODE $y'' = f(y, y')$, the two state variables are:
- x-axis: $y$ (position)
- y-axis: $y'$ (velocity)

Each curve on the phase portrait corresponds to a different initial condition $[y_{0}, y'_{0}]$ and the shape of the curve tells you the type of motion.
#### Plotting phase portraits in python
```py
def system(t, y): 
y1, y2 = y # y1 = position, y2 = velocity 
dy1dt = y2 
dy2dt = f(y1, y2) # replace with your specific ODE right hand side return [dy1dt, dy2dt] 

# initial conditions
initial_conditions = [ 
	[y1_0, y2_0], 
	] 

t_span = (0, 10)
t_eval = np.linspace(0, 10, 3000) 
fig, ax = plt.subplots(figsize=(10, 6)) 
for ic in initial_conditions: 
	sol = solve_ivp(system, t_span, ic, t_eval=t_eval)
	ax.plot(sol.y[0], sol.y[1]) 
```

##### Example: pendulum (continued)

```py
## defining the initial conditions to explore
harmonic = [0.1, 0.35, 0.6, 0.9]
anharmonic = [1.5, 2.0, 3]
rolling = [7, 8, 9]
t_roll = np.linspace(0,3,100)

fig, ax = plt.subplots(figsize=(12, 7))

for theta in harmonic:
    sol = solve_ivp(system, t_span, [theta, 0], t_eval=t_eval)
    ax.plot(sol.y[0], sol.y[1], color='blue')

for theta in anharmonic:
    sol = solve_ivp(system, t_span, [theta, 0], t_eval=t_eval)
    ax.plot(sol.y[0], sol.y[1], color='green')

for omega in rolling:
    for sign in [1, -1]:
        sol = solve_ivp(system, (0,6), [0, sign*omega], t_eval = t_roll)
        ax.plot(sol.y[0], sol.y[1], color='red')

ax.set_xlim(-np.pi - 0.3, np.pi + 0.3)

legend_elements= [
    mpatches.Patch(color='blue', label='harmonic'),
    mpatches.Patch(color='green', label='anharmonic'),
    mpatches.Patch(color='red', label='rolling')
]
ax.set_xlabel(r'$\theta$')
ax.set_ylabel(r'$\dot{\theta}$')
ax.set_title('Phase portrait')
```


