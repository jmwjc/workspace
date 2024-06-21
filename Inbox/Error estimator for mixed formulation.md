---
Icon: OcInfinity 16
---

#Formulation/Galerkin #Math/FunctionalAnalysis 

![[Error estimator for Galerkin method]]

# Mixed formulation

For mixed formulation, the variational problem is given as follows
$$
\begin{split}
a(v,u) + b(v,p) &= f(v),\quad \forall v \in V \\
b(u,q) + c(q,p) &= g(q),\quad \forall q \in Q
\end{split}
$$
the bilinear form $a: V \times V \rightarrow \mathbb R$ and $b: V \times Q \rightarrow \mathbb R$ also meet their continuity and coercivity as follows

- **continuity**
$$
\begin{align}
&a(v,u) \le C \Vert v \Vert_V \Vert u \Vert_V, \quad \forall v,u \in V \\
&b(v,q) \le C \Vert v \Vert_V \Vert q \Vert_Q, \quad \forall v \in V,\; q \in Q
\end{align}
$$

- **coercivity**
$$
a(u,u) \le \Vert u \Vert_V^2, \quad \forall u \in V
$$
or
$$
\alpha \Vert v \Vert_V \le \sup_{v \in V \setminus \{0\}} \frac{a(w,v)}{\Vert w \Vert_V},\quad \forall v \in V
$$
- **inf-sup condition**
$$
\inf_{q\in Q} \sup_{v \in V} \frac{b(v,q)}{\Vert q \Vert_Q \Vert v \Vert_V} \ge \beta
$$
or
$$
\beta \Vert q \Vert_Q \le \sup_{v \in V} \frac{b(v,q)}{\Vert v \Vert_V},\quad \forall q \in Q
$$

# Céa theorem for mixed-formulation

