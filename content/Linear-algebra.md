---
title: Linear-algebra
draft: false
tags:
  - math
---
 [[matrices]]
 [[tensor-product]]
 
#### Vector space
A **vector space** consists of a set of vectors $\{\ket{\alpha},\ket{\beta}, \ket{\gamma}, . . .  \}$ and scalars $\{a, b, c, . . . \}$

- **linear combination** = $a \ket{\alpha}+ b \ket{\beta} + c \ket{\gamma} + . . .$
- A vector $\ket{\lambda}$ is said to be **linearly independent** if it cannot be written as a linear combination of the set of vectors
	- the unit vector $\hat{k}$ is linearly independent to the unit vectors $\hat{i}$ and $\hat{j}$, but any vector in the xy plane would be a linearly dependent on $\hat{i}$ and $\hat{j}$
- a collection of vectors **span** the space when every vector can be written as a linear combination of the set of vectors
- **basis** = a collection of linearly independent vectors that span the space
- **dimension** of the vector space = # of bases

#### inner product
The dot product of an n-dimensional vector space is called the **inner product**

**norm** = $||\alpha|| = \sqrt{ \braket{ \alpha | \alpha } }$
- **normalized** = $||\alpha||=1$
- **orthogonal** = $\braket{ \alpha | \beta }=0$
- **orthonormal set** = a collection of orthogonal normalized vectors $\braket{ \alpha_{i} |\alpha_{j}  } = \delta_{ij}$ where 
	- when $i=j \to \delta_{ij}=1$ 
	- when $i \neq j \to \delta_{ij}=0$ 

**Schwartz inequality** 
$$|\braket{ \alpha |\beta  } |^2 \leq \braket{ \alpha |\alpha  }\braket{ \beta |\beta  }  $$
**angle between two vectors** 
$$\cos \theta = \sqrt{ \frac{\braket{ \alpha |\beta  }\braket{ \beta |\alpha  }}{||\alpha|| ||\beta||} }$$
##### Gram-Schmidt Procedure
Given a set of linearly independent vectors $\{v_{1}, v_{2}, v_{3}, \dots \}$, the Gram-Schmidt produces an orthogonal basis  $\{u_{1}, u_{2}, u_{3}, \dots \}$, followed by an orthonormal basis  $\{e_{1}, e_{2}, e_{3}, \dots \}$

$$\begin{align}
\hat{e_{1}} = \frac{v_{1}}{\sqrt{ v_{1} \cdot v_{1} }} \\
\text{For } e_{2} : \vec{e_{2}} = v_{2} - \hat{e_{1}} (\hat{e_{1}} \cdot v_{2}) \\
\hat{e_{2}} = \frac{e_{2}}{\sqrt{ e_{2} \cdot e_{2} }} \\
\text{For } e_{3} : \vec{e_{3}} =v_{3} - \hat{e_{1}} (\hat{e_{1}} \cdot v_{3} ) - \hat{e_{2}} (\hat{e_{2}} \cdot v_{3}) \\
\hat{e_{3}} =  \frac{e_{3}}{\sqrt{ e_{3} \cdot e_{3} }}
\end{align}$$
So, general formula =
$$\vec{e_{n}} = v_{n} - \sum_{i<n} \hat{e_{i}} (\hat{e_{i} \cdot v_{n}}) , \hat{e_{n}} = \frac{\vec{e_{n}}}{\sqrt{ e_{n} \cdot e_{n} }}$$
