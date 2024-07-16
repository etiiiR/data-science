---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/lineare-algebra/abbildungen/","noteIcon":""}
---

## Lineare Abbildungen

Eine Lineare Abbildung ist definiert durch:

> [!Definition]
> ![f(\vektor{v}+\vektor{w})=f(\vektor{v})+f(\vektor{w})Mathe-Abitur](https://abiturma.de/assets/compiled-latex/1e1ceeab8714602bbb230cb759128bb238db9f21.svg "f(\vektor{v}+\vektor{w})=f(\vektor{v})+f(\vektor{w})Mathe-Abitur")
> ![f(\lambda \vektor{v})=\lambda f(\vektor{v})Mathe-Abitur](https://abiturma.de/assets/compiled-latex/aa368ee214091ee8b03d2097e80b5651dd13d35e.svg "f(\lambda \vektor{v})=\lambda f(\vektor{v})Mathe-Abitur")

### Längen treue (längentreue) Lineare Abbildungen

> [!Definition]
> 
> $$
> |\vec{v}| = |A\cdot\vec{v}|
> $$

Bekommen wir durch: $A^{T}\cdot A = E_{n}$ was auch einer Orthogonal Matrix beschreibt.





### Abbildungsmatrix bestimmen
Einstetzen der Standard Vektoren in die Abbildung

$f: \mathbb{R^{3}} \mapsto \mathbb{R^{3}} \thinspace \vert \thinspace  f(x,y,z) = \begin{bmatrix} x+2y-z \\ y + z \\ x + y - 2z \end{bmatrix}$

$f\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ = $\begin{bmatrix} 1+0+0 \\ 0+0 \\ 1 + 0 + 0 \end{bmatrix}$ = $\begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}$

$f\begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}$ = $\begin{bmatrix} 0+2+0 \\ 2+0 \\ 0 + 2 + 0 \end{bmatrix}$ =  $\begin{pmatrix} 2 \\ 2 \\ 2 \end{pmatrix}$

$f\begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ = $\begin{bmatrix} 0+0-1 \\ 0+1 \\ 0 + 0 - 2 \end{bmatrix}$ =  $\begin{pmatrix} -1 \\ 1 \\ -2 \end{pmatrix}$

**Resultat**:
$A = \begin{bmatrix} 1 & 2  & -1 \\ 0 & 2 & 1 \\ 1 & 2 & -2\end{bmatrix}$



### Kern einer Linearen Abbildung

> [!Kern Schreibweise]
> $$ker(f) = f^{-1}[{\vec{0}}]$$

Injectivität: Dass 2 verschiedene V auf W abgebildet werden.
Surjectiv: todo 

#### Kern bestimmen
1. Abbildungsmatrix bestimmen
2. Abbildungsmatrix 0 setzten
3. Mittels Gaus lösen

### Bild einer Linearen Abbildung
heisst auch Spaltenraum

#### Beispiel 
gegeben sei $f: \mathbb{R}^{2} \mapsto \mathbb{R}^{3}, mit  \begin{bmatrix} x \\ y \end{bmatrix} \mapsto \begin{bmatrix} x+y \\ x-y \\ x+y \end{bmatrix}$

$IM(f) = L(f(e1), f(e2) = L(f(\begin{bmatrix} 1 \\ 0 \end{bmatrix}), f(\begin{bmatrix} 0 \\ 1 \end{bmatrix})) = L( \begin{bmatrix} 1+0 \\ 1-0 \\ 1+0 \end{bmatrix},\begin{bmatrix} 0+1 \\ 0-1 \\ 0+1 \end{bmatrix} )$ 

#### Beispiel 2
![Pasted image 20230327134847.png](/img/user/Files/Pasted%20image%2020230327134847.png)

#### Beispiel 3 ALA
gegeben folgende Abbilungsmatrix =  $A = \begin{bmatrix} 1 & 2 & -1 \\ 0 & 1 & 1 \\ 1 & 1 & -2 \end{bmatrix}$

Spalten als Spaltenvektoren darstellen:
![Pasted image 20230327185456.png](/img/user/Files/Pasted%20image%2020230327185456.png)

Nun haben wir das Bild, jedoch mit linear Abhänigen Vektoren. Hier sieht man nicht, dass das Erzeugersystem eigentlich ein $\mathbb{R^1}$ ist anstatt ein $\mathbb{R^3}$. Deshalb lösen wir die Vektoren als Gleichungssystem:

TR: sys-solve: $\begin{bmatrix} 1 & 2 & -1 & 0 \\ 0 & 1 & 1 & 0 \\ 1 & 1 & -2 & 0\end{bmatrix}$

Lösung: 
x = 0 + 3z
y = 0 - z
z = z

Ergibt ein Vektor:
![Pasted image 20230327185957.png](/img/user/Files/Pasted%20image%2020230327185957.png)
