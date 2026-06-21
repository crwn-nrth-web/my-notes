---
title: calculus-of-variations
draft: false
tags:
  - physics
  - math
aliases:
  - euler-equations
---
## Minimizing integral functions
In order to find a function $y(x)$ that extremizes the value of integral functional:
$$J = \int_{x_{1}}^{x_{2}} f(y, y', x) \ dx$$
we can use the **Euler equation**:
$$\boxed{\frac{\partial f}{\partial y} - \frac{d}{dx}\left( \frac{\partial f}{\partial y'} \right)=0}$$
**Second Euler equation** (or Beltrami's identity):
To find a function $y(x)$ that extremizes $J$ where $f = f(y, y')$ i.e. the function does not explicitly depend on x. 
$$\boxed{f - y' \frac{\partial f}{\partial y'} = constant}$$
### Geodesics (shortest path between two points)
The length of the path is given by 
$$J = \int_{A}^{B} ds =  \int_{A}^{B} \sqrt{dx^2 + dy^2 + dz^2}$$
For a planar surface (cartesian coordinates),
$$J =  \int_{A}^{B} \sqrt{ 1 + y'^2 } \ dx^2$$
For a spherical surface (spherical coordinates),
$$J = \int_{A}^B R \sqrt{ d \theta^2 + \sin^2 \theta \ d \phi^2 }$$
For a cylindrical surface (cylindrical coordinates)
$$J = \int_{A}^B \sqrt{ R^2 d \theta^2 + dz^2 }$$
### Brachistochrone problem (shortest time between two points)
Finding the path which minimizes the time taken between two points
$$t = \int dt = \int \frac{ds}{v}$$
$$t = \int_{A}^B \frac{\sqrt{ 1 + y'^2 }}{\sqrt{ 2gy }} \ dx$$
Solving using the second Euler equation,
$$1 + y'^2 = \frac{k^2}{y}$$
The solution to this second order differential equation is the *cycloid function*
$$\begin{aligned}
x = \frac{k^2}{2} (\theta - \sin \theta) + c \\
y = \frac{k^2}{2} (1 - \cos \theta)
\end{aligned}$$
Substituting this into the equation for time,
$$\begin{aligned}
t = \frac{1}{\sqrt{ 2g }} \int_{0}^{\theta_{B}} \frac{\sqrt{ 1 + \cot^2 \frac{\theta}{2} }}{\frac{k^2}{2}(1-\cos \theta)} \frac{k^2}{2}(1-\cos \theta) \ d\theta \\
\boxed{t= \frac{k}{\sqrt{ 2g }} \theta_{B}} \rightarrow \boxed{\theta_{B} = \frac{\sqrt{ 2g }}{k} t = wt}
\end{aligned}$$
where $k = \frac{1}{2gc^2}$
### Tautochrone Problem
Finding the path where a particle starting from rest takes the same amount to time to travel no matter where it starts
$$t = \int_{A}^B \frac{\sqrt{ 1 + y'^2 }}{\sqrt{ 2g(y-y_{A}) }} \ dx$$
$$\begin{aligned}
t = \frac{1}{\sqrt{ 2g }} \int_{0}^{\theta_{B}} \frac{\sqrt{ 1 + \cot^2 \frac{\theta}{2} }}{(1-\cos \theta - 1 + \cos \theta_{A})} (1-\cos \theta) \ d\theta \\
\boxed{t= \frac{\pi k}{\sqrt{2g }}}
\end{aligned}$$