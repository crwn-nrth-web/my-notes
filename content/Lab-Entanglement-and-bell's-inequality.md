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

John S. Bell proposed a new thought experiment that could test whether the behavior of quantum entangled particles was consistent with local realism. Consider two detectors that can perform measurements whose outcomes could only ever take one of two values; the measurement outcomes can be represented as $A = \pm 1$ and $B= \pm 1$. Also, detector A can choose to take measurements with input settings $a$ and $a'$; likewise detector B can choose to take measurements with input settings $b$ and $b'$. 

Locality is imposed by assuming that the output from the two detectors depends only on the input setting (a, b) and other properties prepared at the source that could affect the measurement (these properties are called "hidden variable", proposed by Einstein, represented by $\lambda$). Realism is imposed by assuming the inputs (a , a' , b , b') result in a predetermined output ($\pm 1$).

The expectation value $E(a,b)$ for a given experimental run: 
$$E(a,b) = \int \partial{\lambda} \  A(a, \lambda) B(b, \lambda)$$
The value $\lambda$ is considered to vary for each experimental run and follows a probability distribution $\int \partial \lambda f(\lambda)$, where both particles A and B would share the same value of $\lambda$ on any given run. This is demonstrated by table below. 

| $\lambda$     | a     | a'    | b     | b'    |
| ------------- | ----- | ----- | ----- | ----- |
| $\lambda_{1}$ | 1     | -1    | 1     | 1     |
| $\lambda_2$   | 1     | 1     | -1    | -1    |
| . . .         | . . . | . . . | . . . | . . . |

The combination of expectation values, resulting from the different detector input settings, gives the parameter $S$ known as the Clauser-Horne-Shimony-Holt (CHSH) parameter.

$$ S = E(a,b) + E(a' , b) - E(a, b') - E(a' , b')$$
As can be seen from table 1, for any particular $\lambda_i$, there are two possibilities:
- Either $B(b , \lambda) + B(b', \lambda) = 0$ and $B(b, \lambda) - B(b' , \lambda) = \pm 2$
- or $B(b , \lambda) + B(b', \lambda) = \pm 2$ and $B(b, \lambda) - B(b' , \lambda) = 0$

This leads to: 
$$A(a, \lambda) [B(b , \lambda) + B(b', \lambda)] + A(a' , \lambda)[B(b , \lambda) - B(b', \lambda)] = \pm 2$$
$$ \int \partial \lambda f(\lambda) \ A(a, \lambda) [B(b , \lambda) + B(b', \lambda)] + A(a' , \lambda)[B(b , \lambda) - B(b', \lambda)] \leq 2$$
And so the CSHS inequality becomes
$$|S| = |E(a,b) + E(a' , b) - E(a, b') - E(a' , b')| \leq 2$$


**spontaneous parametric downconversion (SPDC)** = a non-linear optical process where a photon spontaneously splits into two other photons of lower energies[^2]




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
