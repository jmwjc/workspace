---
icon: OcInfinity16
---
#Formulation/Dynamic #Math 

Consider the following mass-spring-damper system:
$$
m\ddot u + c \dot u + ku = f
$$
or
$$
\begin{cases}
a = \frac{1}{m}(f-c v + ku) \\
\dot u = v \\
\dot v = a
\end{cases}
$$
Using extended mean value theorem, the velocity can be solved as:
$$
v_{n+1} = v_n + \Delta t a_\gamma
$$
$$
a_\gamma = v_n + (1-\gamma) \Delta t a_n + \gamma \Delta t a_{n+1}
$$
$$
v_{n+1} = v_n + (1-\gamma)\Delta t a_n + \gamma \Delta t a_{n+1}
$$
Again, introducing extended mean value theorem to correct displacement:
$$
u_{n+1} = u_n + \Delta t v_n + \frac{1}{2} \Delta t^2 a_\beta
$$
$$
a_\beta = (1-2\beta)a_{n+1} + 2\beta a_{n+1}, \quad 0 \le 2\beta \le 1
$$
Finally, the Newmark-β formulation becomes:
$$
\begin{cases}
a_{n+1} = \frac{1}{m}(f_{n+1} - c v_{n+1} - k u_{n+1}) \\
v_{n+1} = v_{n} + \Delta t ((1-\gamma)a_n + \gamma a_{n+1})\\
u_{n+1} = u_n + \Delta t v_n + \frac{1}{2}\Delta t^2((1-2\beta)a_n + 2\beta a_{n+1})\\
\end{cases}
$$
**Flowchart**
1. For $n=0$
$$
a_{0} = \frac{1}{m}(f_0 - c v_0 - k u_0)
$$
2. For $t=t_{n+1}$, give $u_n, \dot u_n, \ddot u_n, f_{n+1}$, compute the predict phase
$$
\begin{cases}
\tilde v_{n+1} = v_{n} + \Delta t (1-\gamma)a_n\\
\tilde u_{n+1} = u_n + \Delta t v_n + \frac{1}{2}\Delta t^2(1-2\beta)a_n\\
\end{cases}
$$
3. Compute acceleration
$$
a_{n+1} = \frac{1}{m+\gamma c \Delta t + \beta k \Delta t^2}(f_{n+1} - c \tilde v_{n+1} - k \tilde u_{n+1})
$$
4. Compute correct phase
$$
\begin{cases}
v_{n+1} = \tilde v_{n+1} + \gamma \Delta t a_{n+1} \\
u_{n+1} = \tilde u_{n+1} + \beta \Delta t^2 a_{n+1} \\
\end{cases}
$$

# Explicit Euler
$$
\begin{cases}
a_{n} = \frac{1}{m}(f_{n} - c v_n - k u_n) \\
v_{n+1} = v_n + \Delta t a_{n} \\
u_{n+1} = u_n + \Delta t v_n
\end{cases}
$$

# Semi-implicit Euler
$$
\begin{cases}
a_{n+1} = \frac{1}{m}(f_{n+1} - c v_{n+1} - k u_n) \\
v_{n+1} = v_n + \Delta t a_{n+1} \\
u_{n+1} = u_n + \Delta t v_{n+1}
\end{cases}
$$

# Implicit Euler
$$
\begin{cases}
a_{n+1} = \frac{1}{m}(f_{n+1} - c v_{n+1} - k u_{n+1}) \\
v_{n+1} = v_n + \Delta t a_{n+1} \\
u_{n+1} = u_n + \Delta t v_{n+1}
\end{cases}
$$
