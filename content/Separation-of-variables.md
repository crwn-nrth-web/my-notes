---
title: Separation-of-variables
draft: false
tags:
  - math
---
 https://web2.ph.utexas.edu/~vadim/Classes/2024f-emt/sep.pdf
 
**Second order differential equation of the form** $x'' = - \lambda x$ 

let the exponential ansatz be $x(t) = e^{rt}$ 

The equation becomes $r^2 e^{rt} = - \lambda e^{rt}$ and the characteristic equation becomes $r^2 + \lambda = 0$

*Case 1*: $\lambda > 0$
$$\begin{align}
r^2 = - \lambda  \\
r = \pm i \sqrt{ \lambda }  
\end{align}$$
Using Euler's equation $e^{i \theta} = \cos{\theta} + i\sin{\theta}$, the general solution is a linear combination of sine and cosines:
$$\boxed{x(t) = A \cos{\lambda t} + B\sin{\lambda t}}$$

*Case 2:* $\lambda < 0$
define a positive constant $\mu = \sqrt{ - \lambda }$ so $\lambda = - \mu^2$
$$\begin{align}
r = \pm \mu = \pm \sqrt{ -\lambda }  
\end{align}$$

General solution:
$$\begin{aligned}
\text{exponential form: } \boxed{x(t) = C e^{\sqrt{ - \lambda }t} + De^{-\sqrt{ - \lambda }t}} \\
\text{hyperbolic form: } \boxed{x(t) = C \cosh{\sqrt{ - \lambda }t} + D\sinh{\sqrt{ - \lambda }t}}
\end{aligned}$$
