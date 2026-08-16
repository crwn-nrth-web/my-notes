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

| coordinate                    | x                        | y                         | z            | velocity                                                                             | line element ds                      |
| ----------------------------- | ------------------------ | ------------------------- | ------------ | ------------------------------------------------------------------------------------ | ------------------------------------ |
| polar                         | $r\cos \theta$           | $r \sin \theta$           |              | $\dot{r} \hat{r}$                                                                    | $ds^2 = dr^2 + r^2 d\theta^2 + dz^2$ |
| cylindrical $(r, \theta, z)$  | $r\cos \theta$           | $r \sin \theta$           | z            | $\dot{r} \hat{r} + r \dot{\theta} \hat{\theta} + \dot{z} \hat{z}$                    |                                      |
| spherical $(r, \theta, \phi)$ | $r\sin \phi \cos \theta$ | $r \sin \phi \sin \theta$ | $r\cos \phi$ | $\dot{r} \hat{r} + r \dot{\theta} \hat{\theta} + r\sin \theta \dot{\phi} \hat{\phi}$ |                                      |

