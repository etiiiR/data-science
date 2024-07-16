---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/analysis/funktionen-mit-mehreren-variablen/","noteIcon":""}
---

### Hesse-Matrix und Determinantenanalyse
> [!Hesse-Matrix und Determinantenanalyse]
>
> Die Hesse-Matrix ist ein Werkzeug in der Analysis, das verwendet wird, um das Verhalten einer Funktion an kritischen Punkten zu analysieren. Sie besteht aus den zweiten partiellen Ableitungen der Funktion und hilft dabei, das Vorhandensein von Maxima, Minima oder Sattelpunkten zu bestimmen.
>
> **Hesse-Matrix Definition:**
> $$
> H_f = \begin{pmatrix}
> f_{xx} & f_{xy} \\
> f_{yx} & f_{yy}
> \end{pmatrix}
> = \begin{pmatrix}
> a & b \\
> b & c
> \end{pmatrix}
> $$
>
> - **Größen:**
>   - $H_f$: Hesse-Matrix
>   - $f_{xx}, f_{yy}$: Zweite partielle Ableitungen von $f$ nach $x$ bzw. $y$
>   - $f_{xy}, f_{yx}$: Gemischte zweite partielle Ableitungen
>   - $a, b, c$: Elemente der Hesse-Matrix
>
> **Determinantenanalyse:**
> Der Determinant der Hesse-Matrix hilft dabei, die Natur der kritischen Punkte zu bestimmen.
>
> **Determinantenregel:**
> $$
> \det(H_f) = ac - b^2
> $$
>
> **Analyse der Determinante:**
> - Wenn $\det(H_f) > 0$:
>   - Wenn $a > 0$: Lokales Minimum (positiv definit, konvex)
>   - Wenn $a < 0$: Lokales Maximum (negativ definit, konkav)
> - Wenn $\det(H_f) < 0$: Sattelpunkt (indefinit)
> - Wenn $\det(H_f) = 0$:
>   - Weiteres Testen erforderlich (positiv semidefinit oder negativ semidefinit)
>
> - **Größen:**
>   - $\det(H_f)$: Determinante der Hesse-Matrix
>   - $a, c$: Elemente der Hesse-Matrix, die die zweiten partiellen Ableitungen darstellen
>   - Sattelpunkt (SP)
>
> **Beispiel:**
> Betrachten wir eine Funktion $f(x, y)$ mit den folgenden zweiten partiellen Ableitungen:
> $$
> f_{xx} = 2, \quad f_{yy} = 3, \quad f_{xy} = 1
> $$
>
> Die Hesse-Matrix ist:
> $$
> H_f = \begin{pmatrix}
> 2 & 1 \\
> 1 & 3
> \end{pmatrix}
> $$
>
> Die Determinante der Hesse-Matrix ist:
> $$
> \det(H_f) = 2 \cdot 3 - 1^2 = 6 - 1 = 5
> $$
>
> Da $\det(H_f) > 0$ und $f_{xx} = 2 > 0$, hat die Funktion ein lokales Minimum an diesem kritischen Punkt.



### Konvex / Konkav
![Pasted image 20230327213148.png](/img/user/Files/Pasted%20image%2020230327213148.png)
