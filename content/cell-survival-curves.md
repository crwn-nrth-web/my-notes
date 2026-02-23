---
title: cell-survival-curves
draft: false
tags:
  - biology
  - physics
---
Different cells have different sensitivity to radiational and so **cell survival curves** demonstrate the radiosensitivity of a cell type to radiation

### In vitro cell survival curve

How to generate a survival curve
1. culture the cells
2. expose the cells to a specified dose of radiation
3. assess the ability of irradiated cells to reproduce
	- cells that retain the ability to divide are reported as the fraction of cells that have *survived* irradiation
4. process is repeated with different doses of radiation and the findings are plotted on a graph

For the control: 
- $N_0$ = the number of individual cells seeded into a dish. 
- radiation dose $D = 0$
- After incubation time $\Delta t_{inc}$ where the cells divide, the number of colonies is $N_1$. 
- Ideally, the $N_1 = N_0$ but in reality, $N_1 < N_0$ due to various reasons such as suboptimal growth medium, errors and uncertainties in counting, etc.

**Plating efficiency** = fraction of cells seeded that grow into colonies
$$PE = \frac{\text{number of colonies for D=0}}{\text{number of cells seeded for D=0}} = \frac{N_{1}}{N_{0}}$$

For trial 1:
- $N_0$ = the number of individual cells seeded into a dish. 
- radiation dose $D_{1}$ 
- cells are incubated for time $\Delta t_{inc}$ 
- number of colonies after incubation $N_2$

**Survival** $$S = \frac{\text{number of colonies for D}}{\text{number of cells seeded for D} \times PE}$$
### Survival curve in linear quadratic model

![[theory-of-radiation-to-cell-death#Linear quadratic model]]

For the Linear Quadratic model where $S(D)$ is the fraction of cells to survive a given dose in which
- $P = \alpha D$ is the probability of cell death arising from a single hit ("one track action") producing a double strand break
- $P = \beta D^2$ is the probability of cell death arising from multiple hits ("two track action") enough to produce a double strand break

The linear quadratic model assumes that a cell can be killed in two ways:
1. single lethal event = $S^1$
2. accumulation of sublethal events = $S^n$
So that $$S = S^1 S^n = e^{-\alpha D - \beta D^2}$$
**mean inactivation dose** $D_{0}$ = the average dose required to inactivate (kill) cells in a population
- in general, for mammalian cells $D_{0} = 1 - 1.5 \text{ Gy}$

$$\ln N = \frac{D_{q}}{D_{0}}$$
- **extrapolation dose (N)** = it is the measure of the size of the shoulder
- **quasi-threshold dose** $D_{q}$ = a better measurement for the width of the shoulder and is repeated between fractions if enough time is left for repair
#### shape of the survival curve
- **high alpha/beta ratio** (around 10) = indicate that two track action damage does not readily accumulate to lethal effects and there is little increase in cell killing per unit dose for higher total dose
	- indicate a greater linear portion on the cell survival plot
- **low alpha/beta ratio** (less than 3) = indicate that two track action damage produces increased lethality for higher doses
	- indicate a greater curvature
#### properties of cell survival curves
**early responding tissue** (e.g. skin, GI tract) show radiation damage within weeks (acute) due to rapidly dividing cells, making them sensitive to total dose and time.

**late responding tissue** (e.g. brain, lung, kidney, spinal cord, bladder) show damage months/years later (chronic) 

| feature                                                                     | early-responding tissue                        | late responding tissue                         |
| --------------------------------------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| slope of cell survival curve                                                | steeper linear slope                           | more curved                                    |
| survival curve shoulder                                                     | small                                          | large                                          |
| when are the $\alpha$ and $\beta$ components equal ($\frac{\alpha}{\beta}$) | high $\frac{\alpha}{\beta} \sim 10 \text{ Gy}$ | low $\frac{\alpha}{\beta} \sim 2-3 \text{ Gy}$ |
| fractionation sensitvity                                                    | low                                            | high                                           |

### Normal vs tumor cell curves
The principle of radiotherapy is usually illustrated by plotting two sigmoid curves:
1. Tumor control probability (TCP)
2. Normal tissue complication probability (NTCP)

**Tumor control probability (TCP)** = probability that all clonogenic tumor cells are killed
- at low dose, TCP $\approx 0$ (tumor not controlled)
- at high dose, TCP plateaus near 1 (high chance of cure)
- TCP never reaches a value of 1.0 because of microscopic or metastatic spread of the disease beyond the tumor site
	- Radiotherapy can only control disease where the dose is delivered so because it is likely that the tumor cells have already spread microscopically or seeded in distant organs, the perfecto local control does not guarantee cure

**Normal tissue complication probability (NTCP)** = probability of clinically significant side effects in normal tissue
- at low dose, NTCP $\approx 0$ (safe)
- at high dose, NTCP $\to 1$ (high risk of complications)
- it is important to keep the dose to normal tissue lower than the does to tumors to minimize treatment complications and optimize treatment outcomes

The **therapeutic ratio** is the separation between the TCP and NTCP curves
- this region is called the **therapeutic window**
- the best treatment dose is in the region where TCP is maximized while simultaneously minimizing the NTCP
- wider the gap between TCP and NTCP, the better the therapeutic ratio

#### Radiosensitizers and Radioprotectors
**Radiosensitizers** are chemical modifications that make tumor cells more vulnerable to radiation therapy and so shifts the TCP curve to the left

**Radioprotectors** are chemical modifications that protect normal tissues from radiation and so shifts NTCP curve to the right

**Dose modifying factor (DMF)** quantifies how an agent (sensitizer or protector) alters the effect of a given dose radiation
$$DMF = \frac{dose_{control}}{dose_{agent}}$$
- if a drug makes cells more sensitive $DMF > 1$ (radiosensitizers)
- if a drug protects cells $DMF < 1$ (radioprotectors)
