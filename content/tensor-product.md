---
title: tensor-product
draft: false
tags:
  - math
---
Intuitively, tensor products (also known as outer products) is a way of capturing all possible combinations of basis vectors.

![[Formalism-of-quantum-mechanics#^563fc4]]

A quantum die (with 6 basis vectors) and a quantum coin (with two basis vectors) can be considered to be 2 different vector spaces with its own set of basis vectors, so that the tensor product of the two would capture all the possible combinations

**Formal definition** = The tensor product $V \otimes W$ of two vector spaces V and W is a vector space, containing a bilinear map ($(v,w) \to v \otimes w$) from the cartesian product $V \times W$ to $V \otimes W$ 

any two vector spaces V and W can be combined with the tensor product to generate a new vector space $V \otimes W$ 

Consider two vectors:
$$a = \begin{bmatrix}
a_{1}  \\
a_{2}
\end{bmatrix} , b = \begin{bmatrix}
b_{1} \\
b_{2} \\
b_{3}
\end{bmatrix}$$
$$a \otimes b = \begin{bmatrix}
a_{1} (b) \\
a_{2} (b)
\end{bmatrix} = \begin{bmatrix}
a_{1} (\begin{bmatrix}
b_{1} \\
b_{2} \\
b_{3}
\end{bmatrix}) \\
a_{2} (\begin{bmatrix}
b_{1} \\
b_{2} \\
b_{3}
\end{bmatrix}) 
\end{bmatrix} = \begin{bmatrix}
a_{1} b_{1} \\
a_{1} b_{2} \\
a_{1} b_{3} \\
a_{2} b_{1} \\
a_{2} b_{2} \\
a_{3} b_{3}
\end{bmatrix} $$
##### applications in quantum theory
In [[Quantum Physics]], the combined system for n systems with individual quantum states =
$$\ket{\Phi}  = \ket{\psi_{0}} \otimes \ket{\psi_{1}} \otimes \ket{\psi_{2}} . . .   $$
