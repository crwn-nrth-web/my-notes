---
title: conserved-quantities
draft: false
tags:
  - physics
---
Three methods =
### Cyclic coordinates
A generalized coordinate is **cyclic** if it does not appear explicitly in the [[Lagrangian-and-Hamiltonian-mechanics|Lagrangian]]: $$\frac{\partial \mathcal{L}}{\partial q_{i}} = 0$$
When the generalized coordinate is cyclic, the corresponding conjugate momentum $p_{k} = \frac{\partial \mathcal{L}}{\partial \dot{q_{i}}}$ is conserved

### Noether's theorem
- Identify a continuous transformation that leaves the physics unchanged $$q_{i} \rightarrow q_{i} + \epsilon K_{i}$$
- Check whether $\mathcal{L}$ remains unchanged
- if so, compute the conserved quantity $$Q = \sum_{i} p_{i}K_{i}$$

 ![[Lagrangian-and-Hamiltonian-mechanics#Noether's theorem]]
### Poisson Brackets
![[Lagrangian-and-Hamiltonian-mechanics#Poisson Brackets]]

For a quantity $f$ that has no time dependence $\{f, \mathcal{H} \} = 0$

Consider angular momentum for a central potential,
$$\mathcal{H} = \frac{p^2_{r}}{2m} + \frac{p^2_{\theta}}{2mr^2} + V(r)$$
$$\{ p_{\theta}, \mathcal{H} \} = (0) (\frac{p_{\theta}}{mr^2}) - (1)(0) =0$$
Hence, $p_{\theta}$ is conserved