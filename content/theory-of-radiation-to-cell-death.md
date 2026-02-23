---
title: theory-of-radiation-to-cell-death
draft: false
tags:
  - biology
---
### Theory of Dual Radiation Action
Proposed by Keller and Rossi to explain how ionizing radiation causes biological damage and why different radiation have different biological effectiveness. It focuses on how lethal lesions arise

Biological damage can occur from radiation in two distinct ways:
1. **single-track (one-hit) action** = A single charged particle track passing through DNA can deposit enough energy in a very small region to cause complex, lethal damage.
2. **two-track (dual-hit) action** = two separate radiation tracks create sublethal lesions (small bits of radiation damage). If these lesions occur close together in space and time, they can can interact to form a lethal lesion

For a two-track action to result in a double-strand break, the two breaks need to occur in both strands directly opposite or separated by only a few base pairs

**Single-track action** is common with high LET radiation and so has linear effects in dose response curves. **Two-track action** is common with low LET radiation and so has both linear and quadratic effects in dose response curves.

### Molecular Theory of Cell Inactivation
Proposed by Chadwick and Leenhouts explains what lethal lesions are at the DNA level.

- cell inactivation (cell death) results from unrepaired DNA double-strand breaks (DSB)
	- DSBs are the most lethal form of DNA damage
	- if DSB is unrepaired = chromosome fragments
	- if DSB is mis repaired = wrong ends join = lethal chromosome aberration

ionizing radiation can induce DSBs on two separate strands and result in 4 possible results 
1. full repair
2. dicentric = mis-joining DNA strand 1 to DNA strand 2
3. incomplete = only one strands repair
4. symmetric translocation = mis-joining leading to exchange of segments

- At low LET, a DSB can result from either a single event (linear component) or two separate events (quadratic component)
	- A single event (single-track action) leads to clustered damage i.e. direct DSB
	- Two separate events lead to two independent SSBs close together that can combine to form DSB

In other words, cell inactivation results from chromosome aberration, which can be produced by a single event or two separate breaks, where the initiating lesion is the DSB and the chromosome aberration is the final lethal outcome.

##### Dose response relationship
- At low radiation dose, both DNA breaks that lead to a lethal chromosome aberration are often produced by a **single track action** So, the probability of forming a lethal aberration increases linearly with dose
- At higher dose, the two DNA breaks that combine to form an exchange aberration can arise from **two-track action**. So, the the probability of an interaction is then proportional to the square of the dose

$$S = e^{-n}$$
where 
- S = surviving fraction of cells
- n = mean number of lethal chromosome aberrations per cell

#### Linear quadratic model
Both the [[#Theory of Dual Radiation Action]] and [[#Molecular Theory of Cell Inactivation]] lead to a linear-quadratic survival curve but by following different approaches.
$$S(D) = e^{-\alpha D - \beta D^2}$$
where 
- $\alpha$ = initial slope at low dose = linear slope
- $\beta$ = add curvature to the final slope (due to larger dose) = quadratic curve
- $\frac{\alpha}{\beta}$ = dose at which the two cell-killing effects are equal 





