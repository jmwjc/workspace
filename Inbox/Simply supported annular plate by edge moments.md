---

---

#Elasticity/Plate/Thin-plate #Example

$$
w = \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}\ln \frac{r}{a} + \frac{m_i b^2 - m_o a^2}{2\bar D(1+\nu)(a^2-b^2)}(r^2-a^2)
$$
$$
\left \{
\begin{split}
w_{,x} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}\frac{x}{x^2+y^2} + \frac{m_i b^2 - m_o a^2}{\bar D(1+\nu)(a^2-b^2)} x \\
w_{,y} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}\frac{y}{x^2+y^2} + \frac{m_i b^2 - m_o a^2}{\bar D(1+\nu)(a^2-b^2)} y \\
\end{split}
\right .
$$
$$
\left \{
\begin{split}
w_{,xx} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(-2\frac{x^2}{(x^2+y^2)^2}+\frac{1}{x^2+y^2}) + \frac{m_i b^2 - m_o a^2}{\bar D(1+\nu)(a^2-b^2)} \\
w_{,xy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(- \frac{2xy}{(x^2+y^2)^2}) \\
w_{,yy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(-2\frac{y^2}{(x^2+y^2)^2}+\frac{1}{x^2+y^2}) + \frac{m_i b^2 - m_o a^2}{\bar D(1+\nu)(a^2-b^2)} \\
\end{split}
\right .
$$
$$
\left \{
\begin{split}
w_{,xxx} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(\frac{8x^3}{(x^2+y^2)^3}-\frac{6x}{(x^2+y^2)^2}) \\
w_{,xxy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(\frac{8x^2y}{(x^2+y^2)^3}-\frac{2y}{(x^2+y^2)^2}) \\
w_{,xyy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(\frac{8xy^2}{(x^2+y^2)^3}-\frac{2x}{(x^2+y^2)^2}) \\
w_{,yyy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(\frac{8y^3}{(x^2+y^2)^3}-\frac{6y}{(x^2+y^2)^2}) \\
\end{split}
\right .
$$
$$
\left \{
\begin{split}
w_{,xxxx} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(-\frac{48x^4}{(x^2+y^2)^4}+\frac{48x^2}{(x^2+y^2)^3}-\frac{6}{(x^2+y^2)^2}) \\
w_{,xxyy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(-\frac{48x^2y^2}{(x^2+y^2)^4}+\frac{8x^2}{(x^2+y^2)^3}+\frac{8y^2}{(x^2+y^2)^3}-\frac{2}{(x^2+y^2)^2}) \\
w_{,yyyy} &= \frac{(m_i-m_o)a^2b^2}{\bar D(1-\nu)(a^2-b^2)}(-\frac{48y^4}{(x^2+y^2)^4}+\frac{48y^2}{(x^2+y^2)^3}-\frac{6}{(x^2+y^2)^2}) \\
\end{split}
\right .
$$
