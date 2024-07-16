---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/lineare-algebra/basis-transformation/","noteIcon":""}
---

#### Beispiel
gegeben: $A =  \Biggl\lbrace \begin{bmatrix} 5 \\ -2 \\ 0 \end{bmatrix} ,\begin{bmatrix} 4 \\ -2 \\ -1 \end{bmatrix} \Biggr\rbrace$

gegeben: $B =  \Biggl\lbrace \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix} -2 \\ 2 \\ 3 \end{bmatrix} \Biggr\rbrace$

$T_{A \mapsto B}$ : Mittels Gauss lösen der beiden Basen

![Pasted image 20230327170546.png](/img/user/Files/Pasted%20image%2020230327170546.png)

> [!Basistransformation umkehren]
> $T_{B \mapsto A} = T^{-1}_{A \mapsto B}$

$$
A\cdot x = \begin{pmatrix} 1 & 1 \\ -1 & 2  \end{pmatrix} \cdot \begin{pmatrix} 1 \\ 3 \end{pmatrix} = \begin{pmatrix} 4 \\ 5 \end{pmatrix} =y
$$
$$
B = {\begin{pmatrix} 1\\1 \end{pmatrix}} , \begin{pmatrix} 1 \\ -1 \end{pmatrix}
$$