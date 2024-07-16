---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/lineare-algebra/determinanten/","noteIcon":""}
---

***Definition***:
Ist eine Zahl || Skalar, die einer quadratischen Matrix zugeordnet wird. Sie gibt an, wie sich das Volumen bei der durch die Matrix beschriebene linearen Abbildung verändert. Es kann als Hilfmittel zur bestimmung von Lösung definitonen dienen.

***Eigenschaften***:
- Ist eine Determinante = 0, so sind die Vektoren der Matrix linear abhängig
- Ist einen Determinante $\neq$, so sind die Vektoren linear Unäbhägig.

***Rechenregeln***:
$$\begin{align*}

	& \text{det}(\textbf{A}\cdot \textbf{B})&&=\text{det}(\textbf{A})\cdot \text{det}(\textbf{B})\\[2mm]

	& \text{det}(\textbf{A}^T)&&=\text{det}(\textbf{A})\\[2mm]

	& \text{det}(\textbf{A}^{-1})&&=\frac{1}{\text{det}(\textbf{A})}\\[2mm]

	& \text{det}(m\cdot\textbf{A})&&=m^n\cdot\text{det}(\textbf{A})\quad\text{mit}\quad m\in\mathbb{R}

\end{align*}$$

***Anwendung***:


## Regel von Sarrus
Beschreibung:
Wird nur verwendet bei Matrizen 3x3 verwendet.

$$\begin{align}

&\text{det}

\left(

\begin{matrix}

a & b & c \\

d & e & f \\

g & h & i \\

\end{matrix}\right) = aei+bfg+cdh-ceg-bdi-afh

\end{align}$$

***Beispiel***:
![Pasted image 20230214132133.png|400](/img/user/Files/Pictures/Pasted%20image%2020230214132133.png)

## Laplace Entwicklungssatz

***Definiton***
Hier wird nach einer bestimmten Zeile oder Spalte entwickelt.
$$
\begin{align}%

\text{Entweder}\quad\text{det}(\textbf{A})&=\sum_{j=1}^n\left[a_{ij}\cdot(-1)^{i+j}\cdot D_{ij}\right]\quad \text{Entwicklung nach $i$-ter Zeile}\\

\text{oder}\quad\text{det}(\textbf{A})&=\sum_{i=1}^n\left[a_{ij}\cdot(-1)^{i+j}\cdot D_{ij}\right]\quad \text{Entwicklung nach $j$-ter Spalte}

\end{align}
$$

Beispiel:
![Pasted image 20230214132622.png|500](/img/user/Files/Pictures/Pasted%20image%2020230214132622.png)
