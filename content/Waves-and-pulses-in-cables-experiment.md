---
title: Waves-and-pulses-in-cables-experiment
draft: false
tags:
  - physics
---
#### Introduction and theory
Transmission cables are everywhere carrying electrical power or radio-frequency signals over long distances in the form of propagating electromagnetic waves. At low frequencies, simple wire connections work fine but for high frequencies, they become impractical due to radiation loss, and so coaxial cables are used instead.

In this experiment, we investigated how electromagnetic waves propagate through these cables, and what happens when those waves encounter a boundary. Specifically, we explored three termination conditions — open circuit, short circuit, and matched load — using both continuous RF signals and discrete pulses, and compared our results against transmission line theory.

A coaxial cable consists of an inner conductor and a grounded outer conductor separated by a dielectric. The wave behavior inside the cable is governed by the cable's distributed inductance (L) and capacitance(C) per unit length. This gives rise to the cable's characteristic impedance, which governs how energy is carried along the line.

**Key Transmission equations**
The key quantity we are working with is impedance, which is the AC analogue of resistance, representing the total opposition to alternating current flow. 
$$Z = R + j \chi$$
where Z = impedance, R = resistance, $\chi$ = reactance

A related quantity is resonant frequency which occurs when impedance is a minimum, at which the cable's inductive and capacitive contributions cancel. 

This bring us to **Impedance matching**. When a wave reaches a boundary where impedance changes, part of it reflects. These reflections interfere with the original signal and — through superposition — can cause data errors, noise, and power loss. Matching the load impedance to the cable's characteristic impedance Z_0 eliminates the discontinuity and suppresses reflection entirely.

**The three terminations**
We examined three termination conditions that span the full range of this behavior. 
- open circuit presents infinite load impedance, producing a current node and reflecting the wave with unchanged polarity.
- short circuit presents zero load impedance, producing a voltage node and reflecting with reversed polarity
- matched load termination places a resistor equal to Z_0 at the cable's end so there's no impedance discontinuity, no reflection, and all energy is absorbed by the resistor.

**Impedance and phase relationship**
Finally, the phase relationship between voltage and current is set by the nature of the impedance. A resistive load keeps them in phase; an inductive load causes voltage to lead; a capacitive load causes current to lead.
### Procedure
Our set up consisted of a function generator, an oscilloscope and an inverting buffer connecting the two. The buffer also controlled the impedance boundary at the input terminal, initially set to 75 $\ohm$. . Coaxial cables of 60 m, 18 m, and 9 m were used — the 18 m cable formed by connecting two 9 m cables in series.

 > a shorting termination cap attached to the far end of the cable to impose short termination, and a variable resistor is attached at the end of the cable to impose matched load termination

The experiment had three stages:
1. first, we used a micrometer to measure the inner conductor and outer insulator diameters, which let us calculate _L_ and _C_ per unit length directly from the cable geometry.
2. Second, with the function generator in CW mode, we swept across a range of frequencies and recorded peak-to-peak voltage and current for both open and short terminations on the 60 m cable. 
3. Third, we switched to pulse mode — 30 ns pulse width at 100 kHz — and examined the time-domain behaviour of the cable under all three terminations. 
### Analysis and Discussion

#### Calculation of L and C
Using micrometer measurements averaged over three readings, we calculated _L_ and _C_ per unit length using the standard coaxial formulas. The relative permeability was taken as 1. This gives us a value for L and C in terms of the relative dielectric constant, which we will determine in the next stage.

#### RF analysis
Plotting impedance as a function of frequency, both terminations followed the qualitative behavior predicted; the open circuit produced a cotangent like curve and the short circuit a tangent like one. Not the short circuit termination does show a noticeable upward shift and more scatter, but this can be attributed to non-idealities in the shorting cap. Unlike the open termination, which required no physical attachment, the shorting cap in the short termination could case small misalignments enough to introduce stray impedance.

The resonant frequencies were identified and taking the spacing of consecutive resonant frequencies, the speed of propagation was calculated. Using this alongside of our geometric values of L and C, we calculated a dielectric constant of $\epsilon_r = 2.2 \pm 0.2$ -- consistent with either polyethylene or PTFE. Polyethylene is the most likely candidate given its standard use in laboratory coaxial cables and its lower cost. 

Examining the phase relationship near resonance, we found the expected behavior for the open termination as seen on the slide. For short termination, the unexpected result was for current leading behavior at the impedance maxima. This could be because of the deviations already seen in the impedance plot and likely attributable to the same connector non-idealities. For the matched termination, both the voltage and current were seen to be in phase throughout as expected.

When looking for an analogous comparison to these phase relationships, it was seen that a series LCR circuit is analogous for the phase trends of impedance minimum as at resonance it reaches a minimum. And a parallel LCR circuit is analogus with impedance maximum as at resonance it reaches a maximum.

Predicted resonant frequencies were calculated from the input impedance equations by setting input impedance to infinity for Z_max and to 0 for Z_min. Comparing predicted and measured resonant frequencies  terminations, errors were consistently in the 2-5% range with the largest discrepancy at n=1 and decreased at higher frequencies as expected. The measured frequencies were systematically lower than predicted throughout, the measured speed of propagation is accounted for correctly with the dielectric slowing the speed, so it is likely the systematic offset is due to small difference in the effective cable length. 

Also to note, every frequency producing Z_min under open termination produced Z_max under short termination, and vice versa — a direct consequence of their opposite boundary conditions.

#### Pulse Input
Next, we analyzed the pulse input, using a discrete signal, to see the time-dependent transient behavior of pulses in coaxial cables. 

> The same set up was used with the oscilloscope was adjusted to the pulse parameter and set to a period of approx. 10 $\mu s /$division and the function generator was adjusted to a pulse width of 30 ns and frequency of 100 kHz for clear observation of reflection signal.

Fig 5 and 6 shows one period of the signal for a 60 m cable for open and short termination respectively. Both show two peaks (or pulses) where the first pulse is due to the input from the function generator and the second pulse is due to the reflection of the input pulse.

Comparing the two figures, the open and short terminations produced reflections of equal magnitude and opposite polarity, exactly as predicted. For open, the reflected voltage pulse returns with same polarity and the reflected current with the opposite -- consistent with the current node boundary condition. For short, the reflected voltage was inverted and current unchanged -- consistent with the voltage node. 

For the matched load, the reflected pulse was minimized by tuning a variable resistor connected to the far end of the cable. Measuring this resistance using a digital multimeter gives us the matched load resistance of $74.1 \pm 0.5 \ohm$. The theoretically predicted value, calculated from L and C, is in very close agreement with the measured value. The propagating speed extracted from the pulse timing was also consistent with the RF method. 

The buffer impedance was then increased and decreased from its set value of 75 $\ohm$ to see the effect of impedance mismatching. Increasing the buffer impedance, it behaves like a partial open circuit. Decreasing the buffer impedance, it behaves like a partial short circuit. However, this was not clearly observed — Figures 8 and 9 appeared similar in shape, suggesting the buffer impedance may not have been correctly set during that part of the measurement.

### Conclusion

This experiment gave a thorough picture of wave propagation in coaxial cables. Our RF and pulse measurements were mutually consistent and agreed with transmission line theory across the board. We identified polyethylene as the most probable dielectric, confirmed the open/short circuit duality experimentally, and demonstrated that impedance matching effectively eliminates reflections. Systematic deviations were small and physically well-motivated — non-ideal connectors and small cable losses — rather than fundamental disagreements with theory.










[^1]: Feynman, 1964; Department of Physics and Astronomy, 2026
[^2]:  Crone, 2026a
