---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/analysis/jacobi-matrix/","noteIcon":""}
---

### Jacobi-Matrix
> [!Jacobi-Matrix]
>
> Die Jacobi-Matrix ist ein wichtiges Werkzeug in der Differentialrechnung, insbesondere in der Vektoranalysis. Sie enthält alle ersten partiellen Ableitungen einer Vektorfunktion und ist von zentraler Bedeutung für die Untersuchung der lokalen linearen Eigenschaften von Funktionen zwischen euklidischen Räumen.
>
> **Definition der Jacobi-Matrix:**
> Für eine Vektorfunktion $$\mathbf{f} : \mathbb{R}^n \to \mathbb{R}^m$$ mit $$ \mathbf{f}(\mathbf{x}) = \begin{pmatrix}
> f_1(\mathbf{x}) \\
> f_2(\mathbf{x}) \\
> \vdots \\
> f_m(\mathbf{x})
> \end{pmatrix}$$ ist die Jacobi-Matrix $J_{\mathbf{f}}$ gegeben durch:
> $$
> J_{\mathbf{f}}(\mathbf{x}) = \begin{pmatrix}
> \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\
> \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\
> \vdots & \vdots & \ddots & \vdots \\
> \frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n}
> \end{pmatrix}
> $$
>
> - **Größen:**
>   - $J_{\mathbf{f}}(\mathbf{x})$: Jacobi-Matrix der Funktion$ \mathbf{f}$
>   - $f_i(\mathbf{x})$: Komponentenfunktionen von$ \mathbf{f}$
>   - $\frac{\partial f_i}{\partial x_j}$: Erste partielle Ableitungen von $f_i$ nach $x_j$
>   - $\mathbf{x} = (x_1, x_2, \ldots, x_n)$: Vektor der unabhängigen Variablen
>
> **Anwendung der Jacobi-Matrix:**
> Die Jacobi-Matrix wird verwendet, um die lokale Linearität von Funktionen zu analysieren, insbesondere in der nichtlinearen Optimierung und in der Theorie der Differentialgleichungen. Sie spielt auch eine zentrale Rolle im Satz von der impliziten Funktion und im Satz von der inversen Funktion.
>
> **Beispiel:**
> Betrachten wir die Vektorfunktion $\mathbf{f} : \mathbb{R}^2 \to \mathbb{R}^2$ definiert durch:
> $$
> \mathbf{f}(x, y) = \begin{pmatrix}
> x^2 + y \\
> \sin(x) + \cos(y)
> \end{pmatrix}
> $$
>
> Die Jacobi-Matrix $ J_{\mathbf{f}} $ ist:
> $$
> J_{\mathbf{f}}(x, y) = \begin{pmatrix}
> \frac{\partial (x^2 + y)}{\partial x} & \frac{\partial (x^2 + y)}{\partial y} \\
> \frac{\partial (\sin(x) + \cos(y))}{\partial x} & \frac{\partial (\sin(x) + \cos(y))}{\partial y}
> \end{pmatrix} = \begin{pmatrix}
> 2x & 1 \\
> \cos(x) & -\sin(y)
> \end{pmatrix}
> $$
>
> - **Größen:**
>   - $ x, y $: Unabhängige Variablen
>   - $ \frac{\partial (x^2 + y)}{\partial x} = 2x $: Partielle Ableitung der ersten Komponentenfunktion nach $ x $
>   - $ \frac{\partial (x^2 + y)}{\partial y} = 1 $: Partielle Ableitung der ersten Komponentenfunktion nach $ y $
>   - $ \frac{\partial (\sin(x) + \cos(y))}{\partial x} = \cos(x) $: Partielle Ableitung der zweiten Komponentenfunktion nach $ x $
>   - $ \frac{\partial (\sin(x) + \cos(y))}{\partial y} = -\sin(y) $: Partielle Ableitung der zweiten Komponentenfunktion nach $ y $
