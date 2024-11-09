#math 

[[Partielle Differentialgleichungen]] werden auf Gewöhnliche Differentialgleichungen zurückgeführt

### Separationsansatz
***
*wie Trennung der Variablen*

z.B. bei Wärmeleitungsgleichung $\partial_t u = \Delta u$ 

Es wird versucht das Argument auf die gleiche Potenz zurückzuführen (Versatz bei räumlichen Ableitungen) und anschließend eine Lösung der von diesem Argument unabhängigen Gleichung zu finden.

**Index-Shift:**
	Der Index einer Summation beginnt ursprünglich bei höheren Werten als 0. (hier weil die Terme 0 werden für die Indizes 0 und 1) Dadurch können alle Vorkommen dieses Index verändert werden um wieder eine Summation beginnend bei 0 zu erhalten.

### Fouriersche Methode
***

>$\Omega \subseteq \mathbb{R}^n$ offen, $u: [0,\infty) \times \Omega \rightarrow \mathbb{R}$ und Löse die Wärmeleitungsgleichung $\partial_t u- \Delta u = 0$.
>Es gebe einen Punkt $(t_0, x_0) \in [o,\infty) \times \mathbb{R}$ so, dass $u(t,x) = X(t)Y(x)$ für $(t,x)$ in einer Umgebung von $(t_0, x_0)$. Ist $u(t_0,x_0) \neq 0$ so erfüllen X und Y die Gleichungen $\mu X(t) = X'(t)$ und $\mu Y(x) = Y'(x)$  für $$\mu = \frac{X'(t_0)}{X(t_0)} = \frac{Y'(x_0)}{Y(x_0)}$$ für $(t,x)$ in Umgebung von $(t_0,x_0)$.

Analog für die Wellengleichung führt $u''(t,x) = \Delta u(t,x)$ auf $\mu X(t) = X''(t)$ und $\mu Y(x) = \Delta Y(x)$.
-> Wellengleichung schwingt, Wärmeleitungsgleichung wird gedämpft