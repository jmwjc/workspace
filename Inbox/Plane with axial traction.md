---
icon: OcInfinity16
---
#Elasticity #Example 

![[Plane with axial traction 2024-05-22 16.13.55.excalidraw]]

**Plain stress solution**:

Displacement

$$
u = \frac{1 - \nu^2}{E} P x, \quad v = - \frac{\nu(1+\nu)}{E} P y
$$

Strain

$$
\varepsilon_{xx} = \frac{1-\nu^2}{E}P, \quad
\varepsilon_{yy} = -\frac{\nu}{1-\nu}\varepsilon_{xx} , \quad
\varepsilon_{xy} = 0
$$

Stress

$$
\sigma_{xx} = P, \quad
\sigma_{zz} = \nu P
$$

**Incompressible material**

Volumetric strain
$$
\varepsilon_{ii} = \varepsilon_{11} + \varepsilon_{22} =\frac{1-2\nu}{1-\nu} \varepsilon_{11} = \frac{(1+\nu)(1-2\nu)}{E}P
$$

Hydrostatic pressure
$$
p =\frac{1}{3} \sigma_{ii} =\frac{1}{3}(\sigma_{xx} + \sigma_{zz}) =\frac{1+\nu}{3} P = K\varepsilon_{ii}
$$
where $K =\frac{E}{3(1-2\nu)}$.
