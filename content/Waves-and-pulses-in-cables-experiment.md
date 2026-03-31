---
title: Waves-and-pulses-in-cables-experiment
draft: false
tags:
  - physics
---
 
#### Introduction and theory
Transmission cables are widely used to carry electrical power or radio-frequency signals over long distances in the form of propagating electromagnetic waves. At low frequencies, electromagnetic energy can be transferred using simple wire connections but at high frequencies, this approach becomes impractical due to radiation loss. Instead, high-frequencies are transmitted via coaxial cables, which consist of an inner conductor and a grounded outer conductor separated by a dielectric[^1].

The behavior of wave propagation in coaxial cables is characterized by the cable's distributed inductance (L) and capacitance(C) per unit length. This gives to the cable's impedance, which governs how energy is carried along the line.

Impedance represents a similar phenomena as resistance but for AC circuits, where impedance is the total opposition a circuit or component offers to AC flows, following a general version of Ohm's law. It is measured in ohms and is given by
$$Z = R + j \chi$$
where Z = impedance, R = resistance, $\chi$ = reactance (*define*)

When a travelling wave reaches a boundary where the impedance changes (such as the termination at the end of the cable, part of it is transmitted while part of it is reflected[^2]. The amount reflected depends on the degree of impedance mismatch between the cable and its load. These reflections are undesirable in practice because they interfere with the original signal and due to superposition can lead to data errors, noise and reduced power. Impedance matching (designing the load impedance to equal the cable's characteristic impedance) is therefore a key engineering practice to suppress these reflections

To systematically explore this behavior, we examined three termination conditions. 
- open circuit termination = presents effectively infinite load impedance, producing a current node at the far end and a complete reflection of the incident wave with unchanged polarity
- short circuit termination = presents zero load impedance, producing a voltage node and a complete reflection with reversed polarity
- matched load termination = places a resistor equal to the characteristic impedance _Z₀_ at the cable's end. This causes the finite cable to behave as if it were semi-infinite: the wave encounters no impedance discontinuity, no reflection occurs, and all energy is absorbed by the resistor.

Another property of interest is the resonant frequency which occurs when impedance is a minimum. At resonance, the cable's reactive components cancel, and this condition is strongly dependent on the termination used — making it another measurable signature of the impedance relationships explored in this experiment.

#### Procedure
The experimental setup is shown in Figure 4.1 with the following instruments:
- Oscilloscope: used to record both the voltage-time and the current-time graphs
- Tektronix function generator: an AC power supply that outputs continuous sine waves or pulses
- Inverting buffer: serves as a contact/measuring point to connect the function generator to the cable being measured. It also allows control of the impedance boundary between the function generator (input terminal) and the cable of interest (output terminal) with the buffer source impedance initially set to 75 Ω

Coaxial cables of different lengths (60 m, 18 m, and 9 m) are examined in this experiment, in
which the 18 m cable is formed by connecting two 9 m cables

1. Calculation of L and C
	- •Measuring the diameter of the inner conductor and outer insulating material gives us the inductance and capacitance per unit length of the coaxial cable
2. RF input
	- set buffer impedance to 70 $\ohm$ and the output mode to CW
	- measured peak-to-peak voltage and current for a range of frequencies in order to determine $Z_{min}$,resonant frequencies, speed of propagation and dielectric constant
	- analyzed the phase relationships between voltage and current near resonant frequencies for open, short and matched load termination
3. Pulse input
	- analyzing the time dependent transient behavior of pulses in coaxial cables for the three cases of the three cables
	- adjusted the oscilloscope to pulse parameter and period of 10 μs/division and adjusting the function generator to pulse width of 30 ns, frequency to 100 kHz and output mode to pulse
	- positional oscilloscopes where adjusted to observe one period of the signal which consisted of two peaks (or pulses)
	- the inverting buffer impedance was adjusted to greater than and less than the characteristic impedance and the resulting pulse trains were analyzed

[^1]: Feynman, 1964; Department of Physics and Astronomy, 2026
[^2]:  Crone, 2026a
