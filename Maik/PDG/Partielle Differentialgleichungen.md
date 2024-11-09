#math

Differentialgleichungen im Allgemeinen:
$$\frac{\partial u(t)}{\partial t} = u(t)$$
Bei partiellen Differentialgleichungen hängt die Gleichung von mehreren Parametern ab, wodurch die Möglichkeit besteht, in mehrere Dimensionen abzuleiten.
$$\frac{\partial u(t,x)}{\partial t} + \frac{\partial u(t,x)}{\partial x} = 0$$
Damit beschreibt 
$$F(x_0, \space x_1,\space...,\space x_n,\space\partial_0u,\space\partial_nu,\space\partial_{0,0}u,\space\partial_{0,1}u,...)) \quad \textrm{mit} \quad u=u(x_0,...,x_n)$$
die Differentialgleichung. Wobei jede Variable aus $\mathbb{R}$ stammt


**Ordnung:**
	Die Ordnung einer PDG ist der Wert der höchsten Ableitung, die in der Differentialgleichung vorkommt.

**Laplace Operator:**
	Der Laplace Operator fasst alle zweiten Ableitungen zusammen, bei denen beide Ableitungen in die selbe Richtung durchgeführt wurden.
	- Der Operator ignoriert meist die Zeitvariable, d.h. es werden nur Ortsvariablen betrachtet.
	- Wird die Zeit nicht als t sondern $x_0$ bezeichnet, dann wird diese Variable ebenfalls ignoriert.
- Aus der Laplacegleichung in Polarkoordinaten ergibt sich der Laplaceoperator in Polarkoordinaten: $\Delta u = u_{rr} + \frac1{r} u_r + \frac1{r^2} u_{\phi\phi}$


#### Lineare PDG:
***
$$a\space+\space\sum_{i=0}^{n}b_i \partial_iu \space+\space\sum_{i,j=0}^{n}c_{i,j} \partial_{i,j}u \space+\space ... \space=0$$
>Sind u und v Lösungen einer linearen homogenen PDG, dann sind auch $\lambda$u und u+v (und jede andere Linearkombination) Lösungen der selben PDG.

 - **Quasi Lineare PDG:** Parameter a, b, c dürfen ebenfalls von den höchsten vorkommenden Ableitungen abhängen, nur nicht von u selbst
 - für das Modul sind nur lineare PDG 2. Ordnung wichtig

###### Arten und Beispiele:

|Art|Definition|Beispiel|Formel|
|---|---|---|---|
|parabolisch|genau ein Eigenwert ist 0, der Rest hat dasselbe Vorzeichen|Wärmeleitungsgleichung|$\partial_tu = \Delta u$|
|elliptisch|alle Eigenwerte haben dasselbe Vorzeichen|Laplace-Gleichung|$\Delta u = 0$|
|hyperbolisch|genau ein Eigenwert hat ein von den anderen verschiedenes Vorzeichen|Wellengleichung|$\partial_{tt}u = \Delta u$|
- Eigenwerte beziehen sich auf die Matrix der Koeffizienten für zweite Ableitungen.

###### Wärmeleitungsgleichung
***
$$\partial_t u - k\Delta u = f$$
ohne die Inhomogenität f: $\partial_t u = \Delta u$ 
-> siehe Notizen Seiten 3 und 4

###### Wellengleichung
***
$$\partial_{tt} u -\Delta u = f(x)$$
###### Maxwellgleichungen
***
-> siehe [[Maxwellgleichungen]]

###### partielle DGL der Strömungsmechanik
***
**Eulersche Gleichungen:** 
$$\partial_{t} v + (v \cdot grad)v + \frac1{\rho}grad \space p = k$$
die Eulerschen Gleichungen stellen einen Bezug zwischen dem Druck p und dem Geschwindigkeitsfeld v her. Durch den Term v² sind diese jedoch nicht mehr linear. Sie sind ein Spezialfall der Navier-Stokes-Gleichung für $\varepsilon = 0$
$$\partial_{t} v + (v \cdot grad)v + \frac1{\rho}grad \space p - \varepsilon \Delta v = k$$

###### Laplace Gleichung
***
-> siehe [[Laplace-Gleichung]]


#### Lösen von PDE
***
>Eine PDE heißt wohlgestellt wenn folgendes erfüllt ist:
>1. zu jedem Anfangswert (*datum*) existiert eine Lösung
>2. die Lösung ist eindeutig
>3. ändert sich das Anfangsdatum gering ändert sich auch die Lösung nur gering (Stetigkeit)

###### Arten von Daten
***
**Anfangsbedingungen:**
	Anfangsbedingungen gelten zu Beginn oder am Ende (*Endbedingungen*) des zu modellierenden Zeitintervalls und im gesamten Gebiet $\Omega$ 
	Es werden immer so viele AB benötigt wie die Ordnung der Zeitableitungen.
$$u(t,x) \Rightarrow u(0,x) = u_0(x)$$

**Randbedingungen:**
	Randbedingungen gelten zu jeder Zeit am Rand des Gebiets $\Omega$. Es werden jeweils so viele RB benötigt wie die Ordnung Ortsableitungen.

- Dirichlet-RB:      $u|_{\partial \Omega}(x) = g(x)$ 
	- feste Werte auf $\partial \Omega$ 

- Neumann-RB:   $(\nu\cdot\nabla u)|_{\partial \Omega}(x) = g(x)$
	- Gradient auf $\partial \Omega$, $\nu$ ist die normierte Normalableitung und zeigt nach außen
	- homogene RB zweiter Art ( $g(x) = 0$ ) beschreiben Reflexionen

- Robin-RB:          $(\nu\cdot\nabla u)|_{\partial \Omega}(x) + k(x) \cdot u|_{\partial \Omega}(x)= g(x)$
	- $k(x)$ ist Funktion auf $\partial \Omega$ 

- periodische Randbedingungen:   $u(t,0) = u(t,2\pi-)$, $u_\varphi(t,0) = u_\varphi(t,2\pi-)$
	- anwendbar auf innen verbundene Systeme, die für die Modellierung geteilt werden mussten (z.B. Ring in $[0,2\pi)$)

**Verträglichkeitsbedingungen:**
	Auf dem *Raum-Zeit-Zylinder* sind AB Bedingungen des Bodens und RB des Mantels. Damit kein Konflikt entsteht muss eine Vertäglichkeitsbedingung auf dem Rand der AB erfüllt sein, damit die Lösung stetig ist. Häufig ist diese Bedingung nicht relevant, da die Lösungen nicht stetig sind.
$$u_0|_{\partial \Omega}(x)= g(x)$$