For $g(q)=0,\; \forall q \in Q$, the variational problem mixed formulation becomes an equvalient problem as follow
$$
\textrm{find} \; u_h \in Z^0_h \quad a(v_h,u_h) = f(v_h), \quad \forall v_h \in Z^0_h
$$
where $Z^0_h = \ker P_h \subset V_h$. Under this circumstance, the bilinear form cover the continuity, coercivity and orthogonality on space $Z^0_h$, thus the following Céa inequality should be held true
$$
\Vert u-u_h \Vert_V \le \frac{C}{\alpha} \inf_{w_h \in Z^0_h}\Vert u-w_h \Vert_V
$$
Furthermore, let $v_h \in V_h$,
$$
\beta = \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h)}{\Vert w_h-v_h \Vert_V \Vert q_h \Vert_Q} \Rightarrow
\Vert w_h-v_h \Vert_V =\frac{1}{\beta} \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h)}{\Vert q_h \Vert_Q}
$$
As $u, w_h\in Z^0_h$,
$$
b(u-w_h,q_h) = 0
$$
$$
\begin{split}
\Vert v_h - w_h \Vert_V &=\frac{1}{\beta} \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h)}{\Vert q_h \Vert_Q} \\
&=\frac{1}{\beta} \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h) + b(u-w_h,q_h)}{\Vert q_h \Vert_Q} \\
&=\frac{1}{\beta}\inf_{q_h \in Q_h} \frac{b(u-v_h,q_h)}{\Vert q_h \Vert_Q} \\
&\le\frac{C}{\beta} \Vert u-v_h \Vert_V
\end{split}
$$
Thus,
$$
\Vert u-w_h \Vert_V \le \Vert u-v_h \Vert_V + \Vert v_h-w_h \Vert_V \le (1+\frac{C}{\beta})\Vert u-v_h \Vert_V
$$
Finally,
$$
\Vert u-u_h \Vert_V \le \frac{C}{\alpha} \inf_{w_h \in Z_h}\Vert u-w_h \Vert_V\le \frac{C}{\alpha} (1+\frac{C}{\beta}) \inf_{v_h \in V_h} \Vert u-v_h \Vert_V
$$
For $g(q)\ne0,\; \forall q \in Q$, and the space $Z^g_h$ as follows
$$
Z^g_h = \{v_h \in V_h \; \vert \; b(v_h,q_h)=g(q_h), \; \forall q_h \in Q_h\}
$$
The problem of variational problem becomes
$$
\textrm{find}\; u^0_h = u_h-u^g_h \in Z^0_h, \quad a(v_h,u^0_h) = f(v_h) - a(v_h,u^g_h), \quad \forall v_h \in Z^0_h
$$
where
$$
b(u^0_h,q_h) = b(u_h-u^g_h,q_h) = 0 \Rightarrow
b(u_h,q_h) = b(u^g_h,q_h) = g(q_h), \quad \forall q_h \in Q_h
$$
Then, the coercivity for bilinear form turns to that, for $v_h \in Z^g_h$,
$$
\alpha \Vert v_h \Vert_V \le \sup_{w_h \in Z^0_h} \frac{a(v_h,w_h)}{\Vert w_h \Vert_V}
$$
$$
\Vert u-u_h \Vert_V \le (1+\frac{C}{\alpha}) \inf_{v_h \in Z^g_h}\Vert u-v_h \Vert_V + \frac{1}{\alpha}\sup_{w_h \in Z^0_h} \frac{\vert a(u-u_h,w_h) \vert}{\Vert w_h \Vert_V}
$$
Since the following relation held true
$$
a(v_h,u) + b(v_h,p) = f(v_h),\quad \forall v_h \in Z^0_h
$$
$$
b(v_h,q_h)=0,\quad \forall v_h \in Z^0_h,\; \forall q_h \in Q_h
$$
such that
$$
a(v_h,u-u_h) + b(v_h,p-q_h) = 0,\quad \forall v_hh \in Z^0_h, \forall q_h \in Q_h
$$
$$
\begin{split}
\sup_{w_h \in Z^0_h} \frac{\vert a(u-u_h,w_h)\vert}{\Vert w_h \Vert_V} &= \sup_{w_h \in Z^0_h} \frac{\vert b(w_h,p-q_h)\vert}{\Vert w_h \Vert_V} \\
&\le C \Vert p-q_h \Vert_Q
\end{split}
$$
Furthermore, let $v_h \in V_h$,
$$
\beta = \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h)}{\Vert w_h-v_h \Vert_V \Vert q_h \Vert_Q} \Rightarrow
\Vert w_h-v_h \Vert_V =\frac{1}{\beta} \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h)}{\Vert q_h \Vert_Q}
$$
As $u, w_h\in Z^g_h$,
$$
b(u-w_h,q_h) = 0
$$
$$
\begin{split}
\Vert v_h - w_h \Vert_V &=\frac{1}{\beta} \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h)}{\Vert q_h \Vert_Q} \\
&=\frac{1}{\beta} \inf_{q_h \in Q_h} \frac{b(w_h-v_h,q_h) + b(u-w_h,q_h)}{\Vert q_h \Vert_Q} \\
&=\frac{1}{\beta}\inf_{q_h \in Q_h} \frac{b(u-v_h,q_h)}{\Vert q_h \Vert_Q} \\
&\le\frac{C}{\beta} \Vert u-v_h \Vert_V
\end{split}
$$
Thus,
$$
\Vert u-w_h \Vert_V \le \Vert u-v_h \Vert_V + \Vert v_h-w_h \Vert_V \le (1+\frac{C}{\beta})\Vert u-v_h \Vert_V
$$
Finally,
$$
\begin{split}
\Vert u-u_h \Vert_V &\le (1+\frac{C}{\alpha}) \inf_{v_h \in Z^g_h}\Vert u-v_h \Vert_V + \frac{1}{\alpha}\sup_{w_h \in Z^0_h} \frac{\vert a(u-u_h,w_h) \vert}{\Vert w_h \Vert_V} \\
&=(1+\frac{C}{\alpha})(1+\frac{C}{\beta}) \Vert u-v_h \Vert_V +\frac{C}{\alpha}\Vert p-q_h \Vert_Q
\end{split}
$$
