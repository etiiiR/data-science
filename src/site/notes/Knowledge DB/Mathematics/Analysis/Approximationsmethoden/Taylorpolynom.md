---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/analysis/approximationsmethoden/taylorpolynom/","noteIcon":""}
---

### Taylorentwicklung eindimensional
Summary
![Pasted image 20230322160025.png](/img/user/Files/Pasted%20image%2020230322160025.png)

> [!Taylorreihe]
> $$ 
> T_{n}(x) = \sum\limits_{k=0}^{n} \frac{f^{k} x_{0} {k!} \cdot(x-x_{0})^{k}} = \frac{f(x_{0})}{0!} \cdot (x-x_{0}) + \frac{fx(x_{0})}{1!}\cdot (x-x_{0})^1 + \frac{fxx(x_{0})}{2!}\cdot (x-x_{0})^2 $$

### Taylorentwicklung 2. Ordnung
#### Ablauf
1. Partielle Ableitungen bis zur k-ten Ordnung bestimmen
2. Entwicklungspunkt einsetzten in die Funktion und Ableitungen

> [!Formel Taylor 2. Ordnung]
> $$ T_{2(x,y)} = f(x_0,y_{0)}+ \nabla^{}Tf(x_{0},y_{0}) \begin{bmatrix}x & -x_0 \\y & -y_0\end{bmatrix} +\frac{1}{2}\cdot\begin{bmatrix}x & -x_0 \\y & -y_0\end{bmatrix}\cdot\nabla^{2}f(x_{0},y_{0})\cdot \begin{bmatrix}x & -x_0 \\y & -y_0\end{bmatrix} $$ 



