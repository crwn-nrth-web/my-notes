---
title: exposure-attenuation
draft: false
tags:
  - biology
  - physics
---
 **Exposure attenuation** = photons are attenuated via photon effect, Rayleigh, Compton scattering or pair production

*attenuation* = reduction in intensity or strength as it passes through the body

For a narrow beam [[quantities-and-units-used-to-describe-radiation-interaction#^8000c7|fluence]] (I) of photons, incident on an absorber of thickness dx, the number of photons which interact with the target atoms in the absorber and which are removed from the beam is given by

$$I(x) = I(0) e^{- \mu x}$$

**Linear attenuation coefficient** ($\mu$) = probability per unit path length that a photon will interact with the absorbing medium. 
- It depends on the photon energy and the atomic number of the medium

**Half value layer** (HVL) = absorber thickness that attenuates the beam to 50%
$$\frac{\ln(2)}{\mu}$$
**tenth value layer** (TVL) = absorber thickness that attenuates the beam to 10%
$$\frac{\ln(10)}{\mu}$$
### Interaction of radiation with matter - Photon
Indirectly ionizing radiation occurs with photon beams

Summary:

|                                     | photoelectric effect                | Compton effect                      | Pair production            | Rayleigh scattering |
| ----------------------------------- | ----------------------------------- | ----------------------------------- | -------------------------- | ------------------- |
| photon interaction                  | with whole atom (bound e-)          | with free electrons (valance e-)    | with nuclear coulomb field | with bound electron |
| mode of photon interaction          | photon disappears                   | photon scattered                    | photon disappears          | photon scattered    |
| energy dependence                   | $\frac{1}{(hv)^3}$                  | No                                  | increases with energy      | $\frac{1}{(hv)^2}$  |
| particles released                  | photoelectron                       | Compton electron                    | positron and electron pair | None                |
| atomic coefficient dependence       | $\propto Z^4$                       | $\propto Z$                         | $\propto Z^2$              | $\propto Z^2$       |
| mass coefficient dependence         | $\propto Z^3$                       | Independent                         | $\propto Z$                | $\propto Z$         |
| subsequent effect                   | characteristic x-rays, auger effect | characteristic x-rays, auger effect | annihilation radiation     | None                |
| Threshold                           | None                                | None                                | 1.02 MeV                   | None                |
| significant energy region for water | $< 20 keV$                          | $20 keV - 10 MeV$                   | $> 10 MeV$                 | $< 20 keV$          |

#### Photoelectric interaction
- photon interacts with atom (tightly bound electrons) and ejects an orbital electron from the atom
- process involves bound electrons (K, L, M, N shells)
- entire energy of photon is transferred to the electron to eject it from the atom
- kinetic energy of ejected photoelectron $hv - E_{b}$
- emission of characteristic x-rays and auger electrons

- atomic attenuation coefficient $\mu_{a} \propto \frac{Z^4}{(hv)^3}$
- mass attenuation coefficient $\mu_{m} \propto \frac{Z}{(hv)^3}$

#### Compton interaction (incoherent scattering)
- photon interacts with outer electron as though it were a free electron
- photon transfers some energy to the electron ejecting it out of the atom with some KE
- photon is scattered at an angle with a degraded energy
- compton interaction is almost independent of atomic number
- decreases with photon energy
- amount of energy scattered and transferred depends on the angle of emission of the scattered photon and energy of photon

- coefficient per electron / per gram 
	- for high Z materials $\propto Z^3$
	- for low Z materials $\propto Z^{3.8}$

#### Pair production
- photon interacts with the electromagnetic field of an atomic nucleus
- photon gives up all of its energy in the process of creating a positron and electron
- threshold energy = 1.02 MeV
- photon energy in excess of the threshold is shared between the two particles as KE
- coefficient per atom (atomic attenuation coefficient) $\propto Z^2$
- coefficient per gram (mass attenuation coefficient) $\propto Z$

#### Triplet production (electronic pair production)
- photon disappears in the vicinity of an electron to produce two electrons and one positron
- threshold energy = 2.04 MeV
- Cross section for pair production and triplet production is zero for photon energies below the threshold energy, and increases rapidly for energy above the threshold

#### Rayleigh (coherent) scattering
- interaction consists of an electromagnetic wave passing near the electron and setting it into oscillation
- scattered x-ray has the same energy as the incident beam
- probable in high atomic number materials with low photon energy

- atomic Rayleigh cross-section $(\sigma_{a})_{R} \propto (\frac{Z}{hv})^2$
- mass attenuation coefficient $\frac{\sigma_{R}}{\rho} \propto \frac{Z}{(hv)^2}$

#### Probability for an interaction 
The probability of a photon to undergo any one of the various interactions depends on the energy of the photon and the atomic number
- photoelectric effect predominates low photon energy
- compton effect predominates intermediate photon energy
- pair production predominates high phootn energy

![[Pasted image 20260202123013.png]]

### Interaction of radiation with matter - electrons
Inelastic collision with atomic electrons leads to 
- atomic ionization = ejection of orbital electron from an absorber atom
- atomic excitation = transfer of an orbital electron from one allowed orbit (shell) to a higher level allowed orbit

Atomic ionization and excitation result in collision energy losses experienced by the incident electrons, and are characterized by **collision (ionization) stopping power**

Inelastic collision with nuclei result in bremsstrahlung (radiation loss) and is characterized by **radiative stopping power**
