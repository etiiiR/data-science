---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/analysis/differential/differentialrechnung/","noteIcon":""}
---

### Theorie
#Ableiten #AbleitungsRegeln
### Ableitungsregeln
> [!Ableitungsregeln]
>
> In der Differentialrechnung sind Ableitungsregeln von zentraler Bedeutung, um die Ableitung einer Funktion zu bestimmen. Hier sind einige grundlegende Ableitungsregeln und Beispiele:
>
> **Grundlegende Ableitungen:**
> $$
> \begin{array}{|c|c|}
> \hline
> f(x) & f'(x) \\
> \hline
> c & 0 \\
> a \cdot x + b & a \\
> x^p & p \cdot x^{p-1} \\
> e^x & e^x \\
> a^x & a^x \cdot \ln(a) \\
> \ln(x) & 1/x \\
> \sin(x) & \cos(x) \\
> \cos(x) & -\sin(x) \\
> 2x^4 & 8x^3 \\
> \sqrt{x} & 1/(2\sqrt{x}) \\
> 1/x & -1/x^2 \\
> \hline
> \end{array}
> $$
>
> - **Größen:**
>   - $f(x)$: Funktion
>   - $f'(x)$: Ableitung der Funktion
>   - $c$: Konstante
>   - $a, b$: Konstanten
>   - $p$: Exponent
>   - $\ln$: Natürlicher Logarithmus
>   - $\sin$: Sinusfunktion
>   - $\cos$: Kosinusfunktion
>
> **Weitere Beispiele:**
> $$
> \begin{array}{|c|c|}
> \hline
> f(x) & f'(x) \\
> \hline
> 1 & 0 \\
> 3 & 0 \\
> 10 & 0 \\
> x & 1 \\
> 2x & 2 \\
> 3x & 3 \\
> 4x^2 & 8x \\
> 7x^3 & 21x^2 \\
> 2x^4 & 8x^3 \\
> x^3 - 4x + 10 & 3x^2 - 4 \\
> 2(x^2 - 4x) & 2(2x - 4) \\
> \hline
> \end{array}
> $$
>
> **Anwendung der Ableitungsregeln:**
> - Konstante Regel: Die Ableitung einer Konstante ist Null.
> - Potenzregel: Die Ableitung von $x^p$ ist $p \cdot x^{p-1}$.
> - Exponentialregel: Die Ableitung von $e^x$ ist $e^x$.
> - Logarithmusregel: Die Ableitung von $\ln(x)$ ist $1/x$.
> - Trigonometrische Regeln: Die Ableitung von $\sin(x)$ ist $\cos(x)$ und die Ableitung von $\cos(x)$ ist $-\sin(x)$.
> - Kettenregel: Wenn $y = f(u)$ und $u = g(x)$, dann ist die Ableitung von $y$ bezüglich $x$ gegeben durch $f'(u) \cdot g'(x)$.
> - Produktregel: Wenn $f(x) = u(x) \cdot v(x)$, dann ist die Ableitung $f'(x) = u'(x) \cdot v(x) + u(x) \cdot v'(x)$.
> - Quotientenregel: Wenn $f(x) = \frac{u(x)}{v(x)}$, dann ist die Ableitung $f'(x) = \frac{u'(x) \cdot v(x) - u(x) \cdot v'(x)}{(v(x))^2}$.
>
> Diese Regeln sind essentiell für die Berechnung von Ableitungen komplexer Funktionen und werden in vielen Bereichen der Mathematik und Naturwissenschaften angewendet.

### Ableitungsregeln

#### Summenregel
> [!Formel]
> $$f(x) = g(x) \pm h(x) \quad \rightarrow \quad f'(x) = g'(x) \pm h'(x)$$

#### Produkteregel
> [!Formel]
> $$f(x) = g(x) \cdot h(x) \quad \rightarrow \quad f'(x) = g'(x) \cdot h(x) + g(x) \cdot h'(x)$$

#### Quotientenregel
> [!Formel]
> $$f(x) = \frac{g(x)}{h(x)} \quad \rightarrow \quad f'(x)=\frac{h(x) \cdot g'(x) - g(x) \cdot h'(x)}{\left[h(x)\right]^2}$$

#### Kettenregel
> [!Formel]
> $$ f(x) = g(h(x)) \quad \rightarrow \quad f'(x) = g'(h(x)) \cdot h'(x) $$

### Tricks:
- Wurzeln umschreiben:
  ![Pasted image 20230221124350.png](/img/user/Files/Pictures/Pasted%20image%2020230221124350.png)

- Brüche umschreiben:
  ![Pasted image 20230221125314.png](/img/user/Files/Pictures/Pasted%20image%2020230221125314.png)
  
- Wenn X im Nenner Steht
  1) Vorzeichen mal minus
  2) Exponent des Nenners 1 erhöhen
  3) Alter Exponent mal alter Zähler

	Achtung Kettenregel beachten!!

	Beispiele:
	![Pasted image 20230221125921.png](/img/user/Files/Pictures/Pasted%20image%2020230221125921.png)



### Differenzieren
#### Grundlagen 
##### Polynome
Polynome werden so abgeleitet, dass jede einzelne Summe betrachtet wird und mittels Grundfunktionen abgeleitet wird.
![Pasted image 20230221123345.png](/img/user/Files/Pictures/Pasted%20image%2020230221123345.png)
![Pasted image 20230221123423.png](/img/user/Files/Pictures/Pasted%20image%2020230221123423.png)


