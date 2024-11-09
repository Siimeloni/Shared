#math 

homogen:      $\Delta u = 0$
inhomogen:   $\Delta u = f$

in Polarkoordinaten: $r^2u_{rr} + u_{\phi\phi} + ru_r = r^2 \Delta u$

*Fundamentallösungen* lösen die homogene Laplace-Gleichung bis auf in einem Punkt. Zur Lösung der inhomogenen Gleichung wird die Fundamentallösung $u$ mit f gefalten: 
$$(u \ast f)(x) = \int u(x-y)\space f(y) \space dy$$
>Sei $f: \mathbb{R}^3 \to \mathbb{R}$ geeignet (stetig genug) und $f = 0$ in $\mathbb{R}^3 \backslash B(0,R)$, dann löst $v = u \ast f$ die Laplace-Gleichung $\Delta v = f$ in B(0,R)  und $\Delta v = 0$ in $\mathbb{R}^3 \backslash B(0,R)$.

