---
title: Legendre-polynomials
draft: false
tags:
  - math
---
Standard Legendre equation
$$(1-x^2)y'' -2xy' +l(l+1)y=0 \tag{1}$$
Legendre polynomials are the special solutions to the Legendre equation

First few polynomials are:




Note that $P_{l}$ is always a polynomial of degree $l$

**Rodriguez's formula** can be used to generate Legendre polynomials
$$P_{l}(x) = \frac{1}{2^l l!} \frac{d^l}{dx^l}(x^2-1)^l$$
**Parity relation** $$P_{l}(-x) = (-1)^l P_{l}(x)$$
**Recursion relation**
$$P_{l+1} = \frac{2l+1}{l+1}xP_{l}(x) - \frac{l}{l+1}P_{l-1}$$
#### Orthogonality of Legendre Polynomials
The Legendre Polynomials are orthogonal on $[-1,1]$
$$\int_{-1}^1 P_{l}(x) P_{l'}(x) dx = \frac{2}{2l+1} δ_{ll'}$$
when $l \neq l'$
$$\int_{-1}^1 P_{l}(x) P_{l'}(x) dx =0$$

#### Generating function and Recursion relations
The generating function of the Legendre polynomial is 
$$G(x,t) = \frac{1}{\sqrt{ 1-2xt +t^2 }}$$
and it is defined such that $$G(x,t) = \sum_{l=0}^\infty P_{l}(x)t^l$$
Expanding in powers of t gives the Legendre polynomials: $$\frac{1}{\sqrt{ 1-2xt +t^2 }} =P_{0} + P_{1}t + P_{2}t^2 + \dots$$

