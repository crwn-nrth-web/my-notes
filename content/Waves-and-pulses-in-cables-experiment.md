---
title: Waves-and-pulses-in-cables-experiment
draft: false
tags:
  - physics
---
#### Introduction and theory
Transmission cables carry electrical power or radio-frequency signals over long distances in the form of propagating electromagnetic waves. At low frequencies, simple wire connections work but at high frequencies, this approach becomes impractical due to radiation loss. Hence, coaxial cables are used instead which consist of an inner conductor and a grounded outer conductor separated by a dielectric[^1].

The behavior of wave propagation in coaxial cables is characterized by the cable's distributed inductance (L) and capacitance(C) per unit length. This gives rise to the cable's characteristic impedance, which governs how energy is carried along the line.

**Key Transmission equations**

The first property of interest is Impedance, which is the AC circuit analogue of resistance, and is the total opposition a circuit or component offers to alternating current. It is measured in ohms and is given by
$$Z = R + j \chi$$
where Z = impedance, R = resistance, $\chi$ = reactance

A related quantity is resonant frequency which occurs when impedance is a minimum. At resonance, the cable's inductive and capacitive contributions cancel. This condition depend on the termination type used at the cable's end, which will be discussed more later on.

**Impedance matching**

When a travelling wave reaches a boundary where the impedance changes, part of it is transmitted while part of it is reflected[^2]. The amount reflected depends on the degree of impedance mismatch between the cable and its load. These reflections are undesirable in practice because they interfere with the original signal and due to superposition can lead to data errors, noise and reduced power. Impedance matching is therefore a key engineering practice that will be explored in this experiment, where the load impedance is designed to equal the characteristic impedance.

**The three terminations**

To systematically explore this behavior, we examined three termination conditions. 
- open circuit termination = presents effectively infinite load impedance, producing a current node at the far end and a complete reflection of the incident wave with unchanged polarity
- short circuit termination = presents zero load impedance, producing a voltage node and a complete reflection with reversed polarity
- matched load termination = places a resistor equal to the characteristic impedance _Z₀_ at the cable's end. the wave encounters no impedance discontinuity, no reflection occurs, and all energy is absorbed by the resistor.

**Impedance and phase relationship**
Another aspect  examined was the phase relationship between voltage and current which is determined by the nature of impedance present.
- a purely resistant component has an impedance equal to the resistance of the component, and so the voltage and current are in phase
- an inductive component has a positive impedance and so voltage will lead the current
- a capacitive component has a negative imaginary impedance and so current will lead the voltage

#### Procedure
The experimental setup is shown in Figure 3 with the following instruments:
- Oscilloscope: records both the voltage-time and the current-time waveforms
- function generator: an AC source that outputs continuous sine waves or pulses
- Inverting buffer: connects the function generator to the cable being tested. It also  controls the impedance boundary between the function generator (input terminal) and the cable of interest (output terminal) with the buffer source impedance initially set to 75 Ω
- a shorting termination cap attached to the far end of the cable to impose short termination, and a variable resistor is attached at the end of the cable to impose matched load termination

Coaxial cables of different lengths (60 m, 18 m, and 9 m) are examined in this experiment, where the 18 m cable is formed by connecting two 9 m cables

**Procedure**
1. Calculation of L and C
	First, the inductance and capacitance per unit length of the cable was calculated by measuring the diameter of the inner conductor and outer insulating material using a micrometer
2. RF input
	The inverting buffer impedance was to 70 $\ohm$ and the output mode to CW, in order to measure the peak-to-peak voltage and current for a range of frequencies in order to determine $Z_{min}$, resonant frequencies, speed of propagation and dielectric constant. The phase relationships between voltage and current near resonant frequencies for open, short and matched load termination were also analyzed
