---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/lineare-algebra/eigenvektoren/","noteIcon":""}
---

Defition: Ein Eigenvektor ist ein Vektor der mit einer Multiplikation einer Matrix immer noch der gleiche Vektor bleibt, jedoch gestaucht oder gestreckt wird, die Richtung bleibt bestehen. Mit dem Lösen des Eigenwert problemes sucht man alle Vektoren 

> [!Eigenwertproblem]
> $$A \cdot \vec{x} = \lambda \cdot \vec{x}, \quad \vec{x} \ne \vec{0}$$
> $$ (A - \lambda\cdot E) = \vec{0}, \quad \vec{x} \ne \vec{0} $$
> $$
> \begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix} \cdot \begin{pmatrix} x \\ y \end{pmatrix} = \lambda \cdot \begin{pmatrix} x \\ y \end{pmatrix}
> $$

### Eigenwerte Berechnen

> [!Eigenwerte berechnen]
> $$
> det(A - Id\cdot \lambda)
> $$


### Zusammenhang Eigenwerte, Spur, Determinante
$$A = \begin{bmatrix}1 & 4 \\a & b\end{bmatrix}, \begin{aligned}\lambda_{1}= 3 \\\lambda_{2}= -3 \end{aligned} $$ $$ I: SPUR (A) \sum\limits\lambda_{i} $$
$$ I: DET (A) \prod\limits\lambda_{i} $$






### Orthonomalsystem 

sei $A = \begin{pmatrix} -3 & x \\ 4 & 3 \end{pmatrix}, A=A^T$

man sehe, dass $A=A^T$ bedeuted, dass es eine Symetrische Matrix sein muss. Dementsprechend ist X = 4 -> Spiegel auf der Hauptdiagonalen

Aufgabe: Bestimmen Sie zwei Eigenwerte von A, sodass die zwei Vektoren ein Ortonormalsystem erzeugen.

EW = {5, -5}
$\vec{X_{1}}= t\begin{pmatrix} 1  \\ 2 \end{pmatrix} t \in \mathbb{R} \setminus {0}$
$\vec{X_{1}}= t\begin{pmatrix} -2  \\ 1 \end{pmatrix} t \in \mathbb{R} \setminus {0}$

Die Vektoren stehen bereits Sekrecht aufeinander, weil Symetrisch mit dem gleichen Eigenwert jedoch negiert. nun müssen die Vektoren nur noch normiert werden.

Um einen Vektor zu normieren:  [[normieren\|normieren]]