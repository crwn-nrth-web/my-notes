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

![[Dual-action-radiation-theory#Linear quadratic model]]

For the Linear Quadratic model where $S(D)$ is the fraction of cells to survive a given dose in which
- $P = \alpha D$ is the probability of cell death arising from a single hit ("one track action") producing a double strand break
- $P = \beta D^2$ is the probability of cell death arising from multiple hits ("two track action") enough to produce a double strand break

The linear quadratic model assumes that a cell can be killed in two ways:
1. single lethal event = $S^1$
2. accumulation of sublethal events = $S^n$
So that $$S = S^1 S^n = e^{-\alpha D - \beta D^2}$$
#### shape of the survival curve
- **high alpha/beta ratio** (around 10) = indicate that two track action damage does not readily accumulate to lethal effects and there is little increase in cell killing per unit dose for higher total dose
	- indicate a greater linear portion on the cell survival plot
- **low alpha/beta ratio** (less than 3) = indicate that two track action damage produces increased lethality for higher doses
	- indicate a greater curvature

#### properties of cell survival curves

- for late responding tissues, the survival curves are more curved than those for early responding tissues
	- for early effects the ratio is large; for late effects the ratio is small
	- early effects dominates at low doses
- the $\alpha$ and $\beta$ components of mammalian cell killing are equal at the following doses:
	- 10 Gy for early responding tissues
	- 3 Gy for late responding tissues
- dose response is more curvy for late effects than early effects
- late responding tissues more sensitive to change in fractionation
- fraction size is dominant factor determining late effects