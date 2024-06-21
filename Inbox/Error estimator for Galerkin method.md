---
Icon: OcInfinity 16
---

#Formulation/Galerkin #Math/FunctionalAnalysis

Consider the traditional variational problem as follows

$$
\textrm{find} \; u \in V, \quad a(v,u) = f(v), \quad \forall v \in V
$$
where $a: V\times V\rightarrow \mathbb R$ is a symmetric bilinear form as the following properties

- **continuity**
$$
a(v,u) \le C \Vert v \Vert_V \Vert u \Vert_V, \quad \forall v, u \in V
$$

- **coercivity**
$$
a(u,u) \ge \alpha \Vert u \Vert_V^2, \quad \forall u \in V
$$
$$
\alpha \Vert u \Vert_V \le \sup_{w \in V \setminus \{0\}} \frac{a(w,u)}{\Vert w \Vert_V}, \quad \forall u \in V
$$

```ad-remark
The *coercivity* of the bilinear form is equivenlent to the *positive definetiness* of the stiffness matrix.
```

Introducing the approximation, like finite element approximation, to solve the above problem leads to the corresponding Ritz problem as
$$
\textrm{find} \; u_h \in V_h, \quad a(v_h,u_h) = f(v_h), \quad \forall v_h \in V_h
$$
where $v_h$ and $u_h$ are approximants of $v$ and $u$, $V_h \in V$ is the approximation space.

where $C$ and $\alpha$ are constants. $f: V\rightarrow \mathbb R$ is a linear form.

As $V_h \in V$, we have
$$
a(v_h,u) = f(v_h), \quad \forall v_h \in V_h
$$
With substract operation, the following **orthogenality** holds true
$$
a(u - u_h, v_h) = 0, \quad \forall v_h \in V_h
$$

# Céa inequality for Galerkin method
```ad-theorem
Suppose the bilinear form $a: V \times V \rightarrow \mathbb R$ of the above problem fulfills the continuity and coercivity, the following inequality namely Céa inequality hold true
$$
\Vert u - u_h \Vert_V \le \frac{C}{\alpha} \inf_{v_h \in V_h} \Vert u - v_h \Vert_V
$$
```
**Proof**:
$\forall v_h \in V_h$,

$$
\begin{flalign}
 & & \alpha \Vert u - u_h \Vert^2_V &\le a(u - u_h, u - u_h) & \textrm{coercivity} \\
 & & &= a(u-u_h,u-v_h) + \underbrace{a(u-u_h,v_h-u_h)}_{0} & \textrm{orthogenality} \\
 & & &\le C \Vert u-u_h \Vert_V \Vert u-v_h \Vert_V & \textrm{continuity}
\end{flalign}
$$

Therefore,
$$
\Vert u-u_h \Vert_V \le \frac{C}{\alpha} \inf_{v_h \in V_h} \Vert u-v_h \Vert
$$

# Céa inequality for generalized Galerkin method
Suppose $a: H \times H \rightarrow \mathbb R$ is a bilinear form, the continuity and coercivity should be restated, where the coercivity should split into existence and uniqueness. For $V,U \subset H$,

- **continuity**
$$
a(v,u) \le C \Vert v \Vert_H \Vert u \Vert_H, \quad \forall v \in V, \; u \in U
$$

- **coercivity**
$$
\alpha \Vert u \Vert_H \le \sup_{v \in H \setminus \{0\}} \frac{a(v,u)}{\Vert v \Vert_H}
$$

- **existence**
$$
\inf_{v \in V} \sup_{u \in U} \frac{a(v,u)}{\Vert v \Vert_H \Vert u \Vert_H} = \alpha_E > 0
$$

- **uniqueness**
$$
\inf_{u \in U} \sup_{v \in V} \frac{a(v,u)}{\Vert v \Vert_H \Vert u \Vert_H} = \alpha_U > 0
$$

Involving numerical approximation, $V_h ⊄ V$ and $U_h ⊄ U$, the orthogenality can not be maintanted now.

```ad-theorem
Suppose an unsymmetric bilinear form $a: H \times H \rightarrow \mathbb R$ fulfills the continuity and coercivity, for $u \in V$,
$$
\Vert u - u_h \Vert_H \le (1 +\frac{C}{\alpha}) \inf_{v_h \in V_h} \Vert u - v_h \Vert_H +\frac{1}{\alpha} \sup_{w_h \in V_h\setminus \{0\}} \frac{\vert a(u-u_h,w_h)\vert}{\Vert w_h \Vert_H}
$$
```
**Proof**:
For any $v_h \in V_h$
$$
\begin{flalign}
 \Vert u-u_h \Vert_H &\le \Vert u-v_h \Vert_H + \Vert v_h-u_h \Vert_H & \textrm{triangle inequality} \\
 &\le \Vert u-v_h \Vert_H +\frac{1}{\alpha} \sup_{w_h \in V_h\setminus \{0\}} \frac{\vert a(v_h-u_h,w_h)\vert}{\Vert w_h \Vert_H} & \textrm{coercivity} \\
 &\le \Vert u-v_h \Vert_H +\frac{1}{\alpha} \sup_{w_h \in V_h\setminus \{0\}} \frac{\vert a(v_h-u,w_h) \vert + \vert a(u-u_h,w_h)\vert}{\Vert w_h \Vert_H} & \textrm{triangle inequality} \\
 &\le \Vert u-v_h \Vert_H +\frac{C}{\alpha} \Vert u-v_h \Vert_H +\frac{1}{\alpha} \sup_{w_h \in V_h\setminus \{0\}} \frac{\vert a(u-u_h,w_h) \vert}{\Vert w_h \Vert_H} & \textrm{coercivity} \\
 &= (1+\frac{C}{\alpha})\Vert u-v_h \Vert_H +\frac{1}{\alpha} \sup_{w_h \in V_h\setminus \{0\}} \frac{\vert a(u-u_h,w_h) \vert}{\Vert w_h \Vert_H} & 
\end{flalign}
$$