3. Pulse input
	The time dependent transient behavior of coaxial cables was examined for the three terminations. The matched load resistance was determined as well as the speed of propagation and inductance and capacitance. 
	- adjusted the oscilloscope to pulse parameter and period of 10 μs/division and adjusting the function generator to pulse width of 30 ns, frequency to 100 kHz and output mode to pulse
	- positional oscilloscopes where adjusted to observe one period of the signal which consisted of two peaks (or pulses)
	- the inverting buffer impedance was adjusted to greater than and less than the characteristic impedance and the resulting pulse trains were analyzed

#### Analysis and Discussion

**Calculation of L and C**
By measuring the diameters of the inner conductor and outer insulator using a micrometer of precision 0.01 mm three times and taking the average, the inductance and capacitance per unit length could be calculated, using the formulas on the slide.

The permittivity of free space and the permeability of free space are known constants and the relative permeability of is taken to be 1. This gives us a value for the inductance per unit length and the capacitance per unit length in terms of the relative dielectric constant. We will come back to this result once we determine the relative dielectric constant.

**RF input**
For a range of frequencies with frequency step of 0.1 MHz, the peak-to-peak amplitude of the voltage and current were measured for both the open and short circuit termination for the 60 m cable. For each frequency, the input impedance was calculated by dividing the voltage over current and this was plotted as a function of frequency.

Both the open and short circuit plots follow the qualitative behavior predicted for a lossless line based on their equations, as the open termination shows a tan graph and the short termination shows a cot graph. Now it is obvious by looking at the short termination that there is an upward shift in impedance values and there is deviation from idealized behavior. It is not as perfect of a graph as the open termination. This could be explanined due to non-idealities in the experimental set up. The open termination was achieved passively with no changes done to the end of the cable but for the short termination a shorting cap needed to be added. The shortening cap could have been nudged slightly or not placed correctly to give us more imperfections in our measurements. It is also important to note that the equations are based on idealized lossless cables when our cables are obviously not perfectly lossless.

The resonant frequencies can be identified as the minimum impedance values as labelled on the graphs and are shown in Table 4 of the lab report.

In order to determine the speed of propagation, we considered resonant frequencies with $\delta f$ representing the difference of two consecutive resonant frequencies. This gives us 4 speed values for each termination, averaging the results gives us the speed of propagation

Next we determined the relative dielectric constant using the values of inductance and capacitance determined previously. Comparing our value with those from the physical material list, this gives us a dielectric of material either polyethylene or PTFE as both are within the uncertainty limits. It is most likely that the dielectric is polyethylene as this is the standard material choice due to its low cost and dielectric properties. From this dielectric constant, we can now calculate the capacitance value.

Next, the phase relationship was examined by increasing the frequency around the resonant frequencies and observing the current and voltage waveforms. This was done for both impedance minimums and maximums as seen in table 6. Theoretically, the phase relationship for short termination are expected to be inverted compared to the open termination, i.e. at impedance minimum, for open termination current leads voltage while for short termination voltage leads current. So, The current leading behavior at impedance maximum for short termination is an unexpected results. Going back to the deviations seen in the short termination plot, the deviation here can be explained for the same reasons shifting the phase relationships subtly.

For the matched load resistance, both the voltage and current were seen to be in phase throughout as expected.

When finding an analogous comparison to these phase relationships, it was seen that a series LCR circuit is analogous for the phase trends of impedance minimum as at resonance it reaches a minimum. And a parallel LCR circuit is analogus with impedance maximum as at resonance it reaches a maximum.

Predicted resonant frequencies were calculated from input impedance equations by setting input impedance to infinity for Z_max and to 0 for Z_min These were compared against our measured values for both open and short terminations. For both terminations, errors were consistently in the 2-5% range with the largest discrepancy at n=1 and improving at higher frequencies. The measured frequencies were systematically lower than predicted throughout, which could be due to a lower speed of propagation or a longer cable length. A notable result is that the Z_min frequencies of the open circuit correspond exactly to the Z_max frequencies of the short circuit, and vice versa. This is a direct consequence of their opposite boundary conditions, where the the short termination enforces a voltage node while the open termination enforces a voltage antinode.







[^1]: Feynman, 1964; Department of Physics and Astronomy, 2026
[^2]:  Crone, 2026a
