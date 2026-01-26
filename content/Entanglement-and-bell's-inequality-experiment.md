---
title: Entanglement-and-bell's-inequality-experiment
draft: false
tags:
  - lab
  - physics
---
# Theory
**Quantum entanglement** is the idea that particles (in our case, photons) can be correlated in a quantum mechanical sense, so that changing the state of one particle changes the state of the other when they "reconnect" with one another.

In this case, we are defining quantum states in terms of polarization. **Polarization** is the direction of the electric field oscillation with respect to a plane of reference (lab manual).

Einstein-Podolsky-Rosen (EPR) argument argued that quantum mechanics could not be a complete theory because such entanglement implies either faster-than-light influences or incomplete physical descriptions.[^1]

EPR argued that any reasonable physical theory should meet the criteria of **local realism**, where:
- "local" refers objects that are influenced only by their immediate surroundings
- "real" refers to objects that have definite properties independent of measurement.
According to EPR, quantum entanglement is incompatible with local realism, since it implies that particles do not have definite values independent of measurement and can be influenced across space arbitrarily quick[^3].

[explain hidden variables proposed by Einstein]

John S. Bell proposed a new experiment that could test whether the behavior of quantum entangled particles was consistent with local realism. Consider two detectors that can perform measurements whose outcomes could only ever take one of two values; detector A has two outputs $a$ and $a'$, detector B has two outputs $b$ and $b'$. 









**spontaneous parametric downconversion (SPDC)** = a non-linear optical process where a photon spontaneously splits into two other photons of lower energies[^2]

**Bell's inequality** = Bell assumed that Einstein's hidden variable hypothesis was true and then showed that it leads to a contradiction, hence proving the hidden variable theory as false.  

> If B is a subset of A, it must be that $N(A) \geq N(B)$

Bell's thought experiment involved sending photons through polarized filters. If a photon passes through a filter, it is referred to as ‘passed’. If it’s blocked, it’s referred to as ‘failed’. The probability that a photon will pass or fail depends entirely on the angle between its polarization state and the filter’s.

So, 
$$\begin{align} A= \text{pass }, \bar{A} = \text{fail } . . . \\
A \bar{B} = \text{pass A, fail B . . .} \\
\text{Then Bell's inequality: } N(A \bar{B} + B \bar{C}) \geq N(A \bar{C}) \\
\text{because } A \bar{C} \text{ is a subset of } A \bar{B} + B \bar{C}  

\end{align}$$

Three lens were used:
- *Lens A* = vertically polarized lens ($\theta = 0$)
- *Lens B* = lens polarized at angle $\theta$
- *Lens C* = lens polarized at angle $2 \theta$

These were run in 3 combinations, using vertically polarized quantum entangled photons and with $\theta = 22.5 \degree$ 

The assumption was that the states of the quantum entangled photons only depends on their original hidden variables and cannot change just because a measurement was taken on the other particle. This assumption is proven false; therefore, there are no hidden variables as Einstein proposed.


**Clauser-Horne-Shimony-Holt bell inequality** = used to experimentally prove bell's inequality

> ***See also:***
> [Superposition and entanglement notes](https://howfarawayisit.com/wp-content/uploads/2025/11/Quantum-Entangelment-2025.pdf)
> [[quantum-superposition]]
> 

## Experimental set-up
![[Pasted image 20260122110255.png]]
The figure above shows a polarization-entangled photon pair source. Polarization entangled photon pairs from the source are collected in optical fibers and directed to polarization analyzers for correlation measurements.

### Experiment 1: Bell state preparation demo




[^1]: Fine, Arthur, (2020) "The Einstein-Podolsky-Rosen Argument in Quantum Theory", _The Stanford Encyclopedia of Philosophy_, Edward N. Zalta (Summer 2020 ed.), https://plato.stanford.edu/entries/qt-epr/

[^2]: Couteau, C. (2018). Spontaneous parametric down-conversion. _Contemporary Physics_, _59_(3), 291–304. https://doi.org/10.1080/00107514.2018.1488463

[^3]: Kaiser, D. (n.d.). _Lecture Notes for 8.225 / STS.042, “Physics in the 20th Century”: Bell’s Inequality and Quantum Entanglement_.
