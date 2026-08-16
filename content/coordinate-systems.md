---
title: coordinate-systems
draft: false
tags:
  - physics
  - math
aliases:
  - curvilinear-coordinates
---
**curvilinear coordinates** are a way to map points in space where the grid lines can bend or curve, unlike the straight gridlines of cartesian coordinates

| coordinate  | x                        | y                         | z            | velocity                                                                             |
| ----------- | ------------------------ | ------------------------- | ------------ | ------------------------------------------------------------------------------------ |
| polar       | $r\cos \theta$           | $r \sin \theta$           |              | $\dot{r} \hat{r}$                                                                    |
| cylindrical | $r\cos \theta$           | $r \sin \theta$           | z            | $\dot{r} \hat{r} + r \dot{\theta} \hat{\theta} + \dot{z} \hat{z}$                    |
| spherical   | $r\sin \phi \cos \theta$ | $r \sin \phi \sin \theta$ | $r\cos \phi$ | $\dot{r} \hat{r} + r \dot{\theta} \hat{\theta} + r\sin \theta \dot{\phi} \hat{\phi}$ |

