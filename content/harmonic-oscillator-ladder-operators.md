---
title: harmonic-oscillator-ladder-operators
draft: false
tags:
  - physics
aliases:
  - ladder-operators
---
**Ladder operators**  are operators that raise or lower the eigenvalues of an observable. They are used to transform the [[schrodinger-equation-solutions#CASE 2 Harmonic oscillator|Harmonic oscillator]] state wave function into a lower or higher energy state
- $a_+$ = *raising operator*
- $a_-$ = *lowering operator*
$$
a_{\pm} = \frac{1}{\sqrt{ 2 \hbar m \omega }} (\mp i \hat{p} + m \omega \hat{x})
$$
$$
a_{+} a_{-} = \frac{1}{\hbar \omega} \mathbb{H} - \frac{1}{2} \ \ , \ \ \mathbb{H} = \hbar \omega \left( a_{+} a_{-} + \frac{1}{2} \right)
$$
The ladder operators do not commute =
$$
[\hat{a_{-}} , \hat{a_{+}}] = a_{-} a_{+} - a_{+} a_{-} = 1
$$
Note that the position operator and momentum operator can be rewritten in terms of the ladder operators =
$$
\hat{X} = \sqrt{ \frac{\hbar}{2m \omega} } (a_{+} + a_{-})
$$
$$
\hat{P} = i \sqrt{ \frac{\hbar m \omega}{2} }(a_{+} - a_{-})
$$

**Number operator**
$$
N = a_{+} a_{-}
$$
such that 
$$
N \psi_{n} (x) = a_{+} a_{-} \psi_{n}(x) = n \psi_{n}  (x)
$$
#### Action on number states
$$a_{-} \ket{n} = \sqrt{ n } \ket{n-1}$$
$$a_{+} \ket{n} = \sqrt{ n+1 } \ket{n+1} $$
#### expectation values
$$\braket{ n |a_{-} |n  } = 0 \text{ , } \braket{ n |a_{+}|n  } = 0  $$
This is because for expectation value of the lowering operator the two states ($\ket{n}$ and $\ket{n-1}$) are orthogonal since they have different eigenvalues ($E_{n} \neq E_{n-1}$)

**expectation value of the number operator** $\braket{ n|a_{+} a_{-} |n  }=n$





