---
title: fourier-series
draft: false
tags:
  -
---
A Fourier series is a way to break up a periodic function into a series representation of sines and cosines, i.e. into discrete frequencies.

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
### Cosine and Sine Fourier series

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
### Convergence of a Fourier series
Suppose $f(x)$ is piecewise smooth on the interval $-L \leq x \leq L$. The Fourier series
- converges to $f(x)$ at all points at which f is continuous
- converges to the average value of the right and left limits $\frac{1}{2} [f(+x) + f(-x)]$ at a point of discontinuity 

**Gibbs Phenomena** = Near points of discontinuity, the Fourier series exhibits overshoots

# Fourier Transform
While a Fourier series represents a function as a sum of sines and cosines, the Fourier transform represents it using a continuous range of frequencies. In other words, the Fourier transform is the Fourier series when the period $L \to 0$

Forward transform:
$$\mathcal{F}\{f \} := \tilde{f}(k) = \frac{1}{\sqrt{ 2\pi }} \int_{-\infty}^\infty f(x)e^{-ikx}dx$$
Inverse transform:
$$f(x) = \frac{1}{\sqrt{ 2\pi }} \int_{-\infty}^\infty \tilde{f}(k) e^{ikx}dx$$
Transform of a derivate for a localized function (i.e. $f \to 0$ as $x \to \pm \infty$)
$$\begin{align}
\mathcal{F}\{ f'\} = ik \tilde{f}(k) \\
\mathcal{F}\{ f''\} = -k^2 \tilde{f}(k) \\
\mathcal{F}\{ f^{(n)}\} = (ik)^n \tilde{f}(k)
\end{align}$$
### Parseval's theorem
$$|f(x)|^2 = \int_{- \infty}^\infty |\tilde{f}(k)|^2 dx$$
the total content in real space = total content in Fourier space

This is useful to calculate the probability or energy density of a function using its Fourier transform

### convolution
$$(f \times g)(x) = \int_{- \infty}^\infty f(x') g(x - x') dx$$
This considers how much does g overlap with h, and adds up all these overlaps.

The Fourier transform of a convolution =
$$\mathcal{F}\{ f \times g\} = \tilde{f}(k) \tilde{g}(k)$$
### cosine and sine Fourier transform
For an even function: **cosine transform**
$$\mathcal{F}_{c}(k) = \sqrt{ \frac{2}{\pi}} \int_{0}^\infty f(x) \cos kx \ dx$$
For an odd function: **sine transform**
$$\mathcal{F}_{s}(k) = \sqrt{ \frac{2}{\pi}} \int_{0}^\infty f(x) \sin kx \ dx$$
where $\tilde{f}(k) = -i \mathcal{F}_{s} (k)$

