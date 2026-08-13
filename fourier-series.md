---
title: fourier-series
draft: false
tags:
  -
---
 To write the series representation of a function $f(x)$ on the interval $a \leq x \leq a+L$: $$f(x) = x_{0} + \sum_{n=1}^{\infty} \left[ \sigma_{n} \sin\left( \frac{2n\pi x}{L} \right) + x_{n} \cos\left( \frac{2n\pi x}{L} \right) \right]$$
 where the coefficients of the Fourier series are = $$\begin{align}
x_{0} = \frac{1}{L} \int_{a}^{a+L} f(x) dx  \\
\sigma_{n} = \frac{2}{L} \int_{a}^{a+L} f(x) \sin\left( \frac{2n\pi x}{L} \right) dx \\
x_{n} = \frac{2}{L} \int_{a}^{a+L} f(x) \cos\left( \frac{2n\pi x}{L} \right) dx
\end{align}$$
Writing sine and cosine functions in terms of exponentials
$$\sin(x) = \frac{e^{ix} - e^{-ix}}{2i} , \cos(x) = \frac{e^{ix} + e^{-ix}}{2}$$
gives us the **exponential Fourier series**
$$\begin{align}
f(x) = \sum_{n= -\infty}^{\infty} \epsilon_{n} e^{i \frac{2n\pi x}{L}}  \\
\epsilon_{n} = \frac{1}{L} \int_{a}^{a+L} f(x) e^{-i \frac{2n\pi x}{L}} dx 
\end{align}$$
## Cosine and Sine Fourier series

- *even function* $f(-x) = f(x)$ e.g. cos x
- *odd function* $f(-x) = f(x)$ e.g. sin x

If a function is even,
$$\int_{-L}^{L} f(x) dx = 2 \int_{0}^L f(x) dx$$
if a function is odd, 
$$\int_{-L}^{L} f(x) dx = 0$$

The series representation of an *even function* is the **cosine Fourier series**
$$f(x) = \sum_{n=1}^{\infty} x_{n} \cos\left( \frac{2n\pi x}{L} \right)$$
The series representation of an *odd function* is the **sine Fourier series**
$$f(x) = x_{0} + \sum_{n=1}^{\infty} \sigma_{n} \sin\left( \frac{2n\pi x}{L} \right)$$
A function defined on a half-interval $[0, L]$ can be extended to $[-L, L]$ as an even function or odd function: 
- The **even extension** is defined as $$f_{even}(x) = \begin{cases} f(x), &  0 \leq x \leq L \\
f(-x), & -L \leq x < 0
\end{cases}$$
- The **odd extension** is defined as $$f_{even}(x) = \begin{cases} f(x), &  0 \leq x \leq L \\
-f(-x), & -L \leq x < 0
\end{cases}$$
## Convergence of a Fourier series
Suppose $f(x)$ is piecewise smooth on the interval $-L \leq x \leq L$. The Fourier series
- converges to $f(x)$ at all points at which f is continuous
- converges to the average value of the right and left limits $\frac{1}{2} [f(+x) + f(-x)]$ at a point of discontinuity 

**Gibbs Phenomena** = Near points of discontinuity, the Fourier series exhibits overshoots