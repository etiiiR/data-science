---
{"dg-publish":true,"permalink":"/knowledge-db/mathematics/analysis/differential/partielle-ableitung/","noteIcon":""}
---

### Defnition
> [!schreibweise Ableitungen 1. Ordnung]
> $$ f_x = \frac{\partial f}{\partial x} \qquad f_y = \frac{\partial f}{\partial y} $$

> [!Schreibweise Abletiung 2. Ordnung]
> $$ f_{xx} = \frac{\partial^2 f}{\partial x^2} \qquad f_{xy} = \frac{\partial^2 f}{\partial x\partial y} $$

### Gradient und Hessematrix
Der Gradient ist die erste Ableitung und die Hessematrix die 2. Abeleitung.


### Differenzierung von Partiellen Funktionen
![Pasted image 20230221115141.png](/img/user/Files/Pictures/Pasted%20image%2020230221115141.png)

### Totales Differential 
Gibt die gesammte änderung der Funktion an, wenn ich die Variable in die Funktion hereingebe und was sich ändert.

- Bei zwei Variablen:

$$ df = fx \cdot dx + fy \cdot dy  $$
- Formel bei n Variblen:
$$ df = \sum_{i=1}^{n}fx_{i} \cdot dx_i $$

- Beispiel:
	- ***Gegeben***: ![Pasted image 20230228224729.png](/img/user/Files/Pictures/Pasted%20image%2020230228224729.png)
	- Totales Differential:
	  ![Pasted image 20230228224753.png](/img/user/Files/Pictures/Pasted%20image%2020230228224753.png)


### Richtungsableitung 
gegeben:
$$$f(x,y) = \frac {\sqrt[3]{y-1}}{X} = \frac{(y-1)^\frac{1}{3}}{X}$$
gradienten:

Fromel:
![Pasted image 20230305160821.png](/img/user/Files/Pasted%20image%2020230305160821.png)

### Tangentialebene 

***Definition***:: Ist eine Ebene die, die Funktion in den Punkten  f(x0, y0) berührt.

#### Tangentialebene aufstellen:
Schritte:
   
1) Du brauchst eine Funktion
2) Du brauchst nun von dieser Funktion alle Ableitungen sprich den Gradienten [[Knowledge DB/Mathematics/Analysis/Differential/Partielle Ableitung#Gradient und Hessematrix\|Partielle Ableitung#Gradient und Hessematrix]]
3) Du brauchst einen Punkt X0 und Y0 
4) Formel anwenden: $Z =(x_{0,}y_{0}) + fx(x_{0}, y_{0}) \cdot (x-x_{0}) + fy(x_{0},y_{0}) \cdot (y-y_0)$ ![Pasted image 20230228231455.png](/img/user/Files/Pictures/Pasted%20image%2020230228231455.png)

##### Beispielsrechnung
Gegeben:![Pasted image 20230228230717.png](/img/user/Files/Pictures/Pasted%20image%2020230228230717.png)
Gradienten: ![Pasted image 20230228230742.png](/img/user/Files/Pictures/Pasted%20image%2020230228230742.png)
Formel anwenden, zahlen in funktion einsetzten und in ableitungen:
Lösung: ![Pasted image 20230228231736.png](/img/user/Files/Pictures/Pasted%20image%2020230228231736.png)
Jetzt noch Ebenen Gleichung in Normalform bringen [[Knowledge DB/Mathematics/Lineare Algebra/Vektoren#Normalform:\|Vektoren#Normalform:]]:
1) Klammern auflösen:![Pasted image 20230228231952.png](/img/user/Files/Pictures/Pasted%20image%2020230228231952.png)
2) Konstante Zahlen nun noch zusammenfassen (Normalform):![Pasted image 20230228232056.png](/img/user/Files/Pictures/Pasted%20image%2020230228232056.png)
Fun fact:
Der Normalenvektor der senkrecht auf der Ebenen steht, besteht aus den Folgenden kompoenenten 
![Pasted image 20230228232150.png](/img/user/Files/Pictures/Pasted%20image%2020230228232150.png)

### Partielle Elastizität 

### Höhenlinien 
Die Funktion einfach constant setzten und nach Y aufloesen:
![Pasted image 20230322155723.png](/img/user/Files/Pasted%20image%2020230322155723.png)

![Pasted image 20230322155813.png](/img/user/Files/Pasted%20image%2020230322155813.png)

### Implizites Differenzieren 

### Homogentiätsgrad bestimmen 

### Extrema / Stationäre / Kritische Punkte 

### Definitheit bestimmen (Sylvesterkriterium) 

### Definitheit Hessematrix (Tricks) 

### Extrema unter Nebenbedinnungen 

### Beispiele 
1 = Gradient
2 = Totales Differential
3 = Tangentialebene
4 = Richtungsableitung
5 = Partielle Elasitzität
![Pasted image 20230311163437.png](/img/user/Files/Pasted%20image%2020230311163437.png)

### Aufgaben Mathe Peter 
#### Gradient / Hessematrix
##### Aufgabe 1
Gegeben:
![Pasted image 20230519194337.png](/img/user/Files/Documents/Pasted%20image%2020230519194337.png)
Lösung:
![Pasted image 20230519195820.png](/img/user/Files/Documents/Pasted%20image%2020230519195820.png)
##### Aufgabe 2
Gegeben:
![Pasted image 20230519201215.png](/img/user/Files/Documents/Pasted%20image%2020230519201215.png)

Lösung:
![Pasted image 20230519201147.png](/img/user/Files/Documents/Pasted%20image%2020230519201147.png)
##### Aufgabe 3

Gegeben:
![Pasted image 20230519201300.png](/img/user/Files/Documents/Pasted%20image%2020230519201300.png)
Lösu
ng:
![Pasted image 20230519202620.png](/img/user/Files/Documents/Pasted%20image%2020230519202620.png)

#### Totales Differential, Tangentialebene, Richtungsableitung, Elastizität
##### Aufgabe 1
Gegeben:
![Pasted image 20230519202708.png](/img/user/Files/Documents/Pasted%20image%2020230519202708.png)
Lösung:
![Pasted image 20230523153143.png](/img/user/Files/Documents/Pasted%20image%2020230523153143.png)
![Pasted image 20230523153232.png](/img/user/Files/Documents/Pasted%20image%2020230523153232.png)

##### Aufgabe 2
![Pasted image 20230523155320.png](/img/user/Files/Documents/Pasted%20image%2020230523155320.png)
![Pasted image 20230523155305.png](/img/user/Files/Documents/Pasted%20image%2020230523155305.png)
##### Aufgabe 3
![Pasted image 20230523204008.png](/img/user/Files/Documents/Pasted%20image%2020230523204008.png)
