---
title: cavity-theory
draft: false
tags:
  - biology
  - physics
---
Consider a point within a medium, in order to measure the absorbed dose[^1] at a point P in a medium, a dosimeter (radiative sensitive device) can be introduced at that point. Generally, the sensitive medium of the dosimeter will not be the same material as the medium.

**Cavity theory** = relates the absorbed dose in the dosimeter's sensitive medium (cavity) to the absorbed dose in the surrounding medium.

Cavity sizes are referred to as small, intermediate, or large in comparison with the ranges of secondary charged particles produced in the cavity medium. 
- e.g. if the range of electrons is much larger than the cavity dimensions, the cavity is regarded as small
#### Bragg-Gray cavity theory

**Conditions for applications of the Bragg-gray cavity** =
1. cavity must be small when compared with the range of the charged particles incident on it, so that its presence does not perturb
	- this condition is valid only in regions of **charged particle equilibrium** = each charged particle of specific type + energy is replaced by an identical particle
2. absorbed dose in cavity is deposited only by charged particles crossing it (so that photon interactions in cavity is neglible)
	- the electrons depositing dose are produced outside the cavity (i.e. there are no secondary electrons produced)
	- electrons cross the cavity completely

According to Bragg-Gray cavity theory
$$D_{med} = D_{cav} \left( \frac{\bar{S}}{\rho} \right)_{med, cav}$$
where $\frac{\bar{S}}{\rho}$ is the ratio average unrestricted mass collision stopping powers of medium and cavity

#### Spencer-Attix cavity theory
It takes into account for secondary electron produced by hard collisions that may have sufficient energy to escape the cavity reducing the absorbed dose in the cavity

This modifies Bragg-gray cavity theory changing the stopping power to the restricted stopping power
- it only includes energy exchanges $< 10 KeV$ to exclude delta rays
- operates on the same conditions of Bragg-Gray
- cavity can be gas/liquid/solid

$$D_{med}=\frac{Q}{m} \left( \frac{W_{gas}}{e} \right) P_{el} P_{dis} P_{wall} P_{elec}$$


[^1]: ![[quantities-and-units-used-to-describe-radiation-interaction#^60e2f7]]