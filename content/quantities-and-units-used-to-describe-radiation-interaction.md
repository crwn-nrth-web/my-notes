---
title: quantities-and-units-used-to-describe-radiation-interaction
draft: false
tags:
  - biology
  - physics
---

|                                    |                                                                                                                        | symbol                  | units                 |
| ---------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------------- | --------------------- |
| photon fluence                     | ratio of number of particles ($dN$) incident on an imaginary sphere of cross-sectional area $dA$ ^8000c7               | $\Phi$                  | $m^{-1}$              |
| fluence rate                       | number of photons that pass through unit area per unit time                                                            | $\phi$                  | $s^{-1} m^{-1}$       |
| energy fluence                     | ratio of the sum of energies of all photons ($dE$) that enters a sphere of cross-sectional $dA$                        | $\Psi$                  | $J m^{-2}$<br>        |
| energy fluence rate                | energy carried across unit area per unit time                                                                          | $\psi$                  | $J s^{-1} m^{-2}$<br> |
| linear attenuation coefficient     | probability per unit path length that a photon will interact with the absorbing medium.                                | $\mu$                   | cm$^{-1}$             |
| mass attenuation coefficient       |                                                                                                                        | $\mu_{m}$               | cm$^{2}$ / g          |
| atomic attenuation coefficient     |                                                                                                                        | $\mu_{a}$               | cm$^{2}$ / atom       |
| electronic attenuation coefficient |                                                                                                                        | $\mu_{e}$               | cm$^{2}$ / electron   |
| energy transfer coefficient        | fraction of photon energy transferred into KE per unit thickness of absorber *including* energy loss to bremsstrahlung | $\mu_{tr}$              |                       |
| mass energy transfer coefficent    |                                                                                                                        | $\frac{\mu_{tr}}{\rho}$ |                       |
| energy absorption coefficient      | fraction of photon energy transferred into KE per unit thickness of absorber *excluding* energy loss to bremsstrahlung | $\mu_{ab}$              |                       |
| mass energy transfer coefficient   |                                                                                                                        | $\frac{\mu_{ab}}{\rho}$ |                       |

### Kerma and absorbed dose
**Kerma** (Kinetic energy released per unit mass) = defined as the sum of initial kinetic energy of all the charged ionizing particles liberated by uncharged particle ($\partial E_{tr}$) in a material of mass
- applicable to *indirectly ionizing radiation*

$$K = \frac{\partial \bar{E_{tr}}}{dm}$$
- SI unit: Gray (Gy) = J/kg

Energy is transferred to electrons by photons in two ways:
1. through collisions (low z materials) = **collision kerma**
2. through radiation interactions (bremsstrahlung and e-p annihilations) (high z materials) = **radiation kerma**

**radiation fraction** (g) = average fraction of the energy which is transferred to electrons and  
then lost through radiative processes is represented by a factor g

**exposure** = ionization equivalent of the collision kerma in air, i.e. the number of coulombs of charge created per joule of energy deposited is the charge created per unit mass of air (or exposure)

$$X = (K_{\text{coll}})_{\text{air}} \frac{e}{W_{\text{air}}}$$

**Absorbed dose** = energy absorbed in medium per unit mass
$$D = \frac{\partial E_{ab}}{dm}$$ ^ba7822
- SI unit: Gray (Gy) = J/kg

Absorbed dose in the medium is related to the **electron fluence** in the medium
$$D_{med} = \Phi \left( \frac{S_{\text{coll}}}{\rho} \right)_{med}$$
where $\frac{S_{\text{coll}}}{\rho}$ is the unrestricted mass collision stopping power of the medium at the energy of the electron ^60e2f7

This relation is valid under the condition =
- photons escape the volume of interest
- secondary electrons are absorbed on the spot
- or there is charged particle equilibrium (CPE) of secondary electrons
#### Relationship between collision kerma and absorbed dose

*Difference between kerma and absorbed dose* = Kerma measures the amount of energy that is transferred from photons to electrons per unit mass at a certain position, while absorbed dose measures the energy deposited in a unit mass at a certain position

At radiological energies, kerma and absorbed does are virtually equal. At higher energies, a photon may interact with tissue in one position and create an electron that posses enough energy to deposit energy at a location away from the interaction point.

When a broad beam of photons enters a medium, 
- kerma is a maximum at the surface and decreases with depth
- absorbed dose builds up to a maximum and then decreases at the same rate as kerma
- before the two curves meet (**build-up region**), the electron build up is less than complete $\beta < 1$ 
- if photon attenuation is negilible through the region of interest, **electronic equilibrium** exists $\beta = 1$
- At depths greater than the maximum range of electrons, attenuation of the primary occurs = **transient electronic equilibrium** $\beta > 1$ 

![[Pasted image 20260202115114.png]]

