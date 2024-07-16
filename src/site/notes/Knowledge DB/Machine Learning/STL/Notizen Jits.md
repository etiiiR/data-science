---
{"dg-publish":true,"permalink":"/knowledge-db/machine-learning/stl/notizen-jits/","noteIcon":""}
---


### Header
All videos:
[(254) StatsLearning Lecture 1 - part1 - YouTube](https://www.youtube.com/watch?v=5N9V07EIfIg&list=PLOg0ngHtcqbPTlZzRHA2ocQZqB1D_qZ5V&index=1)
## Book: 

![[ISLP_websit__ISLP_website__e 1.pdf\|ISLP_websit__ISLP_website__e 1.pdf]]

![[ISLP_website (1).pdf]]






## Statistical Learning
### Overview of Statistical Learning
> [!Overview of Statistical Learning]
> 
> Statistical Learning umfasst Werkzeuge zur Datenanalyse. Es gibt zwei Haupttypen: supervised und unsupervised learning.

### Supervised Learning
Was ist der Unterschied zwischen Regression und Classification?
?
> [!Supervised Learning]
> 
> Supervised Learning baut Modelle zur Vorhersage von Outputs \(Y\) aus Inputs \(X\):
> 
> **Regression:** Vorhersage eines quantitativen Outputs.
> 
> **Classification:** Vorhersage eines qualitativen Outputs.

### Unsupervised Learning
> [!Unsupervised Learning]
> 
> Unsupervised Learning bestimmt Beziehungen aus Inputs \(X\), ohne supervisierte Outputs:
> 
> **Clustering:** Gruppierung basierend auf Ähnlichkeiten.
> 
> **Association:** Identifizierung von Regeln in Daten.


## Lineare Regression
Was sind die Fehler Komponenten der STL
?
> [!Lineare Regression und Fehlerkomponenten]
> 
> Das Hauptproblem ist, dass wir \(Y\) und \(X\) kennen, jedoch nicht die wahre Funktion \(f\):
> 
> $$
> Y = f(X) + \epsilon
> $$
> 
> \(\epsilon\) ist dabei das Rauschen bzw. der Messfehler.
> 
> Wir wollen eigentlich die Approximation herausfinden:
> 
> $$
> \hat{Y} = \hat{f}(X)
> $$
> 
> Warum schreibt man hier $(X)$  und $(Y)$ groß $(Y = f(X) + \epsilon)$? :: Weil \(Y\) und \(X\) Zufallsvariablen aus der Stochastik sind.
> 
> - Welcher ist der reduzierbare Fehler? :: $([f(X) - \hat{f}(X)]^2$)
> - Welcher Fehler ist der irreduzible Fehler? :: $(\text{Var}(\epsilon)$)


Was ist die Bias Varianz Zerlegung
?
> [!Bias-Varianz-Zerlegung]
>
> Die Bias-Varianz-Zerlegung hilft dabei, den erwarteten quadratischen Fehler einer Vorhersage zu verstehen. Sie teilt den Fehler in reduzierbare und irreduzierbare Komponenten auf. Der reduzierbare Fehler kann durch Verbesserung des Modells verringert werden, während der irreduzierbare Fehler durch Zufallsrauschen verursacht wird und nicht eliminiert werden kann.
>
> $$
> \begin{aligned}
>     \mathbb{E}(Y - \hat{Y})^2 &= \mathbb{E}[f(X) + \epsilon - \hat{f}(X)]^2 \\
>     &= \underbrace{[f(X) - \hat{f}(X)]^2}_{\text{Reducible}} + \underbrace{\text{Var}(\epsilon)}_{\text{Irreducible}}
> \end{aligned}
> $$
> - $\mathbb{E}$ ist der Erwartungswert
> - $Y$ ist die tatsächliche Zielvariable
> - $\hat{Y}$ ist die vorhergesagte Zielvariable
> - $f(X)$ ist die wahre Funktion
> - $\hat{f}(X)$ ist die vorhergesagte Funktion
> - $\epsilon$ ist der irreduzible Fehler (Rauschen)
> - $\text{Var}(\epsilon)$ ist die Varianz des irreduziblen Fehlers

Hier ist die Notiz zur Bias-Varianz-Zerlegung der mittleren quadratischen Fehlers:

> [!Bias-Varianz-Zerlegung]
> 
> Die Bias-Varianz-Zerlegung ist ein Konzept in der Statistik, das die erwartete quadratische Abweichung eines Schätzers \(\hat{f}(x_0)\) von einem tatsächlichen Wert \(y_0\) in drei Komponenten zerlegt:
> 
> $$
> \mathbb{E} \left( y_0 - \hat{f}(x_0) \right)^2 = \text{Var}(\hat{f}(x_0)) + \left[ \text{Bias}(\hat{f}(x_0)) \right]^2 + \text{Var}(\epsilon)
> $$
> 
> - ($\mathbb{E} \left( y_0 - \hat{f}(x_0) \right)^2$: Erwartete quadratische Abweichung
> - $\text{Var}(\hat{f}(x_0))$: Varianz des Schätzers
> - $\left[ \text{Bias}(\hat{f}(x_0)) \right]^2$: Quadrat des Bias des Schätzers
> - $\text{Var}(\epsilon)$: Varianz des irreduziblen Fehlers

Es gibt 2 Ansätze für die Regression welche?
?
1. Parametrische Methode (eg. Lineare Regression) -> Hat eine starke induktive Bias, ist aber sehr effizient mit nur ein paar Parameter
2. nicht Parametrische Modelle (e.g KNN -> Gesetzt der Kontinuität, ) -> Flexibler, Können sich viel besser an Daten anpassen, kann aber schnell overfitten



Wie sehen die Tradoffs von Modellen?
?
![Pasted image 20240624205502.png](/img/user/Files/Pasted%20image%2020240624205502.png)

Was ist der Bias :: zu viel BIAS ist undefitting

Was ist der Variance :: zu viel Variance is overfitting


Was ist der Bias Variance Trade off
?
> [!Bias-Varianz-Zerlegung]
>
> Die Bias-Varianz-Zerlegung beschreibt, wie die Erwartung des quadratischen Fehlers einer Vorhersage durch die Varianz der Vorhersage, den Bias der Vorhersage und die Varianz des irreduziblen Fehlers beeinflusst wird. Diese Zerlegung hilft, die Fehlerquellen eines Modells zu analysieren und zu verstehen.
>
> $$
> \begin{aligned}
>     \mathbb{E} \left( y_0 - \hat{f}(x_0) \right)^2 &= \text{Var}(\hat{f}(x_0)) + \left[ \text{Bias}(\hat{f}(x_0)) \right]^2 + \text{Var}(\epsilon)
> \end{aligned}
> $$
> - $y_0$ ist der tatsächliche Wert
> - $\hat{f}(x_0)$ ist der vorhergesagte Wert
> - $\text{Var}(\hat{f}(x_0))$ ist die Varianz der Modellvorhersage
> - $\text{Bias}(\hat{f}(x_0))$ ist der Bias der Modellvorhersage
> - $\text{Var}(\epsilon)$ ist die Varianz des irreduziblen Fehlers


Was ist der Bayes Classifier
?
> [!Bayes-Klassifikator]
>
> Der Bayes-Klassifikator im maschinellen Lernen nutzt die bedingte Wahrscheinlichkeit, um die Wahrscheinlichkeit eines bestimmten Klassenergebnisses $Y = j$ gegeben die Beobachtung $X = x_0$ zu bestimmen. Diese Methode basiert auf dem Bayes-Theorem und ist besonders nützlich bei der Klassifizierung und Entscheidungsfindung.
>
> $$
> \Pr(Y = j \mid X = x_0)
> $$
> - $Y$ ist die Zielvariable oder Klasse
> - $j$ ist ein spezifischer Wert oder eine Klasse, die $Y$ annehmen kann
> - $X$ ist die Merkmalsvariable
> - $x_0$ ist ein spezifischer Wert oder Beobachtung, die $X$ annimmt


KNN
?
> [!k-Nearest Neighbors (k-NN) Klassifikator]
>
> Der k-Nearest Neighbors (k-NN) Klassifikator ist eine einfache, nicht-parametrische Methode, die verwendet wird, um die Wahrscheinlichkeit zu berechnen, dass ein Punkt $x_0$ zu einer Klasse $j$ gehört, basierend auf den Klassen der $K$ nächsten Nachbarn von $x_0$.
>
> $$
> \Pr(Y = j \mid X = x_0) = \frac{1}{K} \sum_{i \in \mathcal{N}_0} I(y_i = j)
> $$
> - $Y$ ist die Zielvariable oder Klasse
> - $j$ ist eine spezifische Klasse, die $Y$ annehmen kann
> - $X$ ist die Merkmalsvariable
> - $x_0$ ist der spezifische Wert der Merkmalsvariable
> - $K$ ist die Anzahl der nächsten Nachbarn
> - $\mathcal{N}_0$ ist die Menge der $K$ nächsten Nachbarn von $x_0$
> - $I(y_i = j)$ ist eine Indikatorfunktion, die 1 ist, wenn $y_i = j$, und 0 sonst

### Standardfehler in der linearen Regression
wie sieht der standard fehler aus in der regression?
?
> [!Standardfehler in der linearen Regression]
> 
> Die Formeln für die Standardfehler der Koeffizienten \(\beta_0\) und \(\beta_1\) in der linearen Regression lauten:
> 
> $$
> SE(\hat{\beta}_0)^2 = \sigma^2 \left[ \frac{1}{n} + \frac{\bar{x}^2}{\sum_{i=1}^{n} (x_i - \bar{x})^2} \right]
> $$
> 
> $$
> SE(\hat{\beta}_1)^2 = \frac{\sigma^2}{\sum_{i=1}^{n} (x_i - \bar{x})^2}
> $$
> 
> - \(\sigma^2\): Varianz der Fehlerterme
> - \(n\): Anzahl der Beobachtungen
> - \(\bar{x}\): Mittelwert der Prädiktorwerte
> - \(x_i\): Einzelne Prädiktorwerte
> 
> **Annahmen:**
> - Unabhängige Stichproben
> - Normalverteilung der Fehler
> - Konstante Varianz der Fehler (Homoskedastizität)


Was ist das RSS
?
> [!Residual Sum of Squares (RSS)]
>
> Die Residual Sum of Squares (RSS) ist eine Metrik, die verwendet wird, um die Abweichung der vorhergesagten Werte von den tatsächlichen Werten in einem linearen Regressionsmodell zu messen. Sie summiert die quadrierten Residuen, die die Differenzen zwischen den beobachteten und den vorhergesagten Werten darstellen.
>
> $$
> \text{RSS} = e_1^2 + e_2^2 + \cdots + e_n^2
> $$
> oder äquivalent
> $$
> \text{RSS} = (y_1 - \hat{\beta}_0 - \hat{\beta}_1 x_1)^2 + (y_2 - \hat{\beta}_0 - \hat{\beta}_1 x_2)^2 + \cdots + (y_n - \hat{\beta}_0 - \hat{\beta}_1 x_n)^2
> $$
> - $\hat{y}_i = \hat{\beta}_0 + \hat{\beta}_1 x_i$ ist die Vorhersage für $Y$ basierend auf dem $i$-ten Wert von $X$
> - $e_i = y_i - \hat{y}_i$ ist das $i$-te Residuum
> - $\text{RSS}$ ist die Residual Sum of Squares
> - $y_i$ ist der beobachtete Wert
> - $\hat{\beta}_0$ ist der geschätzte Achsenabschnitt
> - $\hat{\beta}_1$ ist der geschätzte Koeffizient für $X$
> - $x_i$ ist der $i$-te Wert von $X$


Warum quadratische Fehler Therme bei der Linearen Regression
?
> [!Lineare Regression]
>
> Die lineare Regression ist ein statistisches Verfahren, das verwendet wird, um die Beziehung zwischen einer abhängigen Variablen $Y$ und einer oder mehreren unabhängigen Variablen $X$ zu modellieren. Die grundlegenden Annahmen und Modelle der linearen Regression sind wie folgt:
>
> $$
> Y = \beta_0 + \beta_1 X + \epsilon
> $$
> - $Y$ ist die abhängige Variable
> - $\beta_0$ ist der Achsenabschnitt (Intercept) des Modells
> - $\beta_1$ ist der Koeffizient für die unabhängige Variable $X$
> - $X$ ist die unabhängige Variable
> - $\epsilon$ ist der Fehlerterm, der die Residuen darstellt
>
> Die Fehlerterme $\epsilon$ werden als normalverteilt angenommen:
>
> $$
> \epsilon \sim \mathcal{N}(0, \sigma^2)
> $$
> - $\epsilon \sim \mathcal{N}(0, \sigma^2)$ bedeutet, dass die Fehler normalverteilt sind mit einem Mittelwert von 0 und einer Varianz von $\sigma^2$
>
> Die Residuen $e_i$ werden als die Differenz zwischen den beobachteten Werten $y_i$ und den vorhergesagten Werten $\hat{y}_i$ berechnet:
>
> $$
> e_i = y_i - \hat{y}_i \approx \epsilon_i \sim \mathcal{N}(0, \sigma^2)
> $$
> - $e_i$ ist das Residuum für die $i$-te Beobachtung
> - $y_i$ ist der beobachtete Wert für die $i$-te Beobachtung
> - $\hat{y}_i$ ist der vorhergesagte Wert für die $i$-te Beobachtung


Welche Annahmen macht die Lineare Regression
?
> [!Annahmen der linearen Regression]
>
> Die lineare Regression basiert auf mehreren grundlegenden Annahmen, die sicherstellen, dass die Schätzungen der Regressionskoeffizienten unverzerrt und effizient sind, und dass die Inferenzstatistik gültig ist.
>
> 1. **Linearität**:
>    - Die Beziehung zwischen der unabhängigen Variable \(X\) und der abhängigen Variable \(Y\) ist linear. Das bedeutet, dass \(Y\) als eine lineare Funktion von \(X\) beschrieben werden kann.
>    $$
>    Y = \beta_0 + \beta_1 X + \epsilon
>    $$
>
> 2. **Unabhängigkeit der Fehler**:
>    - Die Fehlerterme \(\epsilon\) sind voneinander unabhängig. Das bedeutet, dass der Fehlerterm einer Beobachtung keine Informationen über den Fehlerterm einer anderen Beobachtung liefert.
>
> 3. **Homoskedastizität**:
>    - Die Varianz der Fehlerterme \(\epsilon\) ist konstant über alle Werte von \(X\). Das bedeutet, dass die Streuung der Fehler über den Bereich der unabhängigen Variablen gleich bleibt.
>
> 4. **Normalverteilung der Fehler**:
>    - Die Fehlerterme \(\epsilon\) sind normalverteilt mit einem Mittelwert von 0 und einer Varianz von \(\sigma^2\).
>    $$
>    \epsilon \sim \mathcal{N}(0, \sigma^2)
>    $$
>
> 5. **Keine perfekte Multikollinearität (für multiple lineare Regression)**:
>    - Keine der unabhängigen Variablen ist eine perfekte lineare Funktion einer anderen. Dies stellt sicher, dass die Koeffizienten der Regression eindeutig bestimmt werden können.
>
> 6. **Exogenität**:
>    - Die unabhängigen Variablen sind nicht korreliert mit den Fehlertermen. Das bedeutet, dass die erklärenden Variablen nicht systematisch mit den Störgrößen zusammenhängen.



Was ist die Maximum Likelihood Schaetzung bei der Linearen Regression? (Herleitung Least Squares)
?
> [!Maximum-Likelihood-Schätzung (MLE) Herleitung Least Squares]
>
> Die Maximum-Likelihood-Schätzung (MLE) ist eine Methode zur Schätzung der Parameter eines statistischen Modells. In der linearen Regression wird MLE verwendet, um die Koeffizienten zu finden, die die Wahrscheinlichkeit der beobachteten Daten maximieren.
>
> Die Wahrscheinlichkeit der Beobachtungen gegeben die Parameter $\beta_0$ und $\beta_1$ wird wie folgt ausgedrückt:
>
> $$
> P(\vec{Y} \mid \vec{X}, \beta_0, \beta_1) = \prod_{i=1}^n \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(y_i - (\beta_0 + \beta_1 x_i))^2}{2\sigma^2}}
> $$
>
> Dies kann vereinfacht werden zu:
>
> $$
> P(\vec{Y} \mid \vec{X}, \beta_0, \beta_1) = \left(\frac{1}{\sqrt{2\pi\sigma^2}}\right)^n e^{-\sum_{i=1}^n \frac{(y_i - (\beta_0 + \beta_1 x_i))^2}{2\sigma^2}}
> $$
>
> Um die MLE zu berechnen, maximieren wir das Log-Likelihood:
>
> $$
> \log P(\vec{Y} \mid \vec{X}, \beta_0, \beta_1) = \log \left(\frac{1}{\sqrt{2\pi\sigma^2}}\right)^n - \sum_{i=1}^n \frac{(y_i - (\beta_0 + \beta_1 x_i))^2}{2\sigma^2}
> $$
>
> Da der erste Term eine Konstante ist, können wir ihn ignorieren:
>
> $$
> \hat{\beta}_0, \hat{\beta}_1 = \arg \min_{\beta_0, \beta_1} \sum_{i=1}^n (y_i - (\beta_0 + \beta_1 x_i))^2
> $$
>
> - $Y$ ist die abhängige Variable
> - $X$ ist die unabhängige Variable
> - $\beta_0$ ist der Achsenabschnitt (Intercept) des Modells
> - $\beta_1$ ist der Koeffizient für die unabhängige Variable $X$
> - $y_i$ ist der beobachtete Wert für die $i$-te Beobachtung
> - $\hat{y}_i$ ist der vorhergesagte Wert für die $i$-te Beobachtung
> - $\epsilon$ ist der Fehlerterm, der die Residuen darstellt
> - $\sigma^2$ ist die Varianz des Fehlerterms


Warum funktioniert die Herleitung der Least Squares?
?
Weil man die Normalverteilung annimmt und somit die Maximum Likelihood wie bereits daargelegt. Die Logitische Regression laesst sich auch einfach als Maximum likelihood Problem formulieren und loesen.


### Standard Error of the Coefficient Estimates
Wie wird das Konfidenzintervall aufgestellt?
?
> [!Standardfehler und Konfidenzintervalle]
> 
> **Standardfehler der Koeffizientenschätzungen:**
> Der Standardfehler gibt an, wie die Schätzung bei wiederholter Stichprobenziehung variiert.
> $$
> SE(\hat{\beta}_1)^2 = \frac{\sigma^2}{\sum_{i=1}^{n} (x_i - \bar{x})^2}
> $$
> $$
> SE(\hat{\beta}_0)^2 = \sigma^2 \left[ \frac{1}{n} + \frac{\bar{x}^2}{\sum_{i=1}^{n} (x_i - \bar{x})^2} \right]
> $$
> wobei $\sigma^2 = \text{Var}(\epsilon)$ ist.
> 
> **Konfidenzintervalle:**
> Ein 95%-Konfidenzintervall für $\hat{\beta}_1$ lautet:
> $$
> \left[ \hat{\beta}_1 - 2 \cdot SE(\hat{\beta}_1), \hat{\beta}_1 + 2 \cdot SE(\hat{\beta}_1) \right]
> $$
> Dieses Intervall enthält den wahren Wert von $\beta_1$ mit einer Wahrscheinlichkeit von 95% unter wiederholter Stichprobenziehung.
> 
> - $\sigma^2$: Varianz der Fehlerterme
> - $n$: Anzahl der Beobachtungen
> - $\bar{x}$: Mittelwert der Prädiktorwerte
> - $x_i$: Einzelne Prädiktorwerte
> - $SE$: Standardfehler
> - $\beta_0$: Interzept des Modells
> - $\beta_1$: Koeffizient für den Prädiktor


Hypothesen Tests in Linearer Regression
?
> [!Hypothesentests in der linearen Regression]
>
> In der linearen Regression wird häufig ein Hypothesentest verwendet, um zu überprüfen, ob eine Beziehung zwischen der unabhängigen Variable $X$ und der abhängigen Variable $Y$ besteht.
>
> Die Nullhypothese ($H_0$) und die Alternativhypothese ($H_a$) lauten wie folgt:
>
> $$
> H_0: \text{Es besteht keine Beziehung zwischen } X \text{ und } Y
> $$
>
> versus die Alternativhypothese
>
> $$
> H_a: \text{Es besteht eine Beziehung zwischen } X \text{ und } Y
> $$
>
> Mathematisch entspricht dies dem Testen der folgenden Hypothesen:
>
> $$
> H_0: \beta_1 = 0
> $$
>
> versus
>
> $$
> H_a: \beta_1 \neq 0
> $$
>
> - $H_0$ ist die Nullhypothese, die besagt, dass der Koeffizient $\beta_1$ gleich null ist, was bedeutet, dass keine lineare Beziehung zwischen $X$ und $Y$ besteht.
> - $H_a$ ist die Alternativhypothese, die besagt, dass der Koeffizient $\beta_1$ ungleich null ist, was bedeutet, dass eine lineare Beziehung zwischen $X$ und $Y$ besteht.
>
> Wenn $\beta_1 = 0$, dann reduziert sich das Modell auf:
>
> $$
> Y = \beta_0 + \epsilon
> $$
>
> Dies würde bedeuten, dass $X$ keinen Einfluss auf $Y$ hat und $Y$ nur durch den Mittelwert ($\beta_0$) und den Fehlerterm ($\epsilon$) bestimmt wird.
>
> Um die Hypothese zu testen, verwenden wir den t-Test, der wie folgt definiert ist:
>
> $$
> t = \frac{\hat{\beta}_1 - 0}{SE(\hat{\beta}_1)}
> $$
>
> Hierbei ist:
>
> - $\hat{\beta}_1$ der geschätzte Koeffizient für die unabhängige Variable $X$
> - $SE(\hat{\beta}_1)$ der Standardfehler von $\hat{\beta}_1$
>
> Der t-Wert gibt an, wie viele Standardabweichungen der geschätzte Koeffizient von der Nullhypothese abweicht. Ein großer absoluter Wert von $t$ deutet darauf hin, dass $\hat{\beta}_1$ signifikant von null verschieden ist, was die Nullhypothese widerlegt.
>
> **Z-Score im Vergleich zum t-Score:**
>
> - Der t-Score wird verwendet, wenn die Stichprobengröße klein ist (normalerweise $n < 30$) und/oder die Populationsvarianz unbekannt ist. Er folgt der t-Verteilung.
> - Der Z-Score wird verwendet, wenn die Stichprobengröße groß ist (normalerweise $n \geq 30$) und die Populationsvarianz bekannt ist. Er folgt der Standardnormalverteilung (Normalverteilung mit Mittelwert 0 und Varianz 1).


Wie ist der RSE?
?
> [!Residual Standard Error (RSE)]
> 
> Der Residual Standard Error (RSE) ist ein Schätzwert für die Standardabweichung des Fehlerterms $\epsilon$ im linearen Regressionsmodell. Er gibt grob gesagt an, um wie viel die Antwortvariable im Durchschnitt von der wahren Regressionslinie abweicht.
> 
> Der RSE wird mit der folgenden Formel berechnet:
> 
> $$
> \text{RSE} = \sqrt{\frac{1}{n-2} \text{RSS}} = \sqrt{\frac{1}{n-2} \sum_{i=1}^n (y_i - \hat{y}_i)^2}
> $$
> 
> wobei:
> 
> - $n$ die Anzahl der Beobachtungen ist
> - $\text{RSS}$ die Residual Sum of Squares ist
> - $y_i$ der beobachtete Wert der $i$-ten Beobachtung ist
> - $\hat{y}_i$ der vorhergesagte Wert der $i$-ten Beobachtung ist
> 
> Die RSS (Residual Sum of Squares) ist definiert als:
> 
> $$
> \text{RSS} = \sum_{i=1}^n (y_i - \hat{y}_i)^2
> $$
> 
> Der RSE schätzt die durchschnittliche Abweichung der beobachteten Werte von den vorhergesagten Werten, wenn das Modell die wahre Beziehung zwischen den Variablen perfekt beschreiben würde.
>- $n$ ist die Anzahl der Beobachtungen
>- $\text{RSS}$ ist die Residual Sum of Squares
>- $y_i$ ist der beobachtete Wert der $i$-ten Beobachtung
>- $\hat{y}_i$ ist der vorhergesagte Wert der $i$-ten Beobachtung

### Hypothesentest in der linearen Regression
Wie sieht der t test aus?
?
> [!Hypothesentest in der linearen Regression]
> 
> Um die Nullhypothese zu testen, berechnen wir die t-Statistik:
> $$
> t = \frac{\hat{\beta}_1 - 0}{SE(\hat{\beta}_1)}
> $$
> Diese folgt einer t-Verteilung mit \( n - 2 \) Freiheitsgraden, unter der Annahme, dass \( \beta_1 = 0 \) ist.
> 
> Mit statistischer Software lässt sich die Wahrscheinlichkeit berechnen, einen Wert gleich oder größer als \(|t|\) zu beobachten. Diese Wahrscheinlichkeit nennt man den p-Wert.
> 
> - $\hat{\beta}_1$: Geschätzter Koeffizient
> - $SE(\hat{\beta}_1)$: Standardfehler des geschätzten Koeffizienten
> - $n$: Anzahl der Beobachtungen
> - $t$: t-Statistik


Welche Verteilung braucht welches Modell der Regression?
?
GLM
![Pasted image 20240707173420.png](/img/user/Files/Pasted%20image%2020240707173420.png)

Warum ist der $R^{2}$ kein guter Wert für die Güte eines Modelles?
?
Weil mit mehr Variblen, Parameter desto besser wird der $R^{2}$



Was ist die F-Statistic?
?
> [!F-Statistik in der multiplen linearen Regression]
>
> In der multiplen linearen Regression wird die F-Statistik verwendet, um zu überprüfen, ob alle Regressionskoeffizienten gleich null sind, also ob das Modell signifikant zur Erklärung der Varianz der abhängigen Variablen beiträgt.
>
> Die Nullhypothese ($H_0$) und die Alternativhypothese ($H_a$) lauten wie folgt:
>
> $$
> H_0: \beta_1 = \beta_2 = \cdots = \beta_p = 0
> $$
>
> versus
>
> $$
> H_a: \text{Mindestens ein } \beta_j \text{ ist ungleich null}
> $$
>
> - $H_0$ ist die Nullhypothese, die besagt, dass alle Regressionskoeffizienten gleich null sind, was bedeutet, dass die unabhängigen Variablen keinen Einfluss auf die abhängige Variable haben.
> - $H_a$ ist die Alternativhypothese, die besagt, dass mindestens ein Regressionskoeffizient ungleich null ist, was bedeutet, dass mindestens eine unabhängige Variable einen Einfluss auf die abhängige Variable hat.
>
> Dieser Hypothesentest wird durch Berechnung der F-Statistik durchgeführt:
>
> $$
> F = \frac{(\text{TSS} - \text{RSS})/p}{\text{RSS}/(n - p - 1)}
> $$
>
> wobei:
>
> - $\text{TSS}$ (Total Sum of Squares) die totale Quadratsumme ist und berechnet wird als:
>
> $$
> \text{TSS} = \sum (y_i - \bar{y})^2
> $$
>
> - $\text{RSS}$ (Residual Sum of Squares) die Residualquadratsumme ist und berechnet wird als:
>
> $$
> \text{RSS} = \sum (y_i - \hat{y}_i)^2
> $$
>
> - $p$ die Anzahl der Prädiktoren ist
> - $n$ die Anzahl der Beobachtungen ist
>
> Die F-Statistik vergleicht das Modell mit allen Prädiktoren gegen ein Modell ohne Prädiktoren. Ein hoher F-Wert deutet darauf hin, dass das Modell einen signifikanten Teil der Varianz der abhängigen Variablen erklärt.


Wie werden Categoriale Variablen umcodiert?
?
> [!Interpretation eines linearen Regressionsmodells mit einem binären Prädiktor]
>
> In diesem Beispiel verwenden wir eine binäre Variable als Prädiktor in der Regressionsgleichung. Das resultierende Modell ist:
>
> $$
> y_i = \beta_0 + \beta_1 x_i + \epsilon_i =
> \begin{cases}
> \beta_0 + \beta_1 + \epsilon_i & \text{wenn } x_i = 1 \\
> \beta_0 + \epsilon_i & \text{wenn } x_i = 0
> \end{cases}
> $$
>
> - $\beta_0$ kann als der durchschnittliche Wert von $y$ interpretiert werden, wenn $x_i = 0$.
> - $\beta_0 + \beta_1$ kann als der durchschnittliche Wert von $y$ interpretiert werden, wenn $x_i = 1$.
> - $\beta_1$ ist der durchschnittliche Unterschied im Wert von $y$ zwischen den Gruppen $x_i = 1$ und $x_i = 0$.
>
> Die Schätzungen der Koeffizienten und andere Informationen, die mit dem Modell verbunden sind, liefern wichtige Einblicke in die Beziehung zwischen der binären Prädiktorvariablen und der Zielvariablen $y$.
>
> Beispielhafte Interpretationen könnten sein:
>
> - Der durchschnittliche Wert von $y$ für die Gruppe mit $x_i = 0$.
> - Der durchschnittliche Wert von $y$ für die Gruppe mit $x_i = 1$.
> - Der Unterschied im durchschnittlichen Wert von $y$ zwischen den beiden Gruppen.



Was stellt eine Interaktion dar in der Regression zwischen Dummy Variablen?
?
> [!Interaktion von Dummy-Variablen in der linearen Regression]
>
> In der linearen Regression können Dummy-Variablen verwendet werden, um kategoriale Prädiktoren darzustellen. Wenn Interaktionen zwischen Dummy-Variablen einbezogen werden, ermöglicht dies die Untersuchung der kombinierten Effekte dieser Variablen auf die Zielvariable $Y$.
>
> Betrachten wir folgendes Modell:
>
> $$
> Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \beta_3 X_1 X_2 + \epsilon
> $$
>
> Hierbei sind $X_1$ und $X_2$ Dummy-Variablen. Die Terme in diesem Modell bedeuten:
>
> - $\beta_0$: Der durchschnittliche Wert von $Y$, wenn $X_1 = 0$ und $X_2 = 0$.
> - $\beta_1$: Die Veränderung des durchschnittlichen Werts von $Y$, wenn $X_1$ von 0 auf 1 wechselt, während $X_2$ konstant bleibt.
> - $\beta_2$: Die Veränderung des durchschnittlichen Werts von $Y$, wenn $X_2$ von 0 auf 1 wechselt, während $X_1$ konstant bleibt.
> - $\beta_3$: Der Interaktionseffekt zwischen $X_1$ und $X_2$. Dies ist die zusätzliche Veränderung im durchschnittlichen Wert von $Y$, wenn sowohl $X_1$ als auch $X_2$ von 0 auf 1 wechseln, im Vergleich zur Summe der einzelnen Effekte von $X_1$ und $X_2$.
>
> Das Modell kann die folgenden Szenarien erklären:
>
> 1. **Beide Dummy-Variablen sind 0 ($X_1 = 0$, $X_2 = 0$)**:
>    $$
>    Y = \beta_0 + \epsilon
>    $$
>    Dies ist der Grundwert (Referenzkategorie).
>
> 2. **Nur $X_1$ ist 1 ($X_1 = 1$, $X_2 = 0$)**:
>    $$
>    Y = \beta_0 + \beta_1 + \epsilon
>    $$
>    Der Effekt von $X_1$ alleine.
>
> 3. **Nur $X_2$ ist 1 ($X_1 = 0$, $X_2 = 1$)**:
>    $$
>    Y = \beta_0 + \beta_2 + \epsilon
>    $$
>    Der Effekt von $X_2$ alleine.
>
> 4. **Beide Dummy-Variablen sind 1 ($X_1 = 1$, $X_2 = 1$)**:
>    $$
>    Y = \beta_0 + \beta_1 + \beta_2 + \beta_3 + \epsilon
>    $$
>    Der kombinierte Effekt von $X_1$ und $X_2$ sowie deren Interaktion.
>
> Die Interaktionsterm $\beta_3$ zeigt, ob der Effekt der gleichzeitigen Anwesenheit von $X_1$ und $X_2$ größer (oder kleiner) ist als die Summe ihrer individuellen Effekte.
>
> ![Pasted image 20240624200406.png](/img/user/Files/Pasted%20image%2020240624200406.png)

Wie veraendert sich der Plot mit Interaction in der Regression?
?
![Pasted image 20240708225828.png](/img/user/Files/Pasted%20image%2020240708225828.png)

Was kann passieren wenn man nun zuviele Dummy Variablen hat?
?
> [!Interaktion von Dummy-Variablen und lineare Abhängigkeit]
>
> Betrachten wir das folgende lineare Regressionsmodell mit Dummy-Variablen:
>
> $$
> y_i = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \epsilon_i =
> \begin{cases}
> \beta_0 + \beta_1 + \epsilon_i & \text{wenn die } i\text{-te Person aus dem Süden kommt} \\
> \beta_0 + \beta_2 + \epsilon_i & \text{wenn die } i\text{-te Person aus dem Westen kommt} \\
> \beta_0 + \epsilon_i & \text{wenn die } i\text{-te Person aus dem Osten kommt}
> \end{cases}
> $$
>
> In diesem Modell:
> - $x_1 = 1$, wenn die Person aus dem Süden kommt, und $0$ sonst.
> - $x_2 = 1$, wenn die Person aus dem Westen kommt, und $0$ sonst.
> - Die Referenzkategorie (Osten) ist durch das Fehlen beider Dummy-Variablen ($x_1 = 0$ und $x_2 = 0$) dargestellt.
>
> **Problem der linearen Abhängigkeit:**
>
> Wenn wir eine weitere Dummy-Variable $\beta_3 x_3$ hinzufügen würden, um Personen aus dem Norden zu repräsentieren, würde dies zu einer linearen Abhängigkeit in der Design-Matrix führen. Die Dummy-Variable $x_3$ wäre definiert als:
> - $x_3 = 1$, wenn die Person aus dem Norden kommt, und $0$ sonst.
>
> Dies würde das Modell folgendermaßen ändern:
>
> $$
> y_i = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \beta_3 x_3 + \epsilon_i
> $$
>
> Da jede Person aus dem Süden, Westen, Osten oder Norden kommen muss, würden die Dummy-Variablen $x_1$, $x_2$, und $x_3$ eine lineare Kombination ergeben, die die Konstante $1$ ergibt:
>
> $$
> x_0 + x_1 + x_2 + x_3 = 1
> $$
>
> Hierbei ist $x_0 = 1$ für alle Beobachtungen, um die Interzept-Variable darzustellen.
>
> Diese lineare Abhängigkeit führt zu Multikollinearität, was bedeutet, dass die Design-Matrix nicht mehr invertierbar ist und die Regressionskoeffizienten $\beta_0, \beta_1, \beta_2, \beta_3$ nicht eindeutig geschätzt werden können. Dies wird als das Dummy-Variablen-Falle bezeichnet.
>
> Um dieses Problem zu vermeiden, sollte man nur $k-1$ Dummy-Variablen für $k$ Kategorien verwenden. In diesem Fall sind $x_1$ und $x_2$ ausreichend, um die drei Kategorien (Süden, Westen, Osten) darzustellen, wobei die vierte Kategorie (Norden) die Referenzkategorie ist.


Sprich was muss man bei Dummy Variablen machen, um Multikolineraitaet zu vermeiden?
?
Ein $B_{i}$ weniger als es Auspraegungen gibt, also eine Dummy Variable weniger wie Auspraegungen
 

Was nennt man eine Interaction?
?
Man Multipliziert die Dummies gegenseitig miteinander $X_{1}$ und $X_{2}$
![Pasted image 20240624200115.png](/img/user/Files/Pasted%20image%2020240624200115.png)beispiel: The model equation would be:
$\text{Sales} = 6.7502 + 0.0191 \cdot \text{TV} + 0.0289 \cdot \text{radio} + 0.0011 \cdot (\text{TV} \times \text{radio})$



Welche Probleme gibt es bei der Regression?
?
![Pasted image 20240624201453.png](/img/user/Files/Pasted%20image%2020240624201453.png)



Wie kann man nicht linearitaet mit einem Linearen Model modelieren?
?
> [!Nichtlineare Modellierung mit quadratischen Merkmalen]
>
> Nichtlineare Beziehungen zwischen Variablen können in einem linearen Regressionsmodell dargestellt werden, indem nichtlineare Terme der unabhängigen Variablen hinzugefügt werden. Ein Beispiel ist die Hinzufügung eines quadratischen Terms:
>
> Betrachten wir das folgende Modell:
>
> $$
> \text{mpg} = \beta_0 + \beta_1 \times \text{horsepower} + \beta_2 \times \text{horsepower}^2 + \epsilon
> $$
>
> Hierbei:
> - $\beta_0$ ist der Achsenabschnitt (Intercept) des Modells.
> - $\beta_1$ ist der Koeffizient für den linearen Term der unabhängigen Variable "horsepower".
> - $\beta_2$ ist der Koeffizient für den quadratischen Term der unabhängigen Variable "horsepower".
> - $\epsilon$ ist der Fehlerterm.
>
> Obwohl das Modell einen quadratischen Term enthält, bleibt es ein lineares Modell, weil die Koeffizienten ($\beta_0$, $\beta_1$, $\beta_2$) linear in der Gleichung auftreten. Die Lineareität bezieht sich auf die Parameter des Modells, nicht auf die Variablen selbst.
>
> **Vorteile der Hinzufügung quadratischer Merkmale:**
>
> - **Erfassen von Nichtlinearitäten:** Das Modell kann die nichtlineare Beziehung zwischen "horsepower" und "mpg" besser erfassen, da es den Effekt von "horsepower" sowohl linear als auch quadratisch berücksichtigt.
>
> - **Flexibilität:** Durch das Hinzufügen von Polynomtermen (z.B. quadratische, kubische) kann das Modell flexibler gestaltet werden, um komplexere Beziehungen zu modellieren.
>
> **Beispielhafte Interpretation:**
>
> - Der Koeffizient $\beta_1$ beschreibt die Änderung in "mpg" für eine Einheit Änderung in "horsepower", wenn alle anderen Terme konstant gehalten werden.
> - Der Koeffizient $\beta_2$ beschreibt den zusätzlichen Effekt, der auftritt, wenn "horsepower" quadratisch zunimmt.
>
> **Zusammengefasst:** Durch das Hinzufügen von nichtlinearen Termen wie $\text{horsepower}^2$ bleibt das Modell linear in Bezug auf die Koeffizienten, während es in der Lage ist, nichtlineare Beziehungen zwischen den Variablen zu modellieren. Dies ermöglicht es, die Komplexität der Daten besser zu erfassen, ohne die grundlegende Struktur und die Interpretierbarkeit eines linearen Modells zu verlieren.
> 
> Lineares Modell:
> ![Pasted image 20240707015419.png](/img/user/Files/Pasted%20image%2020240707015419.png)
> 
> Quadratisches Modell mit quadratischem Term:
> ![Pasted image 20240707015504.png](/img/user/Files/Pasted%20image%2020240707015504.png)







Was ist nicht linearität
?
![Pasted image 20240624201543.png](/img/user/Files/Pasted%20image%2020240624201543.png)
Hier sieht man, dass der erste Plot einen Trendaufweist, dies sollte nicht sein, eventuell transformieren mit wurzel quadrat oder log. Dies sieht man am besten mit Residuen Plots.



Was ist das Problem mit der Korrelation der Fehler Thermen
?
todo




Was ist heterogestatisch?
?
Der Begriff "heteroskedastisch" bezieht sich auf eine Situation in der Regressionsanalyse, bei der die Varianz der Fehlerterme (\(\epsilon\)) nicht konstant ist über die Beobachtungen hinweg. Dies steht im Gegensatz zur Annahme der Homoskedastizität, bei der die Varianz der Fehler konstant bleibt.

### Heteroskedastizität
> [!Heteroskedastizität]
> 
> **Definition:** Heteroskedastizität liegt vor, wenn die Varianz der Störgrößen (\(\epsilon\)) in einem Regressionsmodell nicht konstant ist, sondern von den Werten der unabhängigen Variablen abhängt.
> 
> **Formel:** Es gibt keine spezifische Formel für Heteroskedastizität, aber es betrifft die Varianz der Fehlerterme:
> $$
> \text{Var}(\epsilon_i) = \sigma_i^2
> $$
> - \(\epsilon_i\): Fehlerterm für die \(i\)-te Beobachtung
> - \(\sigma_i^2\): Varianz des Fehlerterms, die von \(i\) abhängt
**Konsequenzen:** Heteroskedastizität kann zu ineffizienten und verzerrten Schätzungen der Regressionskoeffizienten führen, da die Annahme der konstanten Varianz verletzt wird.
**Erkennung:** Heteroskedastizität kann durch visuelle Inspektion von Residuenplots oder statistische Tests wie den Breusch-Pagan-Test oder den White-Test identifiziert werden.
**Behandlung:** Es gibt mehrere Methoden, um Heteroskedastizität zu behandeln, einschließlich der Verwendung von robusten Standardfehlern, Transformation der Daten (z.B. Log-Transformation), oder gewichtete kleinste Quadrate (WLS).


Was ist Homoskedastizität ::


Was machst du hier: ![Pasted image 20240624202629.png](/img/user/Files/Pasted%20image%2020240624202629.png)?
Logartymus

\

Was ist ein Aussreiser
?
Art1 (Ist in der Verteilung von X drin) sprich nicht so gut aber auch nicht so schlimm --> schadet der Evaluiereung : ![Pasted image 20240624202830.png](/img/user/Files/Pasted%20image%2020240624202830.png)Art2 (high Leverage Outliers) --> Schadet dem Model und der Evaluierung: ![Pasted image 20240624203012.png](/img/user/Files/Pasted%20image%2020240624203012.png)


Wie kann man high Leverage Points erkennen?
?
![Pasted image 20240624203211.png](/img/user/Files/Pasted%20image%2020240624203211.png)


Was ist koolinerität?
?
todo


Was ist multikoolinerität
?
todo


Wie bemerkt man multikolinerität?
?
![Pasted image 20240624203725.png](/img/user/Files/Pasted%20image%2020240624203725.png) je grösser der VIF desto eher hat man eine Kolinerität.


### Maßnahmen bei Multikollinearität
Massnahmen bei Multikolinerität
?
> [!Maßnahmen bei Multikollinearität]
> 
> Multikollinearität tritt auf, wenn zwei oder mehr Prädiktoren in einem Regressionsmodell stark korreliert sind, was zu instabilen Schätzungen der Regressionskoeffizienten führt. Hier sind einige Maßnahmen, um Multikollinearität zu adressieren:
> 
> **1. Prädiktoren entfernen:**
> - Entfernen hoch korrelierter Prädiktoren, um die Modellstabilität zu verbessern.
> 
> **2. Hauptkomponentenanalyse (PCA):**
> - Reduziert die Dimensionen der Daten, indem sie die Daten auf unkorrelierte Hauptkomponenten projiziert.
> 
> **3. Regularisierungsmethoden:**
> - Ridge Regression und Lasso Regression können verwendet werden, um die Auswirkungen von Multikollinearität zu verringern.
> 
> **4. Datenzentrierung und -skalierung:**
> - Zentrieren und skalieren der Prädiktoren, um die Multikollinearität zu reduzieren.

### \(R^2\) und Restquadratsumme
wie berechnet man r2? 
?
> [! \(R^2\) und Restquadratsumme]
> 
> **Restquadratsumme (RSS):**
> $$
> \text{RSS} = \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
> $$
> 
> **Totalquadratsumme (TSS):**
> $$
> \text{TSS} = \sum_{i=1}^{n} (y_i - \bar{y})^2
> $$
> 
> **Bestimmtheitsmaß (\(R^2\)):**
> $$
> R^2 = 1 - \frac{\text{RSS}}{\text{TSS}}
> $$
> \(R^2\) misst den Anteil der Gesamtvarianz, der durch das Modell erklärt wird.
> 
> - \(\text{RSS}\): Restquadratsumme
> - \(\text{TSS}\): Totalquadratsumme
> - \(y_i\): Beobachteter Wert
> - \(\hat{y}_i\): Vorhergesagter Wert
> - \(\bar{y}\): Mittelwert der beobachteten Werte
> - \(n\): Anzahl der Beobachtungen

## Classification

Warum benutzt man Logistic Regression und nicht Linreg?
?
- weil negative values
- und nicht zwischen 1 und 0

![Pasted image 20240708230931.png](/img/user/Files/Pasted%20image%2020240708230931.png)


Was ist das Discison boundrie? 
?
> [!Decision Boundary]
> 
> Eine Decision Boundary ist eine Grenze im Merkmalsraum, die verschiedene Klassen in einem Klassifikationsproblem voneinander trennt. Sie wird durch ein Klassifikationsmodell definiert und trennt Regionen, in denen verschiedene Klassen dominieren. 
> 
> - In linearen Modellen (z.B. Logistic Regression) ist die Decision Boundary eine lineare Trennlinie.
> - In nichtlinearen Modellen (z.B. Support Vector Machines mit Kerneln) kann die Decision Boundary komplexe Formen annehmen.
> 
> Eine Decision Boundary kann durch visuelle Darstellung der Klassen im Merkmalsraum veranschaulicht werden.
Was ist der Threshhold in Logistic Regression ::


Formel für die Logistische Regression
?
![Pasted image 20240704124342.png](/img/user/Files/Pasted%20image%2020240704124342.png)output: Zahl zwischen 0 und 1 muss nicht die Wahrscheinlichkeit sein.


Formel Logistische Regression Odss umstellung
?
![Pasted image 20240704124522.png](/img/user/Files/Pasted%20image%2020240704124522.png)
output: Odds

Formel Odds mit Logartymuss
?
![Pasted image 20240704124650.png](/img/user/Files/Pasted%20image%2020240704124650.png)



### Maximum Likelihood
Wie sieht die Maximum likelihood aus von der logistischen Regression? 
?
> [!Maximum Likelihood]
> 
> Maximum-Likelihood-Schätzung wird verwendet, um die Parameter zu schätzen. Die Likelihood-Funktion für die logistische Regression lautet:
> $$
> \ell(\beta_0, \beta) = \prod_{i:y_i=1} p(x_i) \prod_{i:y_i=0} (1 - p(x_i))
> $$
> Diese Likelihood gibt die Wahrscheinlichkeit der beobachteten Nullen und Einsen in den Daten an. Wir wählen $\beta_0$ und $\beta_1$ so, dass die Likelihood der beobachteten Daten maximiert wird.
> 
> - $\beta_0$: Interzept
> - $\beta_1$: Koeffizient für die Variable
> - $p(x_i)$: Wahrscheinlichkeitsvorhersage für Beobachtung \(i\)
> - $y_i$: Beobachteter Wert
> 
> In R kann das Modell mit der `glm`-Funktion angepasst werden.

Beispiel Logistische Regression?
?
![Pasted image 20240708231802.png](/img/user/Files/Pasted%20image%2020240708231802.png)
![Pasted image 20240708231955.png](/img/user/Files/Pasted%20image%2020240708231955.png)





Logistische Regression mit dummy variblen binaer
?
![Pasted image 20240708232137.png](/img/user/Files/Pasted%20image%2020240708232137.png)



### Multinominal Logistic Regression
was ist Multinominale Logistic Regression?
?
mehrere Klassen:
![Pasted image 20240708232303.png](/img/user/Files/Pasted%20image%2020240708232303.png)




Z-Statistic
?
> [!Z-Statistic]
>
> Die Z-Statistic misst, wie viele Standardabweichungen ein Datenpunkt vom Mittelwert entfernt ist. Sie wird verwendet, um Hypothesentests durchzuführen und zu bestimmen, ob ein Datenpunkt signifikant von einem erwarteten Wert abweicht.
>
> $$
> Z = \frac{X - \mu}{\sigma}
> $$
> - \( X \): Beobachteter Wert
> - \( \mu \): Erwartungswert
> - \( \sigma \): Standardabweichung
<!--SR:!2024-07-08,1,230-->


### Bernoulli-Verteilung
Wie ist die Bernoulli Verteilung?
?
> [!Bernoulli-Verteilung]
> 
> Die Bernoulli-Verteilung modelliert einen binären Ausgang (Erfolg oder Misserfolg) mit einer Wahrscheinlichkeit \( p \) für Erfolg und \( 1-p \) für Misserfolg.
> 
> **Varianz der Bernoulli-Verteilung:**
> 
> Die Varianz kann berechnet werden, da sie die Streuung der binären Ausgänge um den Mittelwert \( p \) misst:
> $$
> \text{Var}(X) = p(1-p)
> $$
> - \( p \): Wahrscheinlichkeit für Erfolg
> - \( 1-p \): Wahrscheinlichkeit für Misserfolg
> 
> Diese Berechnung ist möglich, weil die Varianz der Bernoulli-Verteilung die Wahrscheinlichkeit berücksichtigt, dass ein Ausgang von der Erwartung \( p \) abweicht.

### T-Statistic in Linearer Regression
> [!T-Statistic in Linearer Regression]
> 
> Der T-Statistic wird in der linearen Regression verwendet, um die Signifikanz eines einzelnen Regressionskoeffizienten zu testen. Da die Varianz des Fehlerterms \(\sigma^2\) unbekannt ist, muss sie aus den Daten geschätzt werden. 
> Die Formel für die T-Statistic lautet:
> $$
> t = \frac{\hat{\beta}_j}{SE(\hat{\beta}_j)}
> $$ 
> - $\hat{\beta}_j$: Geschätzter Koeffizient für den \(j\)-ten Prädiktor
> - $SE(\hat{\beta}_j)$: Standardfehler des geschätzten Koeffizienten
> - Diese Teststatistik folgt unter der Nullhypothese einer t-Verteilung mit \(n - p - 1\) Freiheitsgraden, wobei \(n\) die Anzahl der Beobachtungen und \(p\) die Anzahl der Prädiktoren ist.


Modelle können nur Korrelation erklären was jedoch nicht :: Kausalzusammenhänge --> Confounding


Was ist die Multinominale Logitische Regression :: Regression mit mehrern Klassen


Wie sieht die Formel für die Multinominale Regression aus?
?
Sprich Softmax --> Alle Summieren sich auf 1
![Pasted image 20240704130401.png](/img/user/Files/Pasted%20image%2020240704130401.png)
Formel für Odds mit mit baseline comparative
?
![Pasted image 20240704130549.png](/img/user/Files/Pasted%20image%2020240704130549.png)






Hier sind die wichtigsten Konzepte und Formeln von der angegebenen Webseite im Stil der bisherigen Erklärungen:

Wie sieht die Formel der Logistischen Regression aus
?
> [!Logistic Regression]
>
> Logistic Regression modelt die Wahrscheinlichkeit, dass die Antwortvariable \( Y \) einer bestimmten Kategorie angehört. Das Modell wird wie folgt ausgedrückt:
> $$
> Pr(Y=1|X) = \frac{e^{\beta_{0}+\beta_{1}X}}{1+e^{\beta_{0}+\beta_{1}X}}
> $$
> Dies kann in die Logit-Funktion umgeschrieben werden:
> $$
> \log \left( \frac{Pr(Y=1|X)}{1-Pr(Y=1|X)} \right) = \beta_{0} + \beta_{1}X
> $$
> - $\beta_0$: Interzept
> - $\beta_1$: Koeffizient für den Prädiktor \( X \)


Was ist die Maximum Liklihood verfahren?
?
> [!Maximum Likelihood]
>
> Die Koeffizienten werden durch das Maximum-Likelihood-Verfahren geschätzt, das versucht, $\beta_0$ und $\beta_1$ so zu finden, dass die Wahrscheinlichkeit der beobachteten Daten maximiert wird.


> [!Hypothesis Testing]
>
> Um zu überprüfen, ob ein Zusammenhang zwischen der Wahrscheinlichkeit einer Klasse und einem Prädiktor besteht, wird ein Hypothesentest durchgeführt:
> $$
> H_0: \beta_1 = 0 \\
> $$
> $$
> H_a: \beta_1 \neq 0
> $$
> - \( z \)-statistic misst die Anzahl der Standardabweichungen, die \( \beta_1 \) von 0 entfernt ist.

Wie sieht die Mulltiple Lineare Regression aus?
?
> [!Multiple Logistic Regression]
>
> Wenn mehrere Prädiktoren vorhanden sind, wird das Modell wie folgt erweitert:
> $$
> Pr(Y=1|X_1, X_2, X_3) = \frac{e^{\beta_{0}+\beta_{1}X_1+\beta_{2}X_2+\beta_{3}X_3}}{1+e^{\beta_{0}+\beta_{1}X_1+\beta_{2}X_2+\beta_{3}X_3}}
> $$
> - Die Interpretation der Koeffizienten bleibt ähnlich, wobei die Werte der anderen Prädiktoren konstant gehalten werden.

> [!Linear Discriminant Analysis (LDA)]
>
> LDA modelliert die Verteilungen der Prädiktoren in jeder Antwortklasse und verwendet den Satz von Bayes, um diese in Schätzungen zu überführen:
> $$
> Pr(Y=k|X=x) = \frac{\pi_k f_k(x)}{\sum_{l=1}^K \pi_l f_l(x)}
> $$
> - \( $\pi_k$ \): A-priori-Wahrscheinlichkeit für Klasse \( k \)
> - \( $f_k(x)$ \): Dichtefunktion der Prädiktoren für Klasse \( k \)

### Logistic Regression vs. LDA
wann lda wann logistische regression?
> [!Logistic Regression vs. LDA]
> 
> Für ein Zwei-Klassen-Problem kann gezeigt werden, dass für LDA:
> $$
> \log \left( \frac{p_1(x)}{1 - p_1(x)} \right) = \log \left( \frac{p_1(x)}{p_2(x)} \right) = c_0 + c_1 x_1 + \cdots + c_p x_p
> $$
> Dies hat die gleiche Form wie die logistische Regression. Der Unterschied liegt in der Schätzung der Parameter.
> 
> **Logistische Regression:**
> - Nutzt die bedingte Likelihood basierend auf $\text{Pr}(Y|X)$ (bekannt als diskriminatives Lernen).
> 
> **LDA:**
> - Nutzt die vollständige Likelihood basierend auf $text{Pr}(X,Y)$ (bekannt als generatives Lernen).
> 
> Trotz dieser Unterschiede sind die Ergebnisse in der Praxis oft sehr ähnlich.
> 
> - $p_1(x)$: Wahrscheinlichkeit, dass die Beobachtung \(x\) zu Klasse 1 gehört
> - $p_2(x)$: Wahrscheinlichkeit, dass die Beobachtung \(x\) zu Klasse 2 gehört
> - $c_0, c_1, \ldots, c_p$: Koeffizienten der linearen Kombination der Prädiktoren
> - $x_1, \ldots, x_p$: Prädiktoren
### Bayes-Theorem für Klassifikation
Was ist die LDA Linear Discriminant analysis?
?
> [!Bayes-Theorem für Klassifikation]
> 
> Thomas Bayes war ein Mathematiker, dessen Theorem ein bedeutender Teilbereich der Statistik und probabilistischen Modellierung ist. Das Bayes-Theorem wird für die Klassifikation wie folgt verwendet:
> $$
> \text{Pr}(Y = k|X = x) = \frac{\text{Pr}(X = x|Y = k) \cdot \text{Pr}(Y = k)}{\text{Pr}(X = x)}
> $$
> Für die Diskriminanzanalyse wird es leicht abgewandelt:
> $$
> \text{Pr}(Y = k|X = x) = \frac{\pi_k f_k(x)}{\sum_{l=1}^{K} \pi_l f_l(x)}
> $$
> 
> - $Y$: Zufallsvariable der Klasse
> - $k$: Spezifische Klasse
> - $X$: Eingabevektor
> - $x$: Spezifische Beobachtung von $X$
> - $K$: Gesamtzahl der Klassen
> - $\pi_k$: A-priori-Wahrscheinlichkeit für Klasse $k$
> - $f_k(x)$: Dichtefunktion für $X$ in Klasse $k$
> - $\text{Pr}(Y = k|X = x)$: Posteriori-Wahrscheinlichkeit für Klasse $k$ gegeben $X = x$
> - $\text{Pr}(X = x|Y = k)$: Likelihood von $X = x$ gegeben Klasse $k$
> - $\text{Pr}(Y = k)$: A-priori-Wahrscheinlichkeit für Klasse $k$
> - $\text{Pr}(X = x)$: Gesamtwahrscheinlichkeit von $X = x$

was macht LDA genau?
?
LDA macht eine Dimensions Reduzierung aehnlich zu PCA. Es projeziert jedoch nicht die Punkte, sondern macht einen neuen Space und Projeziert dann die Punkte auf diesen Space. LDA erstellt eine neue Axe die die Distanz der durchschnittlichen distance zwischen zwei categorien minizmiert.
![Pasted image 20240708233905.png](/img/user/Files/Pasted%20image%2020240708233905.png)

> [!Quadratic Discriminant Analysis (QDA)]
>
> QDA lockert die Annahme einer gemeinsamen Kovarianzmatrix und erlaubt jede Klasse ihre eigene Kovarianzmatrix zu haben, was es flexibler macht, aber auch zu höherer Varianz führt.

> [!K-Nearest Neighbors (KNN)]
>
> KNN klassifiziert Beobachtungen basierend auf den \( K \) nächsten Nachbarn:
> $$
> Pr(Y=j|X=x_0) = \frac{1}{K} \sum_{i \in N_0} I(y_i = j)
> $$
> - Die Wahl von \( K \) beeinflusst die Flexibilität und Bias-Varianz-Abwägung des Modells.


### Wann LDA und wann QDA verwenden
Wann soll man LDA verwenden anstatt Log reg?
?
> [!Wann LDA und wann QDA verwenden]
> 
> **LDA (Linear Discriminant Analysis):**
> - Verwenden, wenn die Kovarianzmatrizen der Klassen ungefähr gleich sind.
> - Geeignet für große Datensätze mit vielen Beobachtungen pro Klasse.
> - Stabiler bei kleineren Datensätzen.
> 
> **QDA (Quadratic Discriminant Analysis):**
> - Verwenden, wenn die Kovarianzmatrizen der Klassen unterschiedlich sind.
> - Nützlich für komplexere Modelle mit größeren Unterschieden zwischen den Klassen.
> - Erfordert größere Datensätze, da es mehr Parameter schätzt.
> 
> **Logistische Regression:**
> - Verwenden, wenn eine lineare Entscheidungsgrenze erwartet wird.
> - Flexibler als LDA bei kleineren Datensätzen und weniger Annahmen über die Verteilung der Prädiktoren.
> - Wird nicht verwendet, wenn die Daten nicht gut durch eine lineare Entscheidungsgrenze getrennt werden können.


## Generative Models for Classification
Wie sehen Gernerative Modelle aus?
?
![Pasted image 20240704131017.png](/img/user/Files/Pasted%20image%2020240704131017.png)![Pasted image 20240704131210.png](/img/user/Files/Pasted%20image%2020240704131210.png)


#### LDA (verwenden bei weniger Daten)
### Linear Discriminant Analysis (LDA)
wie sieht LDA aus?
?
> [!Linear Discriminant Analysis (LDA)]
> 
> LDA ist eine Methode zur Klassifizierung, die die Varianz zwischen den Klassen maximiert und die Varianz innerhalb der Klassen minimiert. Die Entscheidungsregel basiert auf der größten diskriminanten Funktion \( \delta_k(x) \):
> $$
> \delta_k(x) = x^T \Sigma^{-1} \mu_k - \frac{1}{2} \mu_k^T \Sigma^{-1} \mu_k + \log(\pi_k)
> $$
> -  $x$: Eingabevektor
> - $Sigma$: Gemeinsame Kovarianzmatrix
> - $mu_k$: Mittelwert der Klasse \( k \)
> - $pi_k$: A-priori-Wahrscheinlichkeit der Klasse \( k \)

### Quadratic Discriminant Analysis (QDA)
Wie sieht QDA aus?
?
> [!Quadratic Discriminant Analysis (QDA)]
> 
> QDA ist eine Erweiterung von LDA, bei der jede Klasse ihre eigene Kovarianzmatrix hat. Die Entscheidungsregel basiert auf der größten diskriminanten Funktion \( \delta_k(x) \):
> $$
> \delta_k(x) = -\frac{1}{2} \log|\Sigma_k| - \frac{1}{2} (x - \mu_k)^T \Sigma_k^{-1} (x - \mu_k) + \log(\pi_k)
> $$
> - \( x \): Eingabevektor
> - \( \Sigma_k \): Kovarianzmatrix der Klasse \( k \)
> - \( \mu_k \): Mittelwert der Klasse \( k \)
> - \( \pi_k \): A-priori-Wahrscheinlichkeit der Klasse \( k \)

![Pasted image 20240704133835.png](/img/user/Files/Pasted%20image%2020240704133835.png)

Was ist LDA und wie ist die Formel
?
![Pasted image 20240704134153.png](/img/user/Files/Pasted%20image%2020240704134153.png)

Univariater Fall:
![Pasted image 20240704134348.png](/img/user/Files/Pasted%20image%2020240704134348.png)

Multivariater Fall:
![Pasted image 20240704134436.png](/img/user/Files/Pasted%20image%2020240704134436.png)

#### QDA (verwenden bei vielen Daten)
![Pasted image 20240704134059.png](/img/user/Files/Pasted%20image%2020240704134059.png)


#### Naive bayes NB (multivariat)
![Pasted image 20240704134928.png](/img/user/Files/Pasted%20image%2020240704134928.png)


Wie werden die Optimalen Betas in Logistischer Regression berechnen? :: Maximum Likelihood

Wie werden die Optimalen Betas in LDA berechnet? :: Wir passen eine Normalverteilung an unsere Daten an.



#### Performance Messung bei Binärklassifikation

Confusion Matrix:



### Accuracy
Wie ist die Formel fuer die Accuracy?
?
> [!Accuracy]
> 
> Accuracy ist der Anteil der korrekten Vorhersagen:
> $$
> \text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}
> $$

### Sensitivity / Recall
Was ist Sensitity / Recall?
?
> [!Sensitivity / Recall]
> 
> Sensitivity (auch Recall genannt) ist ein Maß dafür, wie gut ein Modell tatsächlich positive Fälle korrekt identifiziert. Es ist der Anteil der tatsächlich positiven Fälle, die vom Modell korrekt als positiv klassifiziert wurden.
> 
> Die Formel für Sensitivity / Recall lautet:
> $$
> \text{Sensitivity} = \text{Recall} = \frac{TP}{TP + FN}
> $$
> - \( TP \): True Positives (Anzahl der korrekt als positiv klassifizierten positiven Fälle)
> - \( FN \): False Negatives (Anzahl der tatsächlich positiven, aber als negativ klassifizierten Fälle)
>
>Ein hoher Recall-Wert bedeutet, dass das Modell nur wenige tatsächliche positive Fälle übersieht.

### Precision
Was ist die Precison?
?
> [!Precision]
> 
> Precision ist ein Maß dafür, wie viele der als positiv klassifizierten Fälle tatsächlich positiv sind. Es ist der Anteil der korrekt vorhergesagten positiven Fälle an allen vorhergesagten positiven Fällen.
> 
> Die Formel für Precision lautet:
> $$
> \text{Precision} = \frac{TP}{TP + FP}
> $$
> - \( TP \): True Positives (Anzahl der korrekt als positiv klassifizierten positiven Fälle)
> - \( FP \): False Positives (Anzahl der fälschlicherweise als positiv klassifizierten negativen Fälle)
> 
> Ein hoher Precision-Wert bedeutet, dass das Modell nur wenige negative Fälle fälschlicherweise als positiv klassifiziert. dass das Modell nur wenige tatsächliche positive Fälle übersieht.


### Specificity
Was sagt die Specifity aus?
?
> [!Specificity]
> 
> Specificity misst, wie gut ein Modell tatsächlich negative Fälle korrekt identifiziert. Es ist der Anteil der tatsächlich negativen Fälle, die vom Modell korrekt als negativ klassifiziert wurden.
> 
> Die Formel für Specificity lautet:
> $$
> \text{Specificity} = \frac{TN}{TN + FP}
> $$
> - \( TN \): True Negatives (Anzahl der korrekt als negativ klassifizierten negativen Fälle)
> - \( FP \): False Positives (Anzahl der fälschlicherweise als positiv klassifizierten negativen Fälle)
>
>Ein hoher Specificity-Wert bedeutet, dass das Modell nur wenige tatsächliche negative Fälle fälschlicherweise als positiv klassifiziert.


### Trade-off zwischen Specificity, Recall und Precision
Erklaere den Trade off zwischen Specifity recall und Precision?
?
> [!Trade-off zwischen Specificity, Recall und Precision]
> 
> **Specificity**, **Recall** und **Precision** sind wichtige Maße für die Leistungsfähigkeit eines Klassifikationsmodells. Änderungen in einem Maß können oft zu Kompromissen in den anderen führen:
> - **Recall vs. Precision:** Ein hohes Recall führt oft zu einem niedrigeren Precision, da mehr positive Vorhersagen gemacht werden, was auch die False Positives erhöht. Umgekehrt führt ein hohes Precision oft zu einem niedrigeren Recall.
> - **Recall vs. Specificity:** Ein hohes Recall bedeutet, dass mehr tatsächliche Positive erkannt werden, was die Anzahl der False Negatives verringert, aber die Anzahl der False Positives erhöhen kann, was die Specificity verringert.
> - **Specificity vs. Precision:** Ein hohes Specificity bedeutet, dass viele tatsächliche Negative korrekt erkannt werden, was die Anzahl der False Positives verringert und somit Precision erhöht.

### Decision Threshold
Erklaere den Descision Threshold
?
> [!Decision Threshold]
>
> Der **Decision Threshold** ist der Schwellenwert, ab dem eine Beobachtung als positiv klassifiziert wird. Durch Anpassen des Decision Threshold kann man den Trade-off zwischen Recall, Precision und Specificity steuern:
> - **Niedriger Threshold:** Erhöht Recall, verringert Specificity und Precision.
> - **Hoher Threshold:** Erhöht Specificity und Precision, verringert Recall.
> - Die Wahl des geeigneten Decision Threshold hängt von den spezifischen Anforderungen und Prioritäten der Anwendung ab.
![Pasted image 20240704140802.png](/img/user/Files/Pasted%20image%2020240704140802.png)
<!--SR:!2024-07-08,1,230-->

ROC Curve
?
![Pasted image 20240704140929.png](/img/user/Files/Pasted%20image%2020240704140929.png)


## Poisson Verteilung / Poisson Regression 


Wie sieht die Poisson Verteilung aus?
?
![Pasted image 20240704141217.png](/img/user/Files/Pasted%20image%2020240704141217.png)


### Poisson Regression
Was ist die Poisson Regression?
?
> [!Poisson Regression]
> 
> Poisson Regression wird verwendet, um die Anzahl der Ereignisse in einem festen Intervall zu modellieren. Es ist geeignet für Zähldaten, die die Poisson-Verteilung befolgen.
> 
> Die Modellgleichung lautet:
> $$
> \log(\lambda) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_p X_p
> $$
> 
> wobei:
> - $\lambda$ die erwartete Anzahl der Ereignisse ist.
> - $X_1, X_2, \ldots, X_p$ die Prädiktoren sind.
> - $\beta_0, \beta_1, \ldots, \beta_p$ die Regressionskoeffizienten sind.
> 
> Die linke Seite der Gleichung ist der Logarithmus der Rate, und die rechte Seite ist eine lineare Funktion der Prädiktoren.

Was macht die Poissonverteilung für eine Starke Annahme? :: Varianz = Erwartungswert

![Pasted image 20240704141659.png](/img/user/Files/Pasted%20image%2020240704141659.png)

Durch das Umschreiben von den Theremen, kann man schön die rechte Seite immer eine Linreg machen
?
All diese Regressionen hängen zusammen, ungefähr die gleiche Struktur in einer Theorie. Meistens reicht eine Funktion ein eine GLM funktion. --> Linkfunction
![Pasted image 20240704142819.png](/img/user/Files/Pasted%20image%2020240704142819.png)![Pasted image 20240704142838.png](/img/user/Files/Pasted%20image%2020240704142838.png)

### Generalized Linear Models (GLMs)
Was sind die GLM?
?
> [!Generalized Linear Models (GLMs)]
> 
> **Übersicht:** In diesem Kurs wurden drei GLMs behandelt: Gaussian, Binomial und Poisson.
> 
> **Link-Funktion:** Transformation des Mittelwerts durch eine lineare Funktion:
> $$
> \eta(\mathbb{E}(Y|X_1, X_2, \ldots, X_p)) = \beta_0 + \beta_1 X_1 + \cdots + \beta_p X_p
> $$
> - Linear: $\eta(\mu) = \mu$
> - Logistisch: $\eta(\mu) = \log(\mu / (1 - \mu))$
> - Poisson: $\eta(\mu) = \log(\mu)$
> 
> **Varianzfunktionen:** Jede GLM hat charakteristische Varianzfunktionen.
> 
> **Modellanpassung:** Die Modelle werden mittels Maximum-Likelihood angepasst. Zusammenfassungen werden in R mit der Funktion `glm()` erzeugt.
> 
> **Weitere GLMs:** Gamma, Negative-binomial, Inverse Gaussian und mehr.



## Resampling Methods
Was ist eine Cross Validation?
?
> [!Cross-Validation]
>
> Cross-Validation ist eine Methode zur Schätzung des Testfehlers eines Modells, indem das verfügbare Trainingsdaten in mehrere Teilmengen aufgeteilt wird.

### Validation Set Approach
Was ist der Validation Set Approche?
?
>[!Validation Set Approach]
> - Das Trainingsdatensatz wird zufällig in Trainings- und Testmengen aufgeteilt.
> - Modell wird auf das Trainingsset angepasst und auf das Testset angewendet.
> - Der Fehler im Testset dient als Schätzung für den Testfehler.
>
> Nachteile:
> 1. Hohe Variabilität, abhängig von der zufälligen Aufteilung.
> 2. Das Modell wird auf weniger Daten trainiert, was den Fehler überschätzen kann.

### Leave-One-Out Cross-Validation (LOOCV)
Was ist LOOCV oder auch Leave one Out Cross Validation?
?
>[!Leave-One-Out Cross-Validation (LOOCV)]
> - Jede Beobachtung wird einmal als Testset verwendet, während der Rest als Trainingsset dient.
> - Modell wird \( n \) Mal angepasst und der Durchschnittsfehler wird berechnet.
>
> Vorteile:
> 1. Weniger variabel, da alle Datenpunkte verwendet werden.
> 2. Weniger Bias, da fast das gesamte Datenset verwendet wird.
>
> Nachteil:
> 1. Kann rechnerisch aufwendig sein.

### K-Fold Cross-Validation
Was ist KFold Cross Validation?
?
>[!K-Fold Cross-Validation]
> - Daten werden in \( K \) gleichgroße Gruppen aufgeteilt.
> - Jede Gruppe wird einmal als Testset und der Rest als Trainingsset verwendet.
> - Durchschnittsfehler wird berechnet.
>
> Vorteile:
> 1. Weniger rechnerisch aufwendig als LOOCV.
> 2. Besseres Bias-Varianz-Verhältnis.
>
> Typischerweise wird \( K = 5 \) oder \( K = 10 \) gewählt.

Was ist Bootstrapping?
?
> [!Bootstrap]
>
> Der Bootstrap ist eine Methode zur Schätzung der Unsicherheit eines Modells oder Parameters durch wiederholtes Ziehen von Stichproben mit Zurücklegen aus dem Originaldatensatz.
>
> - Beispiel: Schätzung des Risikos einer Investition durch Bootstrapping von Renditen.
> - Ein Datensatz wird mehrfach mit Zurücklegen gezogen, um viele Bootstrapped-Datensätze zu erzeugen.
> - Diese werden verwendet, um Schätzungen und deren Variabilität zu berechnen.

Cross_validation:

Bootrap --> Used in Random Forest see Bagging: 
![Pasted image 20240704213617.png](/img/user/Files/Pasted%20image%2020240704213617.png)



## Linear Model Selection & Regularization
Hier sind die wichtigsten Konzepte und Formeln von der angegebenen Webseite im Stil der bisherigen Erklärungen:

### Best Subset Selection
Was ist Subset Selection?
?
> [!Best Subset Selection]
> 
> Best Subset Selection passt separate Modelle für jede mögliche Kombination der Prädiktoren an:
> $$
> y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_p X_p + \epsilon
> $$
> Das beste Modell wird basierend auf Kriterien wie \(R^2\) oder Kreuzvalidierungsfehler ausgewählt.

### Stepwise Selection
Was ist Stepwise Selection?
?
> [!Stepwise Selection]
> 
> Stepwise Selection ist eine Methode zur Auswahl der besten Prädiktoren für ein Modell, indem Variablen iterativ hinzugefügt oder entfernt werden. Es gibt drei Hauptarten: dabei wird das p-value verwendet welcher der hoecchste hat entfernt oder tiefsteter hinzugefuegt.
> 
> **Forward Selection:**
> - Beginnt mit keinem Prädiktor und fügt schrittweise den Prädiktor hinzu, der die Modellanpassung am meisten verbessert.
> 
> **Backward Selection:**
> - Beginnt mit allen Prädiktoren und entfernt schrittweise den Prädiktor, der die Modellanpassung am wenigsten verschlechtert.
> 
> **Stepwise Selection:**
> - Kombiniert Forward und Backward Selection, indem es Prädiktoren hinzufügt und entfernt, um das beste Modell zu finden.


### Optimal Model Selection
Was ist die Optimale Model Section?
?
> [!Optimal Model Selection]
> 
> Die Auswahl des besten Modells erfolgt durch Schätzung des Testfehlers mittels Kreuzvalidierung oder Anpassung des Trainingsfehlers (z.B. \(C_p\), \(AIC\), \(BIC\), adjusted-\(R^2\)).

### Shrinkage Methods
Was macht eine Shrinkage Method?
?
> [!Shrinkage Methods]
> 
> Shrinkage-Methoden passen ein Modell mit allen Prädiktoren an und schrumpfen die Koeffizienten in Richtung Null.

### Ridge Regression
Wie sieht die Ridge Regression aus?
?
> [!Ridge Regression]
>
> Minimiert die Funktion:
> $$
> \text{RSS} + \lambda \sum_{j=1}^{p} \beta_{j}^2
> $$
> Dies reduziert die Varianz auf Kosten eines kleinen Bias.
<!--SR:!2024-07-08,1,230-->

### Lasso Regression
Wie sieht die Lasso Regression aus?
?
> [!Lasso Regression]
> 
> Minimiert die Funktion:
> $$
> \text{RSS} + \lambda \sum_{j=1}^{p} |\beta_{j}|
> $$
> Lasso schrumpft einige Koeffizienten auf genau Null, was eine Variablenselektion ermöglicht.

### Dimension Reduction Methods
Was ist eine Dimensions Reduction?
?
> [!Dimension Reduction Methods]
> 
> Reduzieren die Dimensionen des Datensatzes durch Projektion auf ein \(M\)-dimensionales Teilraum.

### Principal Components Analysis (PCA)
Fuer was verwendet man PCA?\
?
> [!Principal Components Analysis (PCA)]
> 
> Identifiziert die Hauptrichtungen der Variabilität in den Daten und projiziert die Prädiktoren auf diese Komponenten.

### Partial Least Squares (PLS)
Was ist Partial Least Squares?
?
> [!Partial Least Squares (PLS)]
> 
> Partial Least Squares (PLS) ist eine Technik zur Dimensionenreduktion, die sowohl die Prädiktoren als auch die Antwortvariablen berücksichtigt. PLS projiziert die Prädiktoren auf neue latente Variablen (Komponenten), die maximale Kovarianz mit der Antwortvariablen haben.
> 
> **Algorithmus:**
> 1. Berechnung der Gewichtungsvektoren, die die Prädiktoren und die Antwortvariablen maximieren.
> 2. Projektion der Prädiktoren und der Antwortvariablen auf diese Gewichtungsvektoren.
> 3. Anpassen eines linearen Modells an die projizierten Daten.

PLS ist besonders nützlich, wenn die Anzahl der Prädiktoren groß ist und Multikollinearität vorliegt. Weitere Details finden Sie auf [ISLR Chapter 6 - Linear Model Selection & Regularization](https://www.bijenpatel.com/guide/islr/linear-model-selection-regularization/).

### Considerations in High Dimensions
Was sollte man in hohen Dimensionen beachten?
?
> [!Considerations in High Dimensions]
>
> Bei vielen Prädiktoren sollte man Methoden wie Subset Selection, Ridge Regression, Lasso oder PCA verwenden. Traditionelle Maßzahlen wie \(R^2\) sind ungeeignet; stattdessen sollte man Kreuzvalidierungsfehler berichten.
<!--SR:!2024-07-08,1,230-->

Weitere Details und ausführliche Erklärungen finden Sie auf der Webseite [ISLR Chapter 6 - Linear Model Selection & Regularization](https://www.bijenpatel.com/guide/islr/linear-model-selection-regularization/).


### AIC (Akaike Information Criterion)
AIC Akaike Information Criterion
?
> [!Akaike Information Criterion (AIC)]
> 
> AIC ist ein Maß zur Modellbewertung, das sowohl die Anpassungsgüte als auch die Komplexität des Modells berücksichtigt:
> $$
> \text{AIC} = 2k - 2\log(L)
> $$
> - \( k \): Anzahl der geschätzten Parameter
> - \( L \): Maximierter Wert der Likelihood-Funktion des Modells

### BIC (Bayesian Information Criterion)
BIC Bayesian Information Criterion
?
> [!Bayesian Information Criterion (BIC)]
> 
> BIC ist ähnlich wie AIC, bestraft jedoch komplexere Modelle stärker:
> $$
> \text{BIC} = \log(n)k - 2\log(L)
> $$
> - \( n \): Anzahl der Datenpunkte

### Mean Squared Error (MSE)
MEAN Square Error
?
> [!Mean Squared Error (MSE)]
> 
> MSE misst den durchschnittlichen quadratischen Fehler zwischen den beobachteten und vorhergesagten Werten:
> $$
> \text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
> $$
> - \( y_i \): Beobachteter Wert
> - \( \hat{y}_i \): Vorhergesagter Wert

### Adjusted \( R^2 \)
Adjusted R2?
?
> [!Adjusted \( R^2 \)]
> 
> Adjusted \( R^2 \) ist eine Anpassung des \( R^2 \)-Werts, die die Anzahl der Prädiktoren im Modell berücksichtigt:
> $$
> \text{Adjusted } R^2 = 1 - \frac{(1 - R^2)(n - 1)}{n - k - 1}
> $$
> - \( R^2 \): Bestimmtheitsmaß
> - \( n \): Anzahl der Beobachtungen
> - \( k \): Anzahl der Prädiktoren



Die Probleme von Regularisierung / Shrinkage
?
- Problem 1:  $p > n$
$$
X \in \mathbb{R}^{n \times p}, \quad \text{rank}(X) = n \\
X^T X \in \mathbb{R}^{p \times p}, \quad \text{rank}(X^T X) = n \leq p \\
\Rightarrow \nexists (X^T X)^{-1}
$$
- Problem 2: Overfitting
$$
\hat{Y}_i = \beta_0 + \beta_1 x + \beta_2 x^2 + \ldots \\
\Rightarrow \beta \text{ mit großem i werden sehr groß}
$$
- Problem 3: Feature Selection



Regularisierung
?
$$
\text{Regularisierung:} \\
L = \sum_{i=1}^n (y_i - \hat{y}_i)^2 + \lambda \sum_{i=1}^p |\beta_i|^q \\
\text{RSS} \quad \text{Regularisierungsterm} \quad \text{Penalty} \\
\lambda \in \mathbb{R}, \, \lambda > 0 \\
q = 1 \quad \text{oder} \quad q = 2
$$

## Moving Boyond Linearity

Hier sind die wichtigsten Konzepte und Formeln von der angegebenen Webseite im Stil der bisherigen Erklärungen:

### Polynomial Regression
Wie sieht die Polynominale Regresion aus?
?
> [!Polynomial Regression]
> 
> Polynomial regression erweitert die lineare Regression durch Hinzufügen zusätzlicher Prädiktoren, die Potenzen der ursprünglichen Prädiktoren sind:
> 
> $$
> Y = \beta_0 + \beta_1X + \beta_2X^2 + \beta_3X^3 + \cdots + \beta_dX^d + \epsilon
> $$
> 
> Dies ermöglicht das Modellieren nichtlinearer Beziehungen zwischen Prädiktoren und Antwortvariablen.
> 
![Pasted image 20240708171743.png](/img/user/Files/Pasted%20image%2020240708171743.png)
### Step Functions
Was ist eine Step Function?
?
> [!Step Functions]
> 
> Step Functions unterteilen den Bereich von \(X\) in Intervalle und passen innerhalb jedes Intervalls eine Konstante an:
> 
> $$
> C_k(X) = I(c_{k-1} \leq X < c_k)
> $$
> 
> $$
> Y = \beta_0 + \beta_1C_1(X) + \beta_2C_2(X) + \cdots + \beta_KC_K(X) + \epsilon
> $$
> 
> Dies ermöglicht unterschiedliche konstante Werte für verschiedene Bereiche von \(X\).
> 
> ![Pasted image 20240708172311.png](/img/user/Files/Pasted%20image%2020240708172311.png)
> I ist eine Idicator funktion die binary zurueck gibt.


Was sind gute Eigenschaften von Stepfunctions?
?
![Pasted image 20240708172552.png](/img/user/Files/Pasted%20image%2020240708172552.png)
### Basis Functions
Wie sind Basis Function definiert?
?
> [!Basis Functions]
> 
> Basis Functions wenden eine Familie von Funktionen auf einen Prädiktor an:
> 
> $$
> Y = \beta_0 + \beta_1b_1(X) + \beta_2b_2(X) + \cdots + \beta_Kb_K(X) + \epsilon
> $$
> 
> Beispiele sind Polynomiale und Stückweise Konstante.

### Piecewise Polynomial Regression
Was ist die Piecewise Polynominal Regression?
?
> [!Piecewise Polynomial Regression]
> 
> Piecewise Polynomial Regression unterteilt den Prädiktorraum in Intervalle und passt in jedem Intervall ein separates Polynom an. Dadurch können komplexe, nichtlineare Beziehungen modelliert werden.
> 
> **Stückweise Lineare Regression:**
> $$
> Y = \begin{cases} 
> \beta_{0,1} + \beta_{1,1} X & \text{für } a \leq X < b \\
> \beta_{0,2} + \beta_{1,2} X & \text{für } b \leq X < c \\
> \vdots & \vdots \\
> \beta_{0,k} + \beta_{1,k} X & \text{für } z \leq X < w
> \end{cases}
> $$
> 
> **Stückweise Polynomiale höheren Grades:**
> $$
> Y = \begin{cases} 
> \sum_{j=0}^{d} \beta_{j,1} X^j & \text{für } a \leq X < b \\
> \sum_{j=0}^{d} \beta_{j,2} X^j & \text{für } b \leq X < c \\
> \vdots & \vdots \\
> \sum_{j=0}^{d} \beta_{j,k} X^j & \text{für } z \leq X < w
> \end{cases}
> $$
> 
> - \( \beta_{j,i} \): Koeffizienten der Polynomiale im \(i\)-ten Intervall
> - \( d \): Grad des Polynoms
> - \( a, b, c, z, w \): Grenzwerte der Intervalle
> 
> ![Pasted image 20240708173056.png](/img/user/Files/Pasted%20image%2020240708173056.png)
> Piecewise Polynomial Regression bietet Flexibilität und Genauigkeit, indem sie die Modellkomplexität auf die Daten anpasst.

### Lineare Splines
Was sind Lineare Splines?
> [!Lineare Splines]
> 
> Ein linearer Spline mit Knoten bei $\xi_k$, $k = 1$, $\ldots, K$ ist ein stückweise lineares Polynom, das an jedem Knoten kontinuierlich ist.
> 
> Wir können dieses Modell darstellen als:
> $$
> y_i = \beta_0 + \beta_1 b_1(x_i) + \beta_2 b_2(x_i) + \cdots + \beta_{K+1} b_{K+1}(x_i) + \epsilon_i
> $$
> 
> wobei die \(b_k\) Basisfunktionen sind:
> $$
> b_1(x_i) = x_i
> $$
> $$
> b_{k+1}(x_i) = (x_i - \xi_k)_+, \quad k = 1, \ldots, K
> $$
> 
> Hier bedeutet \(()_+\) den positiven Teil, d.h.
> $$
> (x_i - \xi_k)_+ = 
> \begin{cases} 
> x_i - \xi_k & \text{wenn } x_i > \xi_k \\
> 0 & \text{sonst}
> \end{cases}
> $$
> - $y_i$: Beobachteter Wert für die $i$-te Beobachtung
> - $\beta_0, \beta_1, \ldots, \beta_{K+1}$: Regressionskoeffizienten
> - $b_k(x_i)$: Basisfunktionen
> - $x_i$: Prädiktorwert für die $i$-te Beobachtung
> - $\xi_k$: Knotenpunkte
> - $\epsilon_i$: Fehlerterm


### Kubische Splines
Was sind cubicsplines?
?
> [!Kubische Splines]
> 
> Ein kubischer Spline mit Knoten bei $\xi_k$, $k = 1, \ldots, K$, ist ein stückweise kubisches Polynom mit stetigen Ableitungen bis zur Ordnung 2 an jedem Knoten.
> 
> Wir können dieses Modell mit abgeschnittenen Potenz-Basisfunktionen darstellen:
> $$
> y_i = \beta_0 + \beta_1 b_1(x_i) + \beta_2 b_2(x_i) + \cdots + \beta_{K+3} b_{K+3}(x_i) + \epsilon_i
> $$
> 
> wobei:
> - $b_1(x_i) = x_i$
> - $b_2(x_i) = x_i^2$
> - $b_3(x_i) = x_i^3$
> - $b_{k+3}(x_i) = (x_i - \xi_k)_+^3, \quad k = 1, \ldots, K$
> 
> Hier bedeutet $(\cdot)_+$ den positiven Teil:
> $$
> (x_i - \xi_k)_+^3 = 
> \begin{cases} 
> (x_i - \xi_k)^3 & \text{wenn } x_i > \xi_k \\
> 0 & \text{sonst}
> \end{cases}
> $$
> - $y_i$: Beobachteter Wert für die $i$-te Beobachtung
> - $\beta_0, \beta_1, \ldots, \beta_{K+3}$: Regressionskoeffizienten
> - $b_k(x_i)$: Basisfunktionen
> - $x_i$: Prädiktorwert für die $i$-te Beobachtung
> - $\xi_k$: Knotenpunkte
> - $\epsilon_i$: Fehlerterm


### Natürliche kubische Splines
Was ist ein natuerlicher kubischer spline? 
?
> [!Natürliche kubische Splines]
> 
> Ein natürlicher kubischer Spline extrapoliert linear über die Randknoten hinaus. Dies fügt 4 (2 × 2) zusätzliche Einschränkungen hinzu und ermöglicht es uns, mehr interne Knoten für die gleichen Freiheitsgrade wie ein regulärer kubischer Spline zu setzen.
> 
> - **Randknoten:** Stellen sicher, dass der Spline an den Rändern linear wird.
> - **Freiheitsgrade:** Anzahl der Parameter, die zur Anpassung des Splines verwendet werden.
> 
> Die Grafik zeigt den Unterschied zwischen einem natürlichen kubischen Spline (rote Linie) und einem regulären kubischen Spline (blaue Linie).
> ![Pasted image 20240709015135.png](/img/user/Files/Pasted%20image%2020240709015135.png)


Warum sind Polynomial Regressions schlechter als Splines?
?
![Pasted image 20240708174005.png](/img/user/Files/Pasted%20image%2020240708174005.png)



### Regression Splines
Was sind Regression splines und wie Berechnet man sie?
?
> [!Regression Splines]
> 
> Regression Splines erweitern die Polynom- und Stückweise-Konstante-Regression:
> 
> $$
> Y = \beta_{0k} + \beta_{1k}X + \beta_{2k}X^2 + \cdots + \beta_{dk}X^d + \epsilon \quad \text{für } X \text{ in jedem Intervall}
> $$
> 
> Splines sind glatt und kontinuierlich an den Knotenpunkten.

### Smoothing Splines
Was sind Smoothing Splines und wie berechnet man sie?
?
> [!Smoothing Splines]
> Das gute an Smoothing Splines ist, dass man splines fitten kann ohne, dass man die Knots placen muss.
> 
> Smoothing Splines minimieren die Summe der quadrierten Fehler und eine Glattheitsstrafe:
> 
> $$
> \sum_{i=1}^n (y_i - g(x_i))^2 + \lambda \int (g''(t))^2 dt
> $$
> 
> Dies führt zu glatten Funktionen, die gut zu den Daten passen.
> ![Pasted image 20240709015426.png](/img/user/Files/Pasted%20image%2020240709015426.png)

### Local Regression
Was ist Local Regression und wie sieht die Formel aus?
?
> [!Local Regression]
> 
> Local Regression passt lokale lineare Modelle an Punkte nahe einem Zielpunkt an:
> 
> $$
> \sum_{i=1}^n K_{i0}(y_i - \beta_0 - \beta_1X_i)^2
> $$
> 
> Dies ermöglicht flexible, nichtlineare Anpassungen.
> 
> ![Pasted image 20240709015543.png](/img/user/Files/Pasted%20image%2020240709015543.png)

### Generalized Additive Models (GAMs)
was sind General additive model?
?
> [!Generalized Additive Models (GAMs)]
> 
> GAMs ermöglichen nichtlineare Funktionen jedes Prädiktors, während sie Additivität beibehalten:
> 
> $$
> Y = \beta_0 + \sum_{j=1}^p f_j(X_j) + \epsilon
> $$
> 
> GAMs kombinieren Flexibilität und Interpretierbarkeit.

### Generalized Additive Models (GAMs)
Wie kann die formel von Gams ohne summe daargestellt werden?
?
> [!Generalized Additive Models (GAMs)]
> 
> GAMs erlauben flexible Nichtlinearitäten in mehreren Variablen, behalten aber die additive Struktur linearer Modelle bei.
> $$
> y_i = \beta_0 + f_1(x_{i1}) + f_2(x_{i2}) + \cdots + f_p(x_{ip}) + \epsilon_i
> $$
> 
> - $y_i$: Beobachteter Wert für die $i$-te Beobachtung
> - $\beta_0$: Interzept
> - $f_j(x_{ij})$: Glättungsfunktionen der Prädiktoren $x_{ij}$
> - $x_{ij}$: Prädiktorwert für die $i$-te Beobachtung und den $j$-ten Prädiktor
> - $\epsilon_i$: Fehlerterm
> 
> Die Diagramme zeigen, wie die Funktionen $f_j$ die Beziehung zwischen den Prädiktoren (Jahr, Alter, Bildung) und der Antwortvariablen modellieren.


### Generalized Additive Models (GAMs)
Koennen in Gams auch wechselwirkungen einbezogen werden? 
?
> [!Generalized Additive Models (GAMs)]
> 
> GAMs sind additiv, obwohl Wechselwirkungen niedriger Ordnung auf natürliche Weise durch bivariate Glätter oder Wechselwirkungen der Form $ns(\text{age}, df = 5) : ns(\text{year}, df = 5)$ einbezogen werden können.
> 
> - **Additive Modelle:** Jede Komponente wird separat angepasst und addiert.
> - **Bivariate Glätter:** Glättungsmethoden für zwei Variablen gleichzeitig.
> - **Wechselwirkungen:** Interaktionen zwischen Variablen, die im Modell berücksichtigt werden.
> - 
>GAMs bieten Flexibilität bei der Modellierung nichtlinearer Beziehungen und Wechselwirkungen in den Daten.

### GAMs für Klassifikation
Wie verwendet man Gams fuer Klassification?
?
> [!GAMs für Klassifikation]
> 
> Generalized Additive Models (GAMs) können auch für Klassifikationsprobleme verwendet werden. Die logistische Regression wird als additive Modelle erweitert:
> $$
> \log \left( \frac{p(X)}{1 - p(X)} \right) = \beta_0 + f_1(X_1) + f_2(X_2) + \cdots + f_p(X_p)
> $$
> 
> - $p(X)$: Wahrscheinlichkeit des Ereignisses
> - $\beta_0$: Interzept
> - $f_j(X_j)$: Glättungsfunktionen der Prädiktoren $X_j$
> 
> In R kann dies mit der `gam()` Funktion durchgeführt werden, wie im Beispiel:
> $$
> \text{gam}(I(\text{wage} > 250) \sim \text{year} + s(\text{age}, \text{df} = 5) + \text{education}, \text{family} = \text{binomial})
> $$
> - $\text{year}$: Jahr
> - $\text{age}$: Alter
> - $\text{education}$: Bildung

Polynominal Regression (Linear Regression)
?
- Hat viel mehr gefahren wie Nutzen
$$
y_i = \beta_0 + \beta_1 x_i + \beta_2 x_i^2 + \beta_3 x_i^3 + \cdots + \beta_d x_i^d + \epsilon_i
$$



Polynominal Regression (Logitic Regression)
?
$$
\Pr(y_i > 250 \mid x_i) = \frac{\exp(\beta_0 + \beta_1 x_i + \beta_2 x_i^2 + \cdots + \beta_d x_i^d)}{1 + \exp(\beta_0 + \beta_1 x_i + \beta_2 x_i^2 + \cdots + \beta_d x_i^d)}
$$



Was sind Step Functions
?
![Pasted image 20240705091719.png](/img/user/Files/Pasted%20image%2020240705091719.png)



Step Function
?
$$
y_i = \beta_0 + \beta_1 C_1(x_i) + \beta_2 C_2(x_i) + \cdots + \beta_K C_K(x_i) + \epsilon_i
$$
![Pasted image 20240705092245.png](/img/user/Files/Pasted%20image%2020240705092245.png)


Step Function als Generalisiertes Modell Beispiel Logitische Regression
?
![Pasted image 20240705092419.png](/img/user/Files/Pasted%20image%2020240705092419.png)



Regression splines
?
![Pasted image 20240705092837.png](/img/user/Files/Pasted%20image%2020240705092837.png)




Local regression
?
![Pasted image 20240705102032.png](/img/user/Files/Pasted%20image%2020240705102032.png)

Generalized additive models
?
### Generalized Additive Models (GAMs)
Was sind GAMS?
?
> [!Generalized Additive Models (GAMs)]
>
> Generalized Additive Models (GAMs) ermöglichen es, die Beziehung zwischen der Antwortvariablen und mehreren Prädiktoren durch additive nichtlineare Funktionen darzustellen.
>
> Das Modell wird wie folgt formuliert:
> $$
> Y = \beta_0 + f_1(X_1) + f_2(X_2) + \cdots + f_p(X_p) + \epsilon
> $$
>
> - $Y$ ist die Antwortvariable.
> - $\beta_0$ ist der Interzept.
> - $f_j(X_j)$ sind nichtlineare Glättungsfunktionen der Prädiktoren $X_j$.
> - $\epsilon$ ist der Fehlerterm.
>
> GAMs kombinieren Flexibilität und Interpretierbarkeit, da jede nichtlineare Funktion einzeln geschätzt und interpretiert werden kann.
> 
> ![Pasted image 20240709020308.png](/img/user/Files/Pasted%20image%2020240709020308.png)

was bringt ein spline was ein piecewise polynom nicht hat?
?
kontinuitaet sprich die linie hat keine sprungstelle, sommit kann stetigkeit die derivative berechnet werden.


basis function
?
todo


Kontinuitaet
?
![Pasted image 20240705093938.png](/img/user/Files/Pasted%20image%2020240705093938.png)
allgemein: K+d+1 freie Parameter



![Pasted image 20240705094212.png](/img/user/Files/Pasted%20image%2020240705094212.png)

Was sind natruerliche Splines ?
?
![Pasted image 20240705094251.png](/img/user/Files/Pasted%20image%2020240705094251.png)

Nachteil Polynominal Regression
?
![Pasted image 20240705094430.png](/img/user/Files/Pasted%20image%2020240705094430.png)


Kolmogorov-arnod Networks
?
todo



## Treebased Models

Hier sind die wichtigsten Konzepte und Formeln von der angegebenen Webseite im Stil der bisherigen Erklärungen:

### Basics of Decision Trees
> [!Basics of Decision Trees]
> 
> Decision Trees segmentieren den Prädiktorraum in einfache Regionen. Jede Beobachtung wird einer Region zugeordnet, und die Vorhersage erfolgt durch den Mittelwert oder Modus der Trainingsbeobachtungen in dieser Region. 
> 
> **Regression Trees:**
> $$
> \sum_{j=1}^{J} \sum_{i \in R_j} (y_i - \hat{y}_{R_j})^2
> $$
> 
> **Pruning:**
> $$
> \sum_{m=1}^{|T|} \sum_{x_i \in R_m} (y_i - \hat{y}_{R_m})^2 + \alpha |T|
> $$

### Classification Trees
> [!Classification Trees]
> 
> Klassifikationsbäume sagen qualitative Antworten voraus. Die Vorhersage erfolgt durch die am häufigsten vorkommende Klasse im Endknoten. 
> 
> **Gini Index:**
> $$
> G = \sum_{k=1}^{K} \hat{p}_{mk}(1 - \hat{p}_{mk})
> $$
> 
> **Cross-Entropy:**
> $$
> D = - \sum_{k=1}^{K} \hat{p}_{mk} \log(\hat{p}_{mk})
> $$

### Bagging
> [!Bagging]
> 
> Bagging reduziert die Varianz durch das Erstellen vieler Bootstrapped-Trainingsdatensätze, das Bauen mehrerer Bäume und das Mittelwerten der Vorhersagen.
> 
> **Out-of-Bag (OOB) Error:**
> OOB-Beobachtungen werden verwendet, um den Testfehler des Modells zu schätzen.

### Random Forests
> [!Random Forests]
> 
> Random Forests verbessern Bagging durch Dekorrelieren der Bäume. Bei jeder Aufteilung wird eine zufällige Stichprobe von \(m\) Prädiktoren als Aufteilungskandidaten gewählt.
> 
> **Wichtigkeit der Prädiktoren:**
> 
> Wichtige Prädiktoren werden durch die Verringerung des Gini-Index oder der RSS bei Aufteilungen bestimmt.

### Boosting
> [!Boosting]
> 
> Boosting baut viele Bäume sequentiell auf, wobei jeder Baum Informationen aus dem vorhergehenden Baum verwendet.
> 
> **Boosting Algorithmus:**
> $$
> \hat{f}_{new} = \hat{f}_{prev} + \lambda \hat{f}^b
> $$
> 
> $$
> r_{i(new)} = r_{i(prev)} - \lambda \hat{f}^b(x_i)
> $$

Weitere Details und ausführliche Erklärungen finden Sie auf der Webseite [ISLR Chapter 8 - Tree-Based Methods](https://www.bijenpatel.com/guide/islr/tree-based-methods/).

## Support Vektor Machines
Hier sind die wichtigsten Konzepte und Formeln von der angegebenen Webseite im Stil der bisherigen Erklärungen:

### Maximal Margin Classifier
> [!Maximal Margin Classifier]
> 
> Der Maximal Margin Classifier trennt Klassen durch einen Hyperplane mit maximalem Abstand zu den nächsten Datenpunkten beider Klassen.
> 
> $$
> \text{Maximiere } M
> $$
> 
> Betreffend:
> $$
> \sum_{j=1}^{p} \beta_{j}^{2} = 1 \\
> y_{i}(\beta_{0} + \sum_{j=1}^{p} \beta_{j} x_{ij}) \geq M
> $$
> $M$ ist der Abstand vom Hyperplane.

### Support Vector Classifier
> [!Support Vector Classifier]
> 
> Der Support Vector Classifier erlaubt einige Fehler und verbessert Robustheit.
> 
> $$
> \text{Maximiere } M
> $$
> 
> Betreffend:
> $$
> \sum_{j=1}^{p} \beta_{j}^{2} = 1 \\
> y_{i}(\beta_{0} + \sum_{j=1}^{p} \beta_{j} x_{ij}) \geq M(1 - \epsilon_{i}) \\
> \epsilon_{i} \geq 0 \\
> \sum_{i=1}^{n} \epsilon_{i} \leq C
> $$

### Support Vector Machines
> [!Support Vector Machines]
> 
> Support Vector Machines erweitern Support Vector Classifier durch Kernel, die nichtlineare Entscheidungsgrenzen ermöglichen.
> 
> **Kernels:**
> $$
> K(x_i, x_{i'}) = \sum_{j=1}^{p} x_{ij} x_{i'j}
> $$
> 
> **Polynom-Kernel:**
> $$
> K(x_i, x_{i'}) = (1 + \sum_{j=1}^{p} x_{ij} x_{i'j})^{d}
> $$
> 
> **Radial Kernel:**
> $$
> K(x_i, x_{i'}) = \exp(-\gamma \sum_{j=1}^{p} (x_{ij} - x_{i'j})^{2})
> $$

### SVMs with More than Two Classes
> [!SVMs with More than Two Classes]
> 
> **One-Versus-One:**
> Entwickelt mehrere SVMs, die jeweils zwei Klassen vergleichen.
> 
> **One-Versus-All:**
> Entwickelt mehrere SVMs, die jede Klasse gegen alle anderen vergleichen.
> 
> Die Testbeobachtung wird der Klasse zugeordnet, für die der Ausdruck:
> $$
> \beta_{0k} + \beta_{1k} x_{1} + \dots + \beta_{pk} x_{p}
> $$
> am größten ist.

### SVMs vs Logistic Regression
> [!SVMs vs Logistic Regression]
> 
> SVMs und Logistische Regression haben ähnliche Verlustfunktionen und geben oft ähnliche Ergebnisse. Bei gut getrennten Klassen performen SVMs besser, während Logistische Regression bei mehr Überlappung besser abschneidet.

Weitere Details und ausführliche Erklärungen finden Sie auf der Webseite [ISLR Chapter 9 - Support Vector Machines](https://www.bijenpatel.com/guide/islr/support-vector-machines/).


## Unsuppervised Learning

Hier sind die wichtigsten Konzepte und Formeln von der angegebenen Webseite im Stil der bisherigen Erklärungen:

### Principal Components Analysis (PCA)
> [!Principal Components Analysis (PCA)]
> 
> PCA reduziert die Dimensionen eines Datensatzes, indem es neue, unkorrelierte Variablen, die Principal Components, berechnet.
> 
> Erster Principal Component:
> $$
> Z_{1} = \phi_{11}X_{1} + \phi_{21}X_{2} + \cdots + \phi_{p1}X_{p}
> $$
> Die $\phi$-Werte sind die Ladefaktoren, welche die Richtung der maximalen Varianz definieren.

### K-Means Clustering
> [!K-Means Clustering]
> 
> K-Means Clustering teilt den Datensatz in \(K\) Cluster auf, sodass die Summe der quadratischen Abweichungen innerhalb der Cluster minimiert wird.
> 
> **Algorithmus:**
> 1. Zufällige Zuweisung von Beobachtungen zu Clustern.
> 2. Berechnung der Cluster-Zentroiden.
> 3. Neuzuordnung der Beobachtungen basierend auf der Nähe zu den Zentroiden.
> 4. Wiederholung bis zur Konvergenz.

### Hierarchical Clustering
> [!Hierarchical Clustering]
> 
> Hierarchical Clustering erzeugt eine hierarchische Darstellung der Daten in Form eines Dendrogramms.
> 
> **Algorithmus:**
> 1. Berechnung der Distanzen zwischen allen Beobachtungen.
> 2. Fusion der ähnlichsten Cluster.
> 3. Wiederholung bis alle Beobachtungen in einem Cluster sind.
> 
> **Linkage-Methoden:**
> - **Complete Linkage:** Maximale Distanz zwischen den Beobachtungen in zwei Clustern.
> - **Single Linkage:** Minimale Distanz.
> - **Average Linkage:** Durchschnittliche Distanz.
> - **Centroid Linkage:** Distanz zwischen den Zentroiden der Cluster.

### Practical Issues in Clustering
> [!Practical Issues in Clustering]
> 
> Entscheidungen wie die Standardisierung von Variablen und die Wahl der Distanz- und Linkage-Methode beeinflussen die Ergebnisse.
> 
> Validierung ist schwierig, und die Ergebnisse sollten als Ausgangspunkt für Hypothesen und weitere Untersuchungen betrachtet werden.

Weitere Details und ausführliche Erklärungen finden Sie auf der Webseite [ISLR Chapter 10 - Unsupervised Learning](https://www.bijenpatel.com/guide/islr/unsupervised-learning/).






## Week 13 (S. 301-307)
Smoothing Splines
?
$$
\sum_{i=1}^n (y_i - g(x_i))^2 + \lambda \int \left(g''(t)\right)^2 dt
$$
![Pasted image 20240705095306.png](/img/user/Files/Pasted%20image%2020240705095306.png)


Loss function von Smoothing Splines
?
todo


Freiheitsgrade von Smoothing Splines
?
todo


Unterschied von Regression Splines und Smoothing Splines
?
todo



Was ist das Setting der Linearen Regression?
?
![Pasted image 20240705100128.png](/img/user/Files/Pasted%20image%2020240705100128.png)]]


Freiheitsgrade Splines
?
![Pasted image 20240705101536.png](/img/user/Files/Pasted%20image%2020240705101536.png)


### Week 14 (S. 307-311)


## Question Answering
### LE 1: Theoretische Grundlagen des STL

#### 1. Was wird im Statistical Learning untersucht?
Statistical Learning untersucht Methoden zur Analyse und Interpretation komplexer Daten. Es umfasst Werkzeuge zur Modellierung der Beziehung zwischen Variablen, sowohl in überwachten (Vorhersage von Outputs basierend auf Inputs) als auch in unüberwachten (Strukturierung und Mustererkennung in Daten ohne explizite Outputs) Kontexten.

#### 2. Fasse deine Erkenntnisse aus diesem Kompetenzmodul auf einer A4-Seite zusammen.
Das Kompetenzmodul vermittelt die Grundlagen des Statistical Learning, einschließlich der Definitionen von überwachten und unüberwachten Lernmethoden, des Bias-Variance-Tradeoffs, und der Unterscheidung zwischen parametrischen und nicht-parametrischen Modellen. Es behandelt wichtige Konzepte wie den reduzierbaren und nicht-reduzierbaren Fehleranteil und stellt verschiedene Modellierungsansätze vor, darunter lineare und nicht-lineare Modelle, sowie Methoden zur Modellbewertung und -auswahl.

#### 3. Was steckt im Fehler $\epsilon$ in $Y = f (X ) + \epsilon$?
Der Fehler $\epsilon$ repräsentiert den irreduziblen Fehler, der durch zufällige Variabilität oder unbekannte Faktoren in den Daten verursacht wird. Er umfasst alle Einflüsse, die nicht durch die Funktion $f(X)$ erklärt werden können.

#### 4. Charakterisiere den reduzierbaren und den nicht-reduzierbaren Anteil von $\epsilon$.
- **Reduzierbarer Anteil:** Der Teil des Fehlers, der durch ein besseres Modell reduziert werden kann. Dieser umfasst den Bias und die Varianz des Modells.
- **Nicht-reduzierbarer Anteil:** Der Fehler, der nicht durch ein Modell reduziert werden kann, da er aus zufälligen Störgrößen und unvorhersehbaren Einflüssen besteht.

#### 5. Was ist der Unterschied zwischen einem parametrischen und einem nicht-parametrischen Modell? Gib Beispiele.
- **Parametrisches Modell:** Diese Modelle nehmen eine spezifische Form für die Funktion $f(X)$ an (z.B. lineare Regression). Sie sind effizient und einfach zu interpretieren, haben aber einen hohen Bias, wenn die Modellannahme falsch ist.
- **Nicht-parametrisches Modell:** Diese Modelle nehmen keine spezifische Form für $f(X)$ an (z.B. KNN, Entscheidungsbäume). Sie sind flexibel und haben einen niedrigen Bias, aber sie können viele Daten benötigen und anfällig für Overfitting sein.

#### 6. Liste die in diesem Kompetenzmodul untersuchten Modelle auf. In welche Untergruppen können sie aufgeteilt werden?
Untersuchte Modelle:
- Lineare Regression
- KNN
- Entscheidungsbäume
- SVM
- Clustering

Untergruppen:
- **Überwachtes Lernen:** Regression (lineare Regression), Klassifikation (KNN, SVM)
- **Unüberwachtes Lernen:** Clustering

#### 7. Welche der eingeführten Modelle können mit qualitativen Prädiktoren umgehen?
Modelle wie die logistische Regression und Entscheidungsbäume können mit qualitativen Prädiktoren umgehen, indem sie diese in Dummy-Variablen umwandeln oder Kategorien direkt in die Analyse einbeziehen.

#### 8. Welche Masse existieren, um die Qualität eines Fits zu bestimmen? Was sind ihre Vor- und Nachteile?
- **Klassifikation:** 
  - **Accuracy:** Einfach zu interpretieren, aber nicht geeignet bei unausgeglichenen Datensätzen.
  - **F1-Score:** Berücksichtigt sowohl Präzision als auch Recall, besser bei unausgeglichenen Datensätzen.
- **Regression:**
  - **MSE (Mean Squared Error):** Einfach zu interpretieren, empfindlich gegenüber Ausreißern.
  - **R^2:** Gibt den Anteil der Varianz an, der durch das Modell erklärt wird, kann jedoch bei komplexen Modellen irreführend sein.

#### 9. Erkläre den Bias-Variance Trade-Off an einem Training und Validierungsset.
Ein Modell mit hoher Kapazität (Komplexität) hat niedrigen Bias, aber hohe Varianz, was zu Overfitting führen kann. Ein einfaches Modell hat hohen Bias, aber niedrige Varianz, was zu Underfitting führt. Die richtige Modellkapazität minimiert den Gesamtfehler und berücksichtigt sowohl Bias als auch Varianz.

#### 10. Was ist der Bayes Classifier? Warum ist KNN eine Annäherung des Bayes Classifiers?
Der Bayes Classifier weist jeder Beobachtung die Klasse mit der höchsten posterioren Wahrscheinlichkeit zu. KNN approximiert dies, indem es die Mehrheit der Klassen in den K nächsten Nachbarn verwendet.

#### 11. Erkläre den Bias-Variance-Tradeoff am Beispiel von KNN oder eines Regression Splines.
- **KNN:** Bei kleinem $K$ hat das Modell niedrigen Bias, aber hohe Varianz. Bei großem $K$ steigt der Bias, die Varianz sinkt.
- **Regression Splines:** Mit vielen Knotenpunkten (Flexibilität) hat das Modell niedrigen Bias, aber hohe Varianz. Wenige Knotenpunkte führen zu hohem Bias, aber niedriger Varianz.

#### 12. Erkläre, wie die Natur der Daten die Kurven im Bias-Variance-Tradeoff beeinflusst.
Wenn Daten komplex und variabel sind, benötigen Modelle mit höherer Kapazität, um Muster zu erfassen, was die Varianz erhöht. Einfache Daten können durch Modelle mit niedriger Kapazität gut beschrieben werden, was den Bias reduziert.

#### 13. Was ist das ‘No free lunch’-Theorem des Statistical Learning?
Das 'No free lunch'-Theorem besagt, dass kein Modell in allen Situationen überlegen ist. Die Modellleistung hängt von der Datenstruktur und dem spezifischen Anwendungsfall ab.

#### 14. Welche Modelle kennst du, die keine Regressionsmodelle sind?
- Klassifikationsmodelle: KNN, logistische Regression, SVM.
- Clustering-Methoden: K-Means, Hierarchical Clustering.

#### 15. Was ist ein memory-basiertes Modell? Nenne Beispiele.
Memory-basierte Modelle speichern Trainingsdaten und verwenden sie zur Vorhersage neuer Daten. Beispiele sind KNN und Kernel-SVMs.

#### 16. Was ist der Accuracy vs. Interpretability-Tradeoff? Warum ist Interpretierbarkeit wichtig, bzw. oft wichtiger als eine hohe Vorhersagegenauigkeit?
Ein hochgenaues Modell kann komplex und schwer interpretierbar sein, während ein einfaches Modell leichter zu verstehen ist. Interpretierbarkeit ist wichtig, um Modelle in praktischen Anwendungen zu erklären und Vertrauen zu schaffen.
### LE 2: Lineare Regression

#### 1. Was sind Residuen und welcher Verteilungsannahme müssen sie im Setting der linearen Regression folgen?
Residuen sind die Differenzen zwischen den beobachteten Werten und den durch das Modell vorhergesagten Werten. Im Setting der linearen Regression wird angenommen, dass die Residuen normalverteilt sind mit einem Mittelwert von null und konstanter Varianz (Homoskedastizität).

#### 2. Warum sind der Residual Standard Error (RSE) und der Root-Mean-Squared Error (RMSE) im asymptotischen Limit der Anzahl Beobachtungen gleich groß?
Im asymptotischen Limit, wenn die Anzahl der Beobachtungen groß ist, konvergiert der RSE gegen den RMSE, da beide Maßzahlen im Wesentlichen die durchschnittliche Größe der Residuen messen. Der Unterschied besteht in der Freiheitsgrade-Korrektur beim RSE, die bei großer Stichprobe vernachlässigbar wird.

#### 3. Was ist der Wertebereich der \( R^2 \)-Statistik? Was ist passiert, wenn die \( R^2 \)-Statistik negativ ist?
Der Wertebereich der \( R^2 \)-Statistik liegt zwischen 0 und 1. Eine negative \( R^2 \)-Statistik deutet darauf hin, dass das Modell schlechter abschneidet als ein einfaches Mittelwertsmodell, was bei schlecht angepassten Modellen auftreten kann.

#### 4. Was sind die Vor- und Nachteile von linearer Regression gegenüber KNN?
- **Interpretierbarkeit:** Lineare Regression ist einfacher zu interpretieren als KNN.
- **Kapazität:** Lineare Regression hat eine geringe Kapazität und neigt zu Underfitting, während KNN eine hohe Kapazität hat und zu Overfitting neigen kann.
- **Effizienz:** Lineare Regression ist rechnerisch effizienter als KNN, insbesondere bei großen Datensätzen.
- **Datenmenge:** KNN benötigt mehr Daten, um genaue Vorhersagen zu treffen, während die lineare Regression auch mit weniger Daten gut funktioniert.

#### 5. Für die lineare Regression lassen sich Standardabweichungen auf die geschätzten Koeffizienten bestimmen. Wie könntest du diese Standardabweichungen auch ohne Formel schätzen?
Die Standardabweichungen der geschätzten Koeffizienten können durch Bootstrap-Methoden geschätzt werden, bei denen wiederholt Stichproben mit Zurücklegen aus dem Datensatz gezogen und die Modellparameter neu geschätzt werden.

#### 6. Was ist der t-Test und welche Rolle spielt er in der linearen Regression? Wo führt er zu Problemen?
Der t-Test wird verwendet, um zu testen, ob ein Regressionskoeffizient signifikant von null verschieden ist. Er prüft die Nullhypothese, dass der Koeffizient keinen Einfluss hat. Probleme treten auf, wenn die Annahmen der Normalverteilung und Homoskedastizität der Residuen verletzt sind.

#### 7. Schreibe das Setting der Multiplen Linearen Regression in Vektor- und Matrixform auf.
In Vektor- und Matrixform wird die multiple lineare Regression wie folgt dargestellt:
$$
\mathbf{Y} = \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\epsilon}
$$
wobei $\mathbf{Y}$ der Vektor der abhängigen Variablen, $\mathbf{X}$ die Designmatrix der unabhängigen Variablen, $\boldsymbol{\beta}$ der Vektor der Koeffizienten und $\boldsymbol{\epsilon}$ der Fehlerterm ist.

#### 8. Was ist die Motivation, für das Fitten der Regressionsparameter Least Squares zu benutzen? Warum nicht zum Beispiel einen Mean Absolute Error (MAE, L1-Distanz zwischen Vorhersage und tatsächlichen Werten)?
Least Squares (Kleinste Quadrate) minimiert die Summe der quadrierten Residuen und führt zu einfacheren mathematischen Lösungen und Optimierung. Mean Absolute Error (MAE) hat den Vorteil, robust gegenüber Ausreißern zu sein, aber es führt zu komplexeren Optimierungsproblemen, da es nicht differenzierbar ist.

#### 9. Wie ist die F-Statistik im Setting der Multiplen Linearen Regression zu interpretieren?
Die F-Statistik testet die Nullhypothese, dass alle Regressionskoeffizienten außer dem Interzept gleich null sind. Eine signifikant hohe F-Statistik deutet darauf hin, dass das Modell mit den Prädiktoren besser ist als ein Modell ohne Prädiktoren.

#### 10. Wie können im linearen Regressionssetting qualitative Variablen berücksichtigt werden? Wie sind die Modellparameter zu interpretieren?
Qualitative Variablen können durch Dummy-Variablen kodiert werden. Modellparameter repräsentieren dann die Veränderung der abhängigen Variablen im Vergleich zur Referenzkategorie.

#### 11. Was ist Multikollinearität? Warum ist sie in der linearen Regression ein Problem? Wie kannst du herausfinden, ob drei oder mehr Variablen eine multikollineare Beziehung haben?
Multikollinearität tritt auf, wenn zwei oder mehr Prädiktoren stark korreliert sind, was die Schätzung der Koeffizienten ungenau macht. Sie kann durch Variance Inflation Factor (VIF) und Korrelationsmatrizen untersucht werden.

#### 12. Was ist ein additives Modell? Warum ist die einfache lineare Regression additiv? Was sind die Einschränkungen eines additiven Modells? Wie kannst du diese zum Teil umgehen? Was ist das hierarchische Prinzip zum Umgang mit Interaktionsvariablen? Was sind Haupteffekte? Warum ist polynomiale Regression immer noch ein lineares Modell?
Additive Modelle kombinieren die Effekte der Prädiktoren additiv. Lineare Regression ist additiv, da sie die Summe der Prädiktor-Effekte modelliert. Einschränkungen bestehen in der Unfähigkeit, komplexe Interaktionen zu modellieren, die durch Interaktionsterme und hierarchisches Modellieren teilweise umgangen werden können. Haupteffekte sind die Einzelwirkungen der Prädiktoren. Polynomiale Regression ist linear in den Koeffizienten, daher ein lineares Modell.

#### 13. Was ist Heteroskedastizität? Wie steht sie zu den Modellannahmen der linearen Regression? Mit welchen Methoden kannst du wieder in ein homoskedastisches Setting zurückkommen?
Heteroskedastizität bedeutet, dass die Varianz der Residuen nicht konstant ist. Dies verletzt die Annahmen der linearen Regression. Methoden wie logarithmische Transformationen oder gewichtete Regression können helfen, Homoskedastizität zu erreichen.

#### 14. Welche Arten von Ausreißern gibt es? Welche Art von Ausreißern beeinflusst ein lineares Regressionsmodell besonders? Mit welchem Mass kannst Ausreisser dieser Art finden?
Es gibt Ausreißer in den Prädiktoren und in den abhängigen Variablen. Leverage-Punkte (Ausreißer in den Prädiktoren) beeinflussen das Modell besonders stark. Cook’s Distance misst den Einfluss einzelner Beobachtungen auf das Modell.

#### 15. Was ist die Maximum-Likelihood-Methode und wie kann sie im Fall der linearen und logistischen Regression benutzt werden, um das optimale Modell zu finden? Warum ist Least Squares eine Konsequenz daraus?
Die Maximum-Likelihood-Methode schätzt Parameter, die die beobachteten Daten am wahrscheinlichsten machen. In der linearen Regression führt dies zu den gleichen Ergebnissen wie Least Squares, da die Normalverteilungsannahmen der Fehler konsistent sind. In der logistischen Regression wird die Wahrscheinlichkeit der Klassenzugehörigkeit maximiert.
### LE 3: Klassifikationsprobleme

#### 1. Welche Grössen zur Beurteilung der Performance eines Klassifikationsmodells kennst du? Wie können sie auf ein Setting mit mehr als nur zwei Klassen erweitert werden? Wie beeinflusst Class Imbalance diese Grössen? Erkläre die ROC-Kurve und warum sie benutzt wird.
Performance-Messgrößen:
- **Accuracy:** Anteil der korrekt klassifizierten Beispiele.
- **Precision:** Anteil der korrekt positiv klassifizierten Beispiele.
- **Recall (Sensitivity):** Anteil der tatsächlich positiven Beispiele, die korrekt erkannt wurden.
- **F1-Score:** Harmonisches Mittel von Precision und Recall.
- **ROC-Kurve (Receiver Operating Characteristic):** Zeigt die True Positive Rate gegen die False Positive Rate für verschiedene Schwellenwerte. Der AUC (Area Under Curve) Wert gibt die Güte des Modells an.
  
Class Imbalance:
- Bei unausgeglichenen Datensätzen kann Accuracy irreführend sein. Precision, Recall und der F1-Score sind besser geeignet, um die Performance zu bewerten.

Multiclass Settings:
- **Macro-Averaging:** Berechnet die Metriken für jede Klasse und mittelt sie.
- **Micro-Averaging:** Aggregiert die Beiträge aller Klassen zur Metrik.

#### 2. Was ist die Rolle der Sigmoid-Funktion in der logistischen Regression? Warum kann für diskrete Zielgrössen nicht einfach ein lineares Regressionsmodell verwendet werden?
Die Sigmoid-Funktion transformiert den linearen Output in einen Wert zwischen 0 und 1, der als Wahrscheinlichkeit interpretiert werden kann:
$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$
Ein lineares Regressionsmodell ist nicht geeignet für diskrete Zielgrößen, da es keine Wahrscheinlichkeiten ausgibt und die Fehlerverteilung nicht normal ist.

#### 3. Wie sind die gefundenen Koeffizienten der logistischen Regression zu interpretieren?
Die Koeffizienten der logistischen Regression (\(\beta\)) geben an, wie sich die Log-Odds des Zielereignisses ändern, wenn sich der Prädiktor um eine Einheit ändert. Die Exponentialfunktion der Koeffizienten (\(e^{\beta}\)) gibt das Odds Ratio an.

#### 4. Was ist der Unterschied zwischen Multipler und Multinomialer Regression? Erkläre beide Settings mit Formeln. Können sie kombiniert werden?
- **Multiple Regression:** Nutzt mehrere Prädiktoren zur Vorhersage einer kontinuierlichen Antwort:
  $$
  Y = \beta_0 + \beta_1X_1 + \beta_2X_2 + \cdots + \beta_pX_p + \epsilon
  $$
- **Multinomiale Regression:** Verwendet mehrere Prädiktoren zur Vorhersage einer kategorialen Antwort mit mehr als zwei Klassen:
  $$
  \log \left(\frac{P(Y=k)}{P(Y=K)}\right) = \beta_{0k} + \beta_{1k}X_1 + \beta_{2k}X_2 + \cdots + \beta_{pk}X_p
  $$

Kombination: Ja, sie können kombiniert werden, um kategoriale Vorhersagen mit multiplen Prädiktoren zu treffen.

#### 5. Was ist ein generatives Modell? Warum sind LDA, QDA und Naive Bayes generative Modelle? Was ist der Vorteil eines generativen Modells im Vergleich zu KNN oder logistischer Regression? Was sind Nachteile?
Generative Modelle modellieren die gemeinsame Verteilung der Prädiktoren und der Antwortvariable \(P(X, Y)\). LDA, QDA und Naive Bayes sind generative Modelle, weil sie die Verteilung \(P(X|Y)\) und \(P(Y)\) modellieren und dann Bayes' Theorem anwenden.

Vorteile:
- Besser bei kleinen Datenmengen.
- Kann fehlende Datenpunkte besser behandeln.

Nachteile:
- Annahmen über die Verteilung der Daten können ungenau sein.
- Komplexität und Rechenaufwand können hoch sein.

#### 6. Was sind die Modellannahmen von LDA? Wie werden Klassifikationsentscheidungen getroffen? Woher kommt der Name 'Diskriminantenanalyse'? In welchem Punkt unterscheidet sich QDA zu LDA bezüglich Modellannahmen? In welchem Punkt Naive Bayes? Welches Modell ist das beste?
- **Modellannahmen von LDA:**
  - Normalverteilte Prädiktoren in jeder Klasse.
  - Gleiche Kovarianzmatrix für alle Klassen.
- **Klassifikationsentscheidungen:** Basieren auf der Maximierung der posterioren Wahrscheinlichkeit.
- **Diskriminantenanalyse:** Kommt von der Nutzung von Diskriminanzfunktionen zur Unterscheidung der Klassen.
- **QDA:** Erlaubt unterschiedliche Kovarianzmatrizen für jede Klasse.
- **Naive Bayes:** Geht von Unabhängigkeit der Prädiktoren aus.

Das beste Modell hängt vom Datensatz und den Annahmen ab. LDA ist effizient bei großen, gut getrennten Klassen, während KNN flexibel ist, aber viel Rechenaufwand erfordert.

#### 7. LDA und Logistische Regression sind beides lineare Modelle. Warum klassifizieren sie gleiche Datensätze trotzdem mit unterschiedlichen Hyperebenen?
LDA maximiert die Trennung zwischen Klassen basierend auf den Klassenverteilungen, während logistische Regression die Wahrscheinlichkeiten für die Klassen direkt modelliert. Dies führt zu unterschiedlichen Klassifikationsgrenzen.

#### 8. Warum ist ein Naive Bayes-Modell mit allgemeiner grundlegender Verteilung flexibler als ein QDA-Modell? Warum ist ein Naive Bayes-Modell mit Normalverteilung weniger flexibel als ein LDA-Modell?
- **Naive Bayes mit allgemeiner Verteilung:** Kann jede Verteilung annehmen und ist daher flexibler.
- **Naive Bayes mit Normalverteilung:** Macht stärkere Annahmen über die Form der Verteilung, was es weniger flexibel macht als LDA, das nur gleiche Kovarianzmatrizen voraussetzt.

#### 9. Welches ist das beste Klassifikationsmodell? Warum kann keine einfache Aussage diesbezüglich gemacht werden? In welchem Setting ist LDA das beste Klassifikationsmodell? In welchem KNN? Welche anderen Kriterien für die Brauchbarkeit eines Modells außer dessen Vorhersagbarkeit kennst du noch?
Es gibt kein bestes Modell für alle Situationen. Die Wahl hängt von der Datenstruktur, der Anzahl der Beobachtungen und der Verteilungsannahmen ab.

- **LDA:** Best bei großen, gut getrennten Klassen mit gleichen Kovarianzmatrizen.
- **KNN:** Best bei komplexen, nichtlinearen Entscheidungsgrenzen.

Andere Kriterien:
- Interpretierbarkeit.
- Rechenaufwand.
- Robustheit gegenüber Ausreißern.

#### 10. Warum konvergiert logistische Regression nur schlecht, wenn die Daten perfekt separiert sind?
Bei perfekter Trennung streben die Koeffizienten gegen Unendlichkeit, da das Modell versucht, die Trennung zu maximieren. Dies führt zu Problemen in der Konvergenz der Optimierung.

#### 11. Warum ist die logistische Regression von starken Korrelationen betroffen, warum LDA und QDA nicht? Wie sieht es mit Naive Bayes und KNN aus?
Logistische Regression kann bei stark korrelierten Prädiktoren instabile Koeffizienten haben. LDA und QDA berücksichtigen die gemeinsame Verteilung und Kovarianzmatrix, was sie stabiler macht. Naive Bayes geht von unabhängigen Prädiktoren aus, daher problematisch bei Korrelationen. KNN ist weniger betroffen, da es auf Distanzen basiert.

#### 12. Warum funktioniert die Accuracy nur schlecht als Performance-Mass, wenn eine große Imbalance in der Klassenverteilung vorliegt?
Accuracy kann irreführend sein, wenn eine Klasse stark dominiert. In diesem Fall kann ein Modell hohe Accuracy erzielen, indem es die dominierende Klasse bevorzugt, während die Leistung auf der Minderheitsklasse schlecht ist. Bessere Metriken sind Precision, Recall und der F1-Score.

### LE 4: Generalisierte Lineare Modelle

#### 1. Punkto welcher Tatsache generalisieren GLMs eigentlich? Was sind die Annahmen der linearen Regression, die möglicherweise nicht immer erfüllt sind?
GLMs generalisieren die lineare Regression, indem sie den linearen Zusammenhang zwischen den Prädiktoren und dem Erwartungswert der Antwortvariable beibehalten, aber eine breitere Palette von Verteilungen für die Antwortvariable zulassen. Annahmen der linearen Regression, die nicht immer erfüllt sind:
- Normalverteilung der Fehler
- Homoskedastizität der Fehler
- Linearität der Beziehung zwischen Prädiktoren und Antwortvariable

#### 2. Schreibe explizit die Form eines GLM auf und beschreibe insbesondere die Rolle der Link-Funktion und den Zusammenhang zum Erwartungswert. Welche Beispiele für GLMs kennst du und welche Link-Funktionen gehören dazu?
Ein GLM hat die Form:
$$
g(\mathbb{E}(Y|X)) = \beta_0 + \beta_1X_1 + \cdots + \beta_pX_p
$$
Die Link-Funktion \( g \) stellt eine Beziehung zwischen dem Erwartungswert \( \mathbb{E}(Y|X) \) und der linearen Kombination der Prädiktoren her.

Beispiele für GLMs und ihre Link-Funktionen:
- **Logistische Regression:** Logit-Link \( g(\mu) = \log\left(\frac{\mu}{1-\mu}\right) \)
- **Poisson-Regression:** Log-Link \( g(\mu) = \log(\mu) \)
- **Gamma-Regression:** Inverse-Link \( g(\mu) = \frac{1}{\mu} \)

#### 3. Was sind Beispiele für poissonverteilte Zielgrössen? Wie sind die Koeffizienten einer Poisson-Regression zu interpretieren? Warum hat die Link-Funktion für eine Poisson-Regression diese spezifische Form?
Beispiele für poissonverteilte Zielgrößen sind die Anzahl der Anrufe in einem Callcenter pro Stunde oder die Anzahl der Unfälle an einem bestimmten Ort pro Jahr. Die Koeffizienten einer Poisson-Regression werden als die Änderung der Log-Zählrate pro Einheit Änderung des Prädiktors interpretiert. Die Log-Link-Funktion wird verwendet, weil sie sicherstellt, dass die vorhergesagte Anzahl nicht negativ ist und die Poisson-Verteilung angemessen modelliert wird.

### LE 5: Resampling

#### 1. Erkläre den Zweck des einfachen Train-Validation-Split, eines k-fold CV-Ansatzes und LOOCV und platziere sie im Bias-Variance-Tradeoff. Welchen Wert für k würdest du im Allgemeinen für eine k-fold CV benutzen?
- **Train-Validation-Split:** Teilt Daten in ein Trainings- und ein Validierungsset auf. Einfach, aber kann hohe Varianz haben.
- **k-fold Cross-Validation (CV):** Teilt Daten in \(k\) gleichgroße Folds, trainiert auf \(k-1\) Folds und validiert auf dem verbleibenden Fold. Besseres Bias-Varianz-Verhältnis.
- **Leave-One-Out Cross-Validation (LOOCV):** Verwendet jede Beobachtung einmal als Validierung und den Rest als Training. Sehr niedriger Bias, aber hohe Varianz.

Empfohlener Wert für \(k\): 10.

#### 2. Warum überschätzt k-fold CV den Fehler auf dem Validierungsset im Allgemeinen?
k-fold CV überschätzt den Validierungsfehler, weil das Modell auf nur \(k-1\) Teilen des Datensatzes trainiert wird und nicht auf dem gesamten Datensatz. Dies führt zu konservativeren Schätzungen des Fehlers.

#### 3. Was ist der Bootstrap und wofür kann er eingesetzt werden? Kennst du ein Anwendungsbeispiel? Kannst du erklären, warum der Bootstrap funktioniert?
Der Bootstrap ist eine Methode zur Schätzung der Verteilung einer Statistik durch wiederholtes Ziehen von Stichproben mit Zurücklegen aus dem Originaldatensatz. Anwendungsbeispiel: Schätzung der Standardabweichung eines Parameters. Der Bootstrap funktioniert, weil jede Bootstrapped-Stichprobe eine repräsentative Unterstichprobe des Originaldatensatzes darstellt, wodurch die Variabilität der Statistik abgeschätzt werden kann.

#### 4. Warum overfittest du umso stärker auf das Validierungsset, je mehr Hyperparameter-Tuning du machst?
Je mehr Hyperparameter-Tuning durchgeführt wird, desto spezifischer wird das Modell an das Validierungsset angepasst, was zu Overfitting führt. Das Modell lernt spezifische Muster und Rauschen im Validierungsset, anstatt generalisierbare Muster zu erkennen.

### LE 6: Model Selection

#### 1. Welche Methoden kennst du um eine Auswahl aus einer Menge von Prädiktoren zu treffen, die in ein Modell eingehen sollen? Welche Techniken helfen dir dabei, diese Auswahl zu treffen und so das Modell zu finden, das vermutlich am besten auf ein Testsetting generalisiert?
Methoden zur Auswahl von Prädiktoren:
- **Best Subset Selection**
- **Forward Stepwise Selection**
- **Backward Stepwise Selection**
- **Shrinkage-Methoden (Ridge, Lasso)**
- **Dimension Reduction Methods (PCA, PLS)**

Techniken zur Auswahl des besten Modells:
- **Cross-Validation (CV)**
- **Information Criteria (AIC, BIC)**
- **Adjusted \(R^2\)**

#### 2. Was sind die Vor- und Nachteile von Best Subset Selection und Forward- und Backward Stepwise Selection? In welchem Setting würdest du welchen Ansatz anwenden?
- **Best Subset Selection:**
  - **Vorteile:** Findet das beste Modell jeder Größe.
  - **Nachteile:** Rechenintensiv bei großen \(p\).
  - **Setting:** Kleine bis mittlere \(p\).
- **Forward Stepwise Selection:**
  - **Vorteile:** Weniger rechenintensiv, schrittweise Prädiktoren hinzufügen.
  - **Nachteile:** Suboptimale Modelle möglich.
  - **Setting:** Große \(p\), wenn Berechnungseffizienz wichtig ist.
- **Backward Stepwise Selection:**
  - **Vorteile:** Beginnt mit allen Prädiktoren, entfernt sukzessiv.
  - **Nachteile:** Funktioniert nicht bei \(n < p\).
  - **Setting:** Große \(p\), aber \(n > p\).

#### 3. Welche Anzahl von Modellen schauen Best Subset Selection und Forward- und Backward Stepwise Selection ungefähr an, wenn eine Menge von \(p\) Prädiktoren vorliegt?
- **Best Subset Selection:** Betrachtet \(2^p\) Modelle.
- **Forward Stepwise Selection:** Betrachtet ungefähr \(\frac{p(p+1)}{2}\) Modelle.
- **Backward Stepwise Selection:** Betrachtet ungefähr \(\frac{p(p+1)}{2}\) Modelle.

#### 4. Was schätzen AIC und BIC ab? Was schätzt adjusted \(R^2\) ab? Welche Überlegung geht in die Berechnung von adjusted \(R^2\) ein?
- **AIC (Akaike Information Criterion):** Schätzt die Qualität eines Modells hinsichtlich des Informationsverlusts:
  $$
  \text{AIC} = 2k - 2\log(L)
  $$
- **BIC (Bayesian Information Criterion):** Schätzt die Qualität eines Modells unter Berücksichtigung der Modellkomplexität:
  $$
  \text{BIC} = k\log(n) - 2\log(L)
  $$
- **Adjusted \(R^2\):** Passt das \(R^2\)-Maß an die Anzahl der Prädiktoren und die Stichprobengröße an:
  $$
  \text{Adjusted } R^2 = 1 - \left( \frac{(1 - R^2)(n - 1)}{n - p - 1} \right)
  $$

#### 5. In welcher Situation kann es mehr Sinn machen, statt einem CV-Ansatz die Größen AIC, BIC oder adjusted \(R^2\) zu benutzen?
In Situationen mit großen Datensätzen oder bei Modellen mit vielen Prädiktoren, wo CV-Ansätze rechnerisch aufwendig sind. Auch wenn schnelle Modellvergleiche nötig sind oder bei Zeitdruck, können AIC, BIC und adjusted \(R^2\) nützlich sein.

#### 6. Was ist ANOVA? Wie wird sie zur Selektion von Modellen eingesetzt?
ANOVA (Analysis of Variance) testet die Unterschiede zwischen Gruppenmittelwerten. In der Modellselektion wird ANOVA verwendet, um zu prüfen, ob das Hinzufügen zusätzlicher Prädiktoren zu einer signifikanten Verbesserung des Modells führt.

#### 7. Was ist die One-Standard-Error-Rule? Erkläre mit einer Grafik. Warum macht sie Sinn?
Die One-Standard-Error-Rule wählt das einfachste Modell, dessen Fehler innerhalb eines Standardfehlers des minimalen Fehlerwerts liegt. Dies reduziert die Varianz und vermeidet Overfitting.

**Grafik:**
```
  Fehler
    ^
    |          *
    |         ***
    |        *****
    |       *******
    |      *********
    |  ******************
    |***********************************
    --------------------------------------------> Modellkomplexität
                         ^
             Einfache Modelle innerhalb eines Standardfehlers des minimalen Fehlers
```
**Sinn:**
Die Regel sorgt für Robustheit und vermeidet Overfitting, indem sie ein einfacheres Modell bevorzugt, das fast so gut ist wie das komplexeste Modell.


### LE 7: Nicht-lineare Regression

#### 1. Welche Ansätze zur nicht-linearen Regression kennst du? Welcher ist der beste?
- **Polynomial Regression**
- **Regression Splines**
- **Smoothing Splines**
- **Natural Splines**
- **Generalized Additive Models (GAMs)**
- **Local Regression**

Es gibt keinen "besten" Ansatz; die Wahl hängt vom spezifischen Anwendungsfall und den Daten ab.

#### 2. Ordne die verschiedenen Ansätze zur nicht-linearen Regression im Bias-Variance-Tradeoff ein - welcher ist der flexibelste?
- **Höchster Bias, geringste Varianz:** Polynomial Regression (niedriger Grad)
- **Mittlerer Bias, mittlere Varianz:** Regression Splines, Natural Splines
- **Niedriger Bias, hohe Varianz:** Smoothing Splines, GAMs, Local Regression (höchste Flexibilität)

#### 3. Was sind Unterschiede zwischen einem polynomialen Regressionsmodell und einem Regression Spline?
- **Polynomiale Regression:** Nutzt eine einzige globale polynomiale Funktion für das gesamte Datenintervall.
- **Regression Splines:** Teilt das Datenintervall in mehrere Stücke und passt für jedes Stück ein Polynom an. Die Stücke sind an den Knotenpunkten verbunden und sorgen für mehr Flexibilität.

#### 4. Worin unterscheiden sich natürliche Splines zu Regression Splines?
- **Natürliche Splines:** Eine spezielle Art von Regression Splines, die zusätzlich die Bedingung erfüllen, dass die zweite Ableitung an den Endpunkten null ist, was zu glatteren Kurven führt.
- **Regression Splines:** Allgemeinerer Ansatz ohne diese zusätzliche Bedingung.

#### 5. Was ist eine Basisfunktion und wie wird sie in Regression Spline-Modellen angewendet?
Eine Basisfunktion ist eine grundlegende Funktion, die verwendet wird, um komplexere Funktionen zu konstruieren. In Regression Spline-Modellen werden Basisfunktionen verwendet, um die Polynomstücke in jedem Intervall darzustellen und zu kombinieren.

#### 6. Mit welchem Parameter wird die Position eines Smoothing-Splines im Bias-Variance-Tradeoff eingestellt? Was reguliert er? Wie könntest du einen optimalen Wert für diesen Parameter bestimmen?
- **Parameter:** Glättungsparameter \(\lambda\).
- **Regulierung:** \(\lambda\) steuert das Gewicht der Glättung gegenüber der Anpassung an die Daten.
- **Bestimmung:** Der optimale Wert kann durch Kreuzvalidierung ermittelt werden.

#### 7. Wie ist der Begriff ‘Freiheitsgrad’ (Degree of freedom) für Spline-Modelle zu verstehen? Was ist insbesondere der Zusammenhang der effektiven Anzahl Freiheitsgrade eines Regressionsmodells zur Spur der Projektionsmatrix, die die tatsächlichen y-Werte auf die Regressionskurve projiziert?
- **Freiheitsgrad:** Anzahl der unabhängigen Parameter im Modell.
- **Zusammenhang:** Die effektiven Freiheitsgrade eines Modells entsprechen der Spur der Projektionsmatrix, die die beobachteten Werte auf die geschätzten Werte projiziert.

#### 8. Was ist die Truncated Power Basis und warum ist sie eine gute Basis für Regression Splines?
Die Truncated Power Basis besteht aus Basisfunktionen, die an den Knotenpunkten "abgeschnitten" werden. Sie ist eine gute Basis für Regression Splines, weil sie einfach zu konstruieren ist und gute numerische Eigenschaften aufweist.

#### 9. Welche Ordnung der Basispolynome eines Regression-Splines würdest du standardmäßig benutzen? Bis zu welcher Ableitung muss er die Randbedingungen in den Knotenpunkten erfüllen?
Standardmäßig wird oft ein kubisches Polynom verwendet, das bis zur zweiten Ableitung stetig ist.

#### 10. Wie funktioniert Lokale Regression? Mit welchem Parameter wird ihre Position im Bias-Variance-Tradeoff, also ihre Flexibilität eingestellt? Warum ist sie memory-basiert?
- **Lokale Regression:** Passt ein Modell in einem kleinen Bereich der Daten um jeden Punkt an.
- **Parameter:** Bandbreite oder Fenstergröße \(\alpha\).
- **Memory-basiert:** Speichert alle Datenpunkte und passt das Modell lokal an.

#### 11. Was wird in einem GAM an der linearen Regression verallgemeinert, was nicht? Wie könntest du diese verbleibende Schwäche dennoch ein wenig mildern?
- **Generalisierung:** Nichtlineare Beziehungen zwischen Prädiktoren und Antwortvariable.
- **Nicht generalisiert:** Additive Struktur.
- **Schwäche mildern:** Interaktionsterme einführen.

#### 12. Wie werden GAMs trainiert?
GAMs werden durch iteratives Glätten und Optimieren der nichtlinearen Funktionen jedes Prädiktors trainiert, häufig unter Verwendung von Backfitting.

#### 13. Kombiniere die für GAMs und GLMs gemachten Verallgemeinerungen und schreibe die Formeln für dieses ‘GLAM’ auf.
Ein GLAM (Generalized Linear Additive Model) kombiniert die additiven nichtlinearen Funktionen von GAMs mit den flexiblen Verteilungsannahmen und Link-Funktionen von GLMs:
$$
g(\mathbb{E}(Y|X)) = \beta_0 + f_1(X_1) + f_2(X_2) + \cdots + f_p(X_p)
$$
wobei \( g \) die Link-Funktion ist und \( f_i \) nichtlineare Funktionen der Prädiktoren sind.




### Mathematische Räume im Statistischen Lernen
Was sind mathematische raueme und wie kann man sie verwenden bei machine learning?
?
> [!Mathematische Räume im Statistischen Lernen]
>
> **Feature Raum:**
> - **Definition:** Der Feature-Raum ist der Raum, der von den Merkmalen oder Prädiktoren einer Analyse aufgespannt wird.
> - **Beispiel:** Ein $p$-dimensionaler Raum $X = (X_1, X_2, \ldots, X_p)$, in dem jede Dimension ein Merkmal darstellt.
> - **Verwendete Modelle:** Alle Machine Learning Modelle (z.B. lineare Regression, Entscheidungsbäume)
> 
> **Metrischer Raum:**
> - **Definition:** Ein Raum mit einer Distanzfunktion, die den Abstand zwischen zwei Punkten misst.
> - **Eigenschaften:** 
>   - Nichtnegativität: $d(x, y) \geq 0$
>   - Identität: $d(x, y) = 0$ wenn $x = y$
>   - Symmetrie: $d(x, y) = d(y, x)$
>   - Dreiecksungleichung: $d(x, z) \leq d(x, y) + d(y, z)$
> - **Verwendete Modelle:** K-Nearest Neighbors, k-Means, hierarchisches Clustering
> 
> **Vektorraum:**
> - **Definition:** Ein Raum, in dem Vektoren addiert und skaliert werden können.
> - **Eigenschaften:**
>   - Abgeschlossenheit unter Addition und Skalierung
>   - Existenz eines Nullvektors und eines inversen Elements für jede Operation
>   - Assoziativität und Kommutativität der Addition
>   - Distributivität der Skalierung über Vektoraddition und Skalaren
> - **Verwendete Modelle:** Lineare Regression, Hauptkomponentenanalyse (PCA)
> 
> **Hilbertraum:**
> - **Definition:** Ein vollständiger innerer Produkt-Raum, wichtig für Methoden wie Kernel-Methoden und Support Vector Machines.
> - **Eigenschaften:**
>   - Inneres Produkt: $\langle x, y \rangle$ definiert
>   - Norm: $\|x\| = \sqrt{\langle x, x \rangle}$
>   - Vollständigkeit: Jede Cauchy-Folge konvergiert
> - **Verwendete Modelle:** Support Vector Machines, Kernel PCA
> 
> **Mannigfaltigkeit:**
> - **Definition:** Räume, die lokal wie ein euklidischer Raum aussehen, nützlich für nichtlineare Methoden wie t-SNE oder Isomap.
> - **Eigenschaften:**
>   - Lokale Ähnlichkeit zum $\mathbb{R}^n$
>   - Glatte Übergangsfunktionen
>   - Topologische Struktur
> - **Verwendete Modelle:** t-SNE, Isomap, LLE (Locally Linear Embedding)
> 
> **Wahrscheinlichkeitsraum:**
> - **Definition:** Ein Raum, in dem Zufallsvariablen definiert sind, grundlegend für probabilistische Modelle und maschinelles Lernen.
> - **Eigenschaften:**
>   - Ereignismenge $\mathcal{F}$
>   - Wahrscheinlichkeitsmaß $P$
>   - Ergebnisraum $\Omega$
> - **Verwendete Modelle:** Naive Bayes, Hidden Markov Models (HMMs), Bayesian Networks


### Normalisierung und Standardisierung im Machine Learning
Wo muss man Normalisieren und Standardiseren?
?
> [!Normalisierung und Standardisierung im Machine Learning]
> 
> **Normalisierung:**
> - **Definition:** Skalierung der Daten auf einen Bereich von 0 bis 1.
> - **Verwendete Modelle:**
>   - K-Nearest Neighbors (KNN)
>   - k-Means
>   - Neural Networks
> - **Begründung:** Diese Modelle verwenden Distanzmetriken im metrischen Raum, und unterschiedliche Skalen der Features können die Distanzen verzerren.
> 
> **Standardisierung:**
> - **Definition:** Skalierung der Daten, so dass sie einen Mittelwert von 0 und eine Standardabweichung von 1 haben.
> - **Verwendete Modelle:**
>   - Lineare Regression
>   - Logistic Regression
>   - Support Vector Machines (SVM)
>   - Principal Component Analysis (PCA)
>   - Lineare Diskriminanzanalyse (LDA)
>   - Quadratische Diskriminanzanalyse (QDA)
> - **Begründung:** Diese Modelle setzen voraus, dass die Features normalverteilt sind und ähnliche Skalen haben, um die Koeffizienten korrekt zu interpretieren und numerische Stabilität zu gewährleisten.
> 
> **Modelle, bei denen Normalisierung oder Standardisierung nicht notwendig ist:**
> - **Verwendete Modelle:**
>   - Entscheidungsbäume
>   - Random Forests
>   - Gradient Boosting Trees
> - **Begründung:** Diese Modelle sind baumbasiert und teilen die Daten an Schnittpunkten, die nicht von der Skalierung der Features beeinflusst werden.


![Pasted image 20240709153955.png](/img/user/Files/Pasted%20image%2020240709153955.png)



todo learn:

### Wichtige Basisfunktionen in der Regressionsanalyse
> [!Wichtige Basisfunktionen in der Regressionsanalyse]
>
> **1. Polynomieller Basis:**
> $$
> 1, x, x^2, x^3, \ldots, x^n
> $$
> - $x$: Prädiktor
> - $n$: Grad des Polynoms
> 
> **2. Stückweise Lineare Basisfunktionen (Piecewise Linear):**
> $$
> 1, x, (x - \xi_1)_+, (x - \xi_2)_+, \ldots, (x - \xi_m)_+
> $$
> - $x$: Prädiktor
> - $\xi_k$: Knotenpunkt
> 
> **3. Stückweise Kubische Splines:**
> $$
> 1, x, x^2, x^3, (x - \xi_1)_+^3, (x - \xi_2)_+^3, \ldots, (x - \xi_m)_+^3
> $$
> - $x$: Prädiktor
> - $\xi_k$: Knotenpunkt
> 
> **4. B-Splines:**
> $$
> B_{i, 3}(x) \quad \text{für} \quad i = 1, 2, \ldots, m+2
> $$
> - $x$: Prädiktor
> - $B_{i, 3}(x)$: Kubische B-Spline-Basisfunktion
> 
> **5. Fourier-Basis:**
> $$
> 1, \sin(x), \cos(x), \sin(2x), \cos(2x), \ldots, \sin(nx), \cos(nx)
> $$
> - $x$: Prädiktor
> - $n$: Maximaler Frequenzindex
> 
> **6. Radial Basisfunktionen (RBF):**
> $$
> \phi_i(x) = \exp\left(-\frac{(x - c_i)^2}{2\sigma^2}\right) \quad \text{für} \quad i = 1, 2, \ldots, m
> $$
> - $x$: Prädiktor
> - $c_i$: Zentrum der RBF
> - $\sigma$: Breitenparameter
> 
> **7. Indicator-Basisfunktionen für Kategorische Variablen:**
> $$
> I(x = \text{Kategorie}_1), I(x = \text{Kategorie}_2), \ldots, I(x = \text{Kategorie}_k)
> $$
> - $x$: Kategorischer Prädiktor
> - $k$: Anzahl der Kategorien
> - 
> **Zusammenfassung:**
> - **Polynomiell:** Einfach und gut für glatte, nichtlineare Beziehungen.
> - **Stückweise linear/kubisch:** Flexibel, gut für Daten mit diskontinuierlichen oder nicht-glatten Strukturen.
> - **B-Splines:** Kompakte Unterstützung, flexibel und effizient.
> - **Fourier-Basis:** Gut für periodische Daten.
> - **Radial Basisfunktionen:** Gut für multidimensionale, nichtlineare Beziehungen.
> - **Indikatorfunktionen:** Für kategorische Daten.


### Vergleich von Regression Splines, Smoothing Splines, GAM, GLM und Piecewise
> [!Vergleich von Regression Splines, Smoothing Splines, GAM, GLM und Piecewise]
>
> **Regression Splines:**
> $$
> y_i = \beta_0 + \beta_1 x_i + \beta_2 x_i^2 + \cdots + \beta_k x_i^k + \sum_{j=1}^{m} \gamma_j (x_i - \xi_j)_+^k + \epsilon_i
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_0, \beta_1, \ldots, \beta_k$: Regressionskoeffizienten
> - $x_i$: Prädiktorwert
> - $\gamma_j$: Spline-Koeffizienten
> - $\xi_j$: Knotenpunkte
> - $\epsilon_i$: Fehlerterm
>
> **Smoothing Splines:**
> $$
> \min \left\{ \sum_{i=1}^{n} (y_i - g(x_i))^2 + \lambda \int (g''(t))^2 dt \right\}
> $$
> - $y_i$: Beobachteter Wert
> - $g(x_i)$: Glättungsfunktion
> - $\lambda$: Glätteparameter
> - $t$: Integervariable
>
> **Generalized Additive Models (GAM):**
> $$
> y_i = \beta_0 + \sum_{j=1}^{p} f_j(x_{ij}) + \epsilon_i
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_0$: Interzept
> - $f_j(x_{ij})$: Glättungsfunktionen
> - $x_{ij}$: Prädiktorwert
> - $\epsilon_i$: Fehlerterm
>
> **Generalized Linear Models (GLM):**
> $$
> g(\mathbb{E}(Y)) = \beta_0 + \beta_1 x_1 + \cdots + \beta_p x_p
> $$
> - $Y$: Antwortvariable
> - $g$: Linkfunktion
> - $\beta_0, \beta_1, \ldots, \beta_p$: Regressionskoeffizienten
> - $x_1, \ldots, x_p$: Prädiktorwerte
>
> **Piecewise Regression:**
> $$
> y_i = \begin{cases} 
> \beta_{0,1} + \beta_{1,1} x_i & \text{für } a \leq x_i < b \\
> \beta_{0,2} + \beta_{1,2} x_i & \text{für } b \leq x_i < c \\
> \vdots & \vdots \\
> \beta_{0,k} + \beta_{1,k} x_i & \text{für } z \leq x_i < w
> \end{cases}
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_{0,1}, \beta_{1,1}, \ldots, \beta_{0,k}, \beta_{1,k}$: Segment-Koeffizienten
> - $x_i$: Prädiktorwert
> - $a, b, c, z, w$: Segmentgrenzen
>
> **Unterschiede und Verwendung:**
> - **Regression Splines:** Flexible, segmentierte Polynomiale für nicht-glatte Strukturen.
> - **Smoothing Splines:** Glatte Funktionen für kontinuierliche Daten; Balancierung durch $\lambda$.
> - **GAM:** Additive Modelle für nichtlineare Beziehungen; interpretiert einzelne Effekte.
> - **GLM:** Verallgemeinerung linearer Modelle; für lineare und nichtlineare, aber parametrische Beziehungen.
> - **Piecewise Regression:** Unterschiedliche lineare Modelle in verschiedenen Bereichen; einfach und interpretierbar für verschiedene Datenbereiche.


### Vergleich von Regression Splines, Smoothing Splines, GAM, GLM, Piecewise, Local Regression und Step Function Regression
> [!Vergleich von Regression Splines, Smoothing Splines, GAM, GLM, Piecewise, Local Regression und Step Function Regression]
>
> **Regression Splines:**
> $$
> y_i = \beta_0 + \beta_1 x_i + \beta_2 x_i^2 + \cdots + \beta_k x_i^k + \sum_{j=1}^{m} \gamma_j (x_i - \xi_j)_+^k + \epsilon_i
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_0, \beta_1, \ldots, \beta_k$: Regressionskoeffizienten
> - $x_i$: Prädiktorwert
> - $\gamma_j$: Spline-Koeffizienten
> - $\xi_j$: Knotenpunkte
> - $\epsilon_i$: Fehlerterm
>
> **Smoothing Splines:**
> $$
> \min \left\{ \sum_{i=1}^{n} (y_i - g(x_i))^2 + \lambda \int (g''(t))^2 dt \right\}
> $$
> - $y_i$: Beobachteter Wert
> - $g(x_i)$: Glättungsfunktion
> - $\lambda$: Glätteparameter
> - $t$: Integervariable
>
> **Generalized Additive Models (GAM):**
> $$
> y_i = \beta_0 + \sum_{j=1}^{p} f_j(x_{ij}) + \epsilon_i
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_0$: Interzept
> - $f_j(x_{ij})$: Glättungsfunktionen
> - $x_{ij}$: Prädiktorwert
> - $\epsilon_i$: Fehlerterm
>
> **Generalized Linear Models (GLM):**
> $$
> g(\mathbb{E}(Y)) = \beta_0 + \beta_1 x_1 + \cdots + \beta_p x_p
> $$
> - $Y$: Antwortvariable
> - $g$: Linkfunktion
> - $\beta_0, \beta_1, \ldots, \beta_p$: Regressionskoeffizienten
> - $x_1, \ldots, x_p$: Prädiktorwerte
> - $\epsilon$: Fehlerterm
>
> **Piecewise Regression:**
> $$
> y_i = \begin{cases} 
> \beta_{0,1} + \beta_{1,1} x_i & \text{für } a \leq x_i < b \\
> \beta_{0,2} + \beta_{1,2} x_i & \text{für } b \leq x_i < c \\
> \vdots & \vdots \\
> \beta_{0,k} + \beta_{1,k} x_i & \text{für } z \leq x_i < w
> \end{cases}
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_{0,1}, \beta_{1,1}, \ldots, \beta_{0,k}, \beta_{1,k}$: Segment-Koeffizienten
> - $x_i$: Prädiktorwert
> - $a, b, c, z, w$: Segmentgrenzen
>
> **Local Regression (LOESS/LOWESS):**
> $$
> \hat{y}_i = \sum_{j=1}^{n} w_j(x_i) y_j
> $$
> - $y_i$: Beobachteter Wert
> - $\hat{y}_i$: Vorhergesagter Wert
> - $w_j(x_i)$: Gewichtungsfunktion, die nahegelegene Beobachtungen stärker gewichtet
> - **Annahmen:** Keine spezielle funktionale Form; lokal gewichtete Regression.
> - **Verwendung:** Flexible Anpassung an lokale Strukturen in den Daten.
>
> **Step Function Regression:**
> $$
> y_i = \beta_0 + \sum_{j=1}^{k} \beta_j I(x_i \in I_j) + \epsilon_i
> $$
> - $y_i$: Beobachteter Wert
> - $\beta_0$: Interzept
> - $\beta_j$: Koeffizienten für die Intervalle
> - $I(x_i \in I_j)$: Indikatorfunktion, die 1 ist, wenn $x_i$ im Intervall $I_j$ liegt, und 0 sonst
> - $\epsilon_i$: Fehlerterm
> - **Annahmen:** Daten in diskrete Intervalle unterteilt.
> - **Verwendung:** Für Daten mit sprunghaften Änderungen.
> - 
**Unterschiede und Verwendung:**
> - **Regression Splines:** Flexible, segmentierte Polynomiale für nicht-glatte Strukturen.
> - **Smoothing Splines:** Glatte Funktionen für kontinuierliche Daten; Balancierung durch $\lambda$.
> - **GAM:** Additive Modelle für nichtlineare Beziehungen; interpretiert einzelne Effekte.
> - **GLM:** Verallgemeinerung linearer Modelle; für lineare und nichtlineare, aber parametrische Beziehungen.
> - **Piecewise Regression:** Unterschiedliche lineare Modelle in verschiedenen Bereichen; einfach und interpretierbar für verschiedene Datenbereiche.
> - **Local Regression:** Flexibel für lokale Strukturen; keine Annahme einer globalen Funktionalität.
> - **Step Function Regression:** Einfach und interpretierbar für Daten mit sprunghaften Änderungen; nützlich, wenn Änderungen in bestimmten Intervallen erwartet werden.




### Parametrische Modelle im Statistischen Lernen
> [!Parametrische Modelle im Statistischen Lernen]
>
> **Lineare Regression:**
> $$
> y_i = \beta_0 + \beta_1 x_i + \epsilon_i
> $$
> - Einfachstes Modell, für lineare Beziehungen.
>
> **Logistische Regression:**
> $$
> \log \left( \frac{p}{1 - p} \right) = \beta_0 + \beta_1 x
> $$
> - Für binäre Klassifikationsprobleme.
>
> **Poisson-Regression:**
> $$
> \log(\lambda) = \beta_0 + \beta_1 x
> $$
> - Für Zähldaten.
>
> **LDA (Lineare Diskriminanzanalyse):**
> $$
> \delta_k(x) = x^T \Sigma^{-1} \mu_k - \frac{1}{2} \mu_k^T \Sigma^{-1} \mu_k + \log(\pi_k)
> $$
> - Für Klassifikationsprobleme.
>
> **QDA (Quadratische Diskriminanzanalyse):**
> $$
> \delta_k(x) = -\frac{1}{2} \log|\Sigma_k| - \frac{1}{2} (x - \mu_k)^T \Sigma_k^{-1} (x - \mu_k) + \log(\pi_k)
> $$
> - Für Klassifikationsprobleme mit unterschiedlichen Kovarianzmatrizen.
>
> **Ridge Regression:**
> $$
> \min \left\{ \sum_{i=1}^n (y_i - \beta_0 - \beta_1 x_i)^2 + \lambda \sum_{j=1}^p \beta_j^2 \right\}
> $$
> - Regularisiert die lineare Regression, um Overfitting zu verhindern.
>
> **Lasso Regression:**
> $$
> \min \left\{ \sum_{i=1}^n (y_i - \beta_0 - \beta_1 x_i)^2 + \lambda \sum_{j=1}^p |\beta_j| \right\}
> $$
> - Setzt einige Koeffizienten auf null, was zu sparsamen Modellen führt.
>
> **Elastic Net:**
> $$
> \min \left\{ \sum_{i=1}^n (y_i - \beta_0 - \beta_1 x_i)^2 + \lambda_1 \sum_{j=1}^p |\beta_j| + \lambda_2 \sum_{j=1}^p \beta_j^2 \right\}
> $$
> - Kombination von Ridge und Lasso Regression.
>
> **Zusammenfassung:**
> - **Lineare Modelle:** Einfach und interpretierbar, für lineare Beziehungen.
> - **Logistische Modelle:** Für Klassifikationsprobleme, log-lineare Beziehungen.
> - **Regularisierte Modelle (Ridge, Lasso, Elastic Net):** Verhindern Overfitting, für lineare und nichtlineare Beziehungen.
> - **Diskriminanzanalyse (LDA, QDA):** Für Klassifikationsprobleme, nutzt unterschiedliche Kovarianzmatrizen.



### Weitere Parametrische Modelle im Statistischen Lernen
> [!Weitere Parametrische Modelle im Statistischen Lernen]
>
> **Bayesian Regression:**
> $$
> p(\beta|y) \propto p(y|\beta) p(\beta)
> $$
> - Schätzt Parameterverteilungen statt Punktwerte.
>
> **Probit Regression:**
> $$
> \Phi^{-1}(p) = \beta_0 + \beta_1 x
> $$
> - Für binäre Klassifikationsprobleme, ähnlich wie logistische Regression.
>
> **Multinomial Logistische Regression:**
> $$
> \log \left( \frac{p_k}{p_0} \right) = \beta_{0k} + \beta_{1k} x_1 + \cdots + \beta_{pk} x_p
> $$
> - Für mehrklassige Klassifikationsprobleme.
>
> **Negative Binomial Regression:**
> $$
> \log(\lambda) = \beta_0 + \beta_1 x
> $$
> - Für überdisperse Zähldaten.
>
> **Ordinal Logistische Regression:**
> $$
> \log \left( \frac{p(Y \leq j)}{p(Y > j)} \right) = \beta_0 + \beta_1 x
> $$
> - Für geordnete kategoriale Daten.
>
> **Survival Analysis (Cox Proportional Hazards Model):**
> $$
> h(t|x) = h_0(t) \exp(\beta_1 x_1 + \cdots + \beta_p x_p)
> $$
> - Für Zeit-zu-Ereignis Daten.
>
> **Zusammenfassung:**
> - **Bayesian Regression:** Schätzt Verteilungen, integriert Vorwissen.
> - **Probit/Logit/Multinomial:** Für Klassifikationsprobleme mit verschiedenen Verteilungen.
> - **Negative Binomial:** Handhabt überdisperse Zähldaten.
> - **Ordinal Logistische Regression:** Für geordnete Kategorien.
> - **Survival Analysis:** Modelliert Zeit-zu-Ereignis Daten.


### Annahmen der Modellsdcge im Statistischen Lernen
> [!Annahmen der Modelle im Statistischen Lernen]
>
> **Regression Splines:**
> - **Annahmen:**
>   - Knotenauswahl: Die Positionen der Knoten müssen festgelegt werden.
>   - Stetige Ableitungen bis zur Ordnung $k$ an den Knoten.
>   - Funktionale Form innerhalb der Segmente ist polynomiell.
> 
> **Smoothing Splines:**
> - **Annahmen:**
>   - Glätteparameter $\lambda$: Balanciert Glätte und Anpassung.
>   - Der Glättungsgrad wird durch Minimierung einer Penalisierungsfunktion bestimmt.
> 
> **Generalized Additive Models (GAM):**
> - **Annahmen:**
>   - Additivität: Die Gesamtfunktion ist die Summe von Glättungsfunktionen der einzelnen Prädiktoren.
>   - Die Glättungsfunktionen sind flexibel und können nichtlineare Beziehungen modellieren.
> 
> **Generalized Linear Models (GLM):**
> - **Annahmen:**
>   - Lineare Form auf transformiertem Mittelwert durch eine Linkfunktion $g$.
>   - Verteilung der Antwortvariable gehört zu einer Exponentialfamilie (z.B. Normalverteilung, Binomialverteilung).
>   - Unabhängigkeit der Beobachtungen.
> 
> **Piecewise Regression:**
> - **Annahmen:**
>   - Diskontinuierliche Segmente: Jedes Segment hat ein eigenes lineares Modell.
>   - Verschiedene lineare Modelle in den Segmenten.
> 
> **Bayesian Regression:**
> - **Annahmen:**
>   - Vorverteilungen (Priors) für die Parameter $\beta$ müssen spezifiziert werden.
>   - Posterior-Verteilung wird durch Bayes-Theorem geschätzt.
> 
> **Probit Regression:**
> - **Annahmen:**
>   - Die latente Variable, die die binäre Antwortvariable bestimmt, ist normalverteilt.
> 
> **Multinomial Logistische Regression:**
> - **Annahmen:**
>   - Für mehrklassige Klassifikationsprobleme.
>   - Unabhängigkeit der irrelevanten Alternativen (IIA).
> 
> **Negative Binomial Regression:**
> - **Annahmen:**
>   - Verwendet für überdisperse Zähldaten.
>   - Varianz ist größer als der Mittelwert (Overdispersion).
> 
> **Ordinal Logistische Regression:**
> - **Annahmen:**
>   - Für geordnete kategoriale Daten.
>   - Proportional Odds Annahme: Die Verhältniswahrscheinlichkeiten sind für alle Kategorien gleich.
> 
> **Survival Analysis (Cox Proportional Hazards Model):**
> - **Annahmen:**
>   - Proportional Hazards Annahme: Die Hazard-Raten der Gruppen sind proportional.
>   - Keine Zeitabhängigkeit der Hazard-Raten.
> 
> **Zusammenfassung:**
> - **Regression Splines:** Knotenauswahl, stetige Ableitungen.
> - **Smoothing Splines:** Glätteparameter, Minimierung einer Penalisierungsfunktion.
> - **GAM:** Additivität, flexible Glättungsfunktionen.
> - **GLM:** Lineare Form durch Linkfunktion, Verteilung aus Exponentialfamilie, Unabhängigkeit der Beobachtungen.
> - **Piecewise Regression:** Diskontinuierliche Segmente, verschiedene lineare Modelle.
> - **Bayesian Regression:** Spezifikation von Priors, Bayes-Theorem zur Schätzung.
> - **Probit Regression:** Normalverteilung der latenten Variable.
> - **Multinomial Logistische Regression:** Unabhängigkeit der irrelevanten Alternativen.
> - **Negative Binomial Regression:** Überdispersion der Zähldaten.
> - **Ordinal Logistische Regression:** Proportional Odds Annahme.
> - **Survival Analysis:** Proportional Hazards Annahme, keine Zeitabhängigkeit.


### Heteroskedastizität in der Linearen Regression
> [!Heteroskedastizität in der Linearen Regression]
**Definition:**
> Heteroskedastizität liegt vor, wenn die Varianz der Fehlerterme (\(\epsilon_i\)) in einem Regressionsmodell nicht konstant ist, sondern von den Werten der unabhängigen Variablen abhängt.
**Modellannahmen der linearen Regression:**
> Ein zentrales Modellannahme in der linearen Regression ist die Homoskedastizität, das bedeutet, dass die Varianz der Fehlerterme konstant ist:
> $$
> \text{Var}(\epsilon_i) = \sigma^2
> $$
**Folgen von Heteroskedastizität:**
> - Verzerrte Standardfehler: Die Schätzer für die Standardfehler der Regressionskoeffizienten sind verzerrt, was zu inkorrekten Konfidenzintervallen und Hypothesentests führen kann.
> - Ineffiziente Schätzer: Die Regressionskoeffizienten bleiben unverzerrt, aber sie sind nicht die effizientesten Schätzer.
**Methoden zur Korrektur von Heteroskedastizität:**
> - **Transformation der abhängigen Variable:**
>   - Log-Transformation: Kann die Varianz stabilisieren.
>   - Quadratische oder andere nichtlineare Transformationen.
> 
> - **Verwendung robuster Standardfehler:**
>   - Anpassung der Standardfehler der Koeffizientenschätzer, um die Verzerrung durch Heteroskedastizität zu kompensieren.
> 
> - **Generalized Least Squares (GLS):**
>   - Transformation des Modells, um die Varianz der Fehlerterme zu stabilisieren.
> 
> - **Weighted Least Squares (WLS):**
>   - Gewichtung der Beobachtungen mit der inversen Varianz der Fehlerterme, um die Effizienz der Schätzer zu verbessern.
> 
> **Literatur und weitere Informationen:**
> - "An Introduction to Statistical Learning" beschreibt diese Methoden detailliert und zeigt Beispiele, wie man sie anwendet【253†source】.
> - Weitere Erklärungen und technische Details finden sich in "Applied Regression Analysis" von Draper und Smith.


## Cheat sheet to learn:

### Modelle im Statistischen Lernen
> [!Modelle im Statistischen Lernen]
**1. Linear Regression**
> - **Simple Linear Regression:**
>   - **Formel:** $Y = \beta_0 + \beta_1 X + \epsilon$
>   - **Eigenschaften:** Modelliert die lineare Beziehung zwischen zwei Variablen.
>   - **Annahmen:** Lineare Beziehung, Unabhängigkeit der Fehler, Normalverteilung der Fehler, Homoskedastizität.
>   - **Degree of Freedom (DF):** $n - 2$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_0$: Interzept
>     - $\beta_1$: Steigung
>     - $X$: Prädiktor
>     - $\epsilon$: Fehlerterm
>
> - **Multiple Linear Regression:**
>   - **Formel:** $Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_p X_p + \epsilon$
>   - **Eigenschaften:** Erweiterung der einfachen linearen Regression auf mehrere Prädiktoren.
>   - **Annahmen:** Gleiche wie bei einfacher linearer Regression.
>   - **Degree of Freedom (DF):** $n - p - 1$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_0, \beta_1, \ldots, \beta_p$: Regressionskoeffizienten
>     - $X_1, X_2, \ldots, X_p$: Prädiktoren
>     - $\epsilon$: Fehlerterm
>    
>**2. Classification**
> - **Logistic Regression:**
>   - **Formel:** $\log \left( \frac{p}{1 - p} \right) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \cdots + \beta_p X_p$
>   - **Eigenschaften:** Modelliert die Wahrscheinlichkeit eines binären Outcomes.
>   - **Annahmen:** Logit-Funktion ist linear in den Prädiktoren.
>   - **Degree of Freedom (DF):** $n - p - 1$
>   - **Verteilung:** Binomialverteilung der Antwortvariable
>   - **Größen:**
>     - $p$: Wahrscheinlichkeit des Ereignisses
>     - $\beta_0, \beta_1, \ldots, \beta_p$: Regressionskoeffizienten
>     - $X_1, X_2, \ldots, X_p$: Prädiktoren
> 
> - **Linear Discriminant Analysis (LDA):**
>   - **Formel:** $\delta_k(x) = x^T \Sigma^{-1} \mu_k - \frac{1}{2} \mu_k^T \Sigma^{-1} \mu_k + \log \pi_k$
>   - **Eigenschaften:** Findet lineare Kombinationen der Prädiktoren, die die Klassen am besten trennen.
>   - **Annahmen:** Multivariate Normalverteilung der Prädiktoren, gleiche Kovarianzmatrix für alle Klassen.
>   - **Degree of Freedom (DF):** $p(k - 1)$
>   - **Verteilung:** Multivariate Normalverteilung
>   - **Größen:**
>     - $\delta_k(x)$: Diskriminanzfunktion für Klasse $k$
>     - $x$: Prädiktorvektor
>     - $\Sigma$: Kovarianzmatrix
>     - $\mu_k$: Mittelwertvektor der Klasse $k$
>     - $\pi_k$: A-priori Wahrscheinlichkeit der Klasse $k$
>     - 
> - **Quadratic Discriminant Analysis (QDA):**
>   - **Formel:** $\delta_k(x) = -\frac{1}{2} \log |\Sigma_k| - \frac{1}{2} (x - \mu_k)^T \Sigma_k^{-1} (x - \mu_k) + \log \pi_k$
>   - **Eigenschaften:** Erweiterung von LDA, erlaubt unterschiedliche Kovarianzmatrizen für jede Klasse.
>   - **Annahmen:** Multivariate Normalverteilung der Prädiktoren.
>   - **Degree of Freedom (DF):** $\sum_{k=1}^K (p_k + \frac{p(p+1)}{2})$
>   - **Verteilung:** Multivariate Normalverteilung
>   - **Größen:**
>     - $\delta_k(x)$: Diskriminanzfunktion für Klasse $k$
>     - $x$: Prädiktorvektor
>     - $\Sigma_k$: Kovarianzmatrix der Klasse $k$
>     - $\mu_k$: Mittelwertvektor der Klasse $k$
>     - $\pi_k$: A-priori Wahrscheinlichkeit der Klasse $k$
> 
> - **K-Nearest Neighbors (KNN):**
>   - **Eigenschaften:** Klassifiziert neue Datenpunkte basierend auf den $k$ nächsten Nachbarn im Trainingsdatensatz.
>   - **Annahmen:** Keine spezifischen Verteilungsannahmen, nicht-parametrisch.
>   - **Degree of Freedom (DF):** Effektive Freiheitsgrade variieren je nach $k$
>   - **Verteilung:** Nicht parametrisch
>   - **Größen:**
>     - $k$: Anzahl der nächsten Nachbarn
> 
> - **Naive Bayes:**
>   - **Formel:** $P(Y = k | X = x) = \frac{P(X = x | Y = k) P(Y = k)}{P(X = x)}$
>   - **Eigenschaften:** Annahme der Unabhängigkeit der Prädiktoren gegeben die Klassen.
>   - **Annahmen:** Bedingte Unabhängigkeit der Prädiktoren.
>   - **Degree of Freedom (DF):** Variiert je nach Anzahl der Klassen und Prädiktoren.
>   - **Verteilung:** Unterschiedlich je nach Art des Naive Bayes Modells (z.B. Gaussian, Multinomial)
>   - **Größen:**
>     - $P(Y = k | X = x)$: Posteriori Wahrscheinlichkeit der Klasse $k$
>     - $P(X = x | Y = k)$: Likelihood der Prädiktoren gegeben die Klasse $k$
>     - $P(Y = k)$: A-priori Wahrscheinlichkeit der Klasse $k$
> 
**3. Linear Model Selection and Regularization**
> - **Subset Selection:**
>   - **Eigenschaften:** Wählt eine Untermenge der Prädiktoren aus, die das Modell optimiert.
>   - **Annahmen:** Gleich wie bei der linearen Regression.
>   - **Degree of Freedom (DF):** Anzahl der ausgewählten Prädiktoren.
>   - **Verteilung:** Normalverteilung der Fehler.
>   - **Größen:**
>     - $k$: Anzahl der ausgewählten Prädiktoren
> 
> - **Shrinkage Methods (Ridge Regression, Lasso):**
>   - **Ridge Regression:**
>     - **Formel:** 
>     $$
>     \min \left\{ \sum_{i=1}^{n} (y_i - \beta_0 - \sum_{j=1}^{p} \beta_j x_{ij})^2 + \lambda \sum_{j=1}^{p} \beta_j^2 \right\}
>     $$
>     - **Eigenschaften:** Fügt einen L2-Penalisierungsterm hinzu, um die Koeffizienten zu schrumpfen.
>     - **Annahmen:** Gleich wie bei der linearen Regression.
>     - **Degree of Freedom (DF):** $\text{trace}(\mathbf{H})$
>     - **Verteilung:** Normalverteilung der Fehler.
>     - **Größen:**
>       - $\lambda$: Regularisierungsparameter
>  
>   - **Lasso:**
>     - **Formel:** 
>     $$
>     \min \left\{ \sum_{i=1}^{n} (y_i - \beta_0 - \sum_{j=1}^{p} \beta_j x_{ij})^2 + \lambda \sum_{j=1}^{p} |\beta_j| \right\}
>     $$
>     - **Eigenschaften:** Fügt einen L1-Penalisierungsterm hinzu, kann Koeffizienten auf null setzen.
>     - **Annahmen:** Gleich wie bei der linearen Regression.
>     - **Degree of Freedom (DF):** $\text{Anzahl der nicht-null Koeffizienten}$
>     - **Verteilung:** Normalverteilung der Fehler.
>     - **Größen:**
>       - $\lambda$: Regularisierungsparameter
>
>**5. Non-linear Models**
> - **Polynomial Regression:**
>   - **Formel:** $Y = \beta_0 + \beta_1 X + \beta_2 X^2 + \cdots + \beta_d X^d + \epsilon$
>   - **Eigenschaften:** Modelliert nicht-lineare Beziehungen durch Hinzufügen von Potenztermen des Prädiktors.
>   - **Annahmen:** Gleiche wie bei der linearen Regression.
>   - **Degree of Freedom (DF):** $n - (d + 1)$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_0, \beta_1, \ldots, \beta_d$: Regressionskoeffizienten
>     - $X$: Prädiktor
>     - $\epsilon$: Fehlerterm
>     - $d$: Grad des Polynoms
>- **Step Functions:**
>   - **Formel:** $Y = \beta_0 + \beta_1 I(X \leq \xi_1) + \beta_2 I(\xi_1 < X \leq \xi_2) + \cdots + \beta_k I(X > \xi_{k-1}) + \epsilon$
>   - **Eigenschaften:** Teilt den Prädiktorraum in Intervalle und passt eine konstante Funktion in jedem Intervall an.
>   - **Annahmen:** Gleiche wie bei der linearen Regression.
>   - **Degree of Freedom (DF):** $n - k$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_0, \beta_1, \ldots, \beta_k$: Regressionskoeffizienten
>     - $X$: Prädiktor
>     - $I(\cdot)$: Indikatorfunktion
>     - $\xi_i$: Schwellenwerte
>     
> - **Regression Splines:**
>   - **Formel:** $Y = \beta_0 + \beta_1 X + \beta_2 X^2 + \cdots + \beta_d X^d + \sum_{k=1}^{K} \gamma_k (X - \xi_k)_+^d + \epsilon$
>   - **Eigenschaften:** Fügt Knotensplines hinzu, um Flexibilität zu erhöhen.
>   - **Annahmen:** Gleiche wie bei der linearen Regression.
>   - **Degree of Freedom (DF):** $n - (d + K + 1)$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_0, \beta_1, \ldots, \beta_d$: Regressionskoeffizienten
>     - $X$: Prädiktor
>     - $\gamma_k$: Koeffizienten der Knotensplines
>     - $\xi_k$: Knotenpunkte
>     
> - **Natural Splines:**
>   - **Formel:** $Y = \sum_{i=1}^{d} \beta_i N_i(X) + \epsilon$
>   - **Eigenschaften:** Eine spezielle Art von Regression Splines, die natürliche Randbedingungen haben, um die Flexibilität am Rand des Datenbereichs zu reduzieren.
>   - **Annahmen:** Gleiche wie bei der linearen Regression.
>   - **Degree of Freedom (DF):** Abhängig von der Anzahl der Knoten und der Ordnung der Splines
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_i$: Regressionskoeffizienten
>     - $N_i(X)$: Basisfunktionen der natürlichen Splines
>     - $\epsilon$: Fehlerterm
>     
> - **Smoothing Splines:**
>   - **Formel:** $Y = \sum_{i=1}^{n} \beta_i S_i(X) + \epsilon$
>   - **Eigenschaften:** Nutzt einen Glätteparameter $\lambda$, um die Glätte der Anpassung zu regulieren.
>   - **Annahmen:** Gleich wie bei der linearen Regression.
>   - **Degree of Freedom (DF):** $\text{trace}(\mathbf{S})$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_i$: Regressionskoeffizienten
>     - $S_i(X)$: Smoothing Splines Basisfunktionen
>     - $\lambda$: Glätteparameter
>     - $\epsilon$: Fehlerterm
>     
> - **Local Regression:**
>   - **Formel:** $Y = \sum_{i=1}^{n} w_i(X) y_i$
>   - **Eigenschaften:** Passt einfache Modelle (z.B. lineare Regression) in einem gleitenden Fenster der Daten an.
>   - **Annahmen:** Keine spezifischen Verteilungsannahmen, nicht-parametrisch.
>   - **Degree of Freedom (DF):** $\sum_{i=1}^{n} w_{ii}$
>   - **Verteilung:** Nicht-parametrisch
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $w_i(X)$: Gewichte der lokalen Regression
>     - $y_i$: Beobachtungen
>     
> - **Generalized Additive Models (GAMs):**
>   - **Formel:** $Y = \beta_0 + \sum_{j=1}^{p} f_j(X_j) + \epsilon$
>   - **Eigenschaften:** Additive Modelle, die nicht-lineare Funktionen der Prädiktoren verwenden.
>   - **Annahmen:** Additivität der Effekte der Prädiktoren.
>   - **Degree of Freedom (DF):** Summe der Freiheitsgrade der einzelnen $f_j$
>   - **Verteilung:** Normalverteilung der Fehler $\epsilon \sim \mathcal{N}(0, \sigma^2)$
>   - **Größen:**
>     - $Y$: Antwortvariable
>     - $\beta_0$: Interzept
>     - $f_j(X_j)$: Glättungsfunktionen
>     - $\epsilon$: Fehlerterm
>     
**6. Unsupervised Learning**
> - **Principal Component Analysis (PCA):**
>   - **Formel:** $Z = XW$
>   - **Eigenschaften:** Reduziert die Dimension der Daten, indem sie orthogonale Hauptkomponenten extrahiert.
>   - **Annahmen:** Keine spezifischen Verteilungsannahmen.
>   - **Degree of Freedom (DF):** Anzahl der Hauptkomponenten
>   - **Verteilung:** Nicht-parametrisch
>   - **Größen:**
>     - $Z$: Hauptkomponenten
>     - $X$: Ursprüngliche Daten
>     - $W$: Gewichte der Hauptkomponenten
>    
> - **K-Means Clustering:**
>   - **Formel:** Minimiert die Summe der quadrierten Distanzen zwischen Datenpunkten und dem nächstgelegenen Clusterzentrum
>   - **Eigenschaften:** Partitioniert die Daten in $k$ Cluster.
>   - **Annahmen:** Keine spezifischen Verteilungsannahmen.
>   - **Degree of Freedom (DF):** Anzahl der Cluster $k$
>   - **Verteilung:** Nicht-parametrisch
>   - **Größen:**
>     - $k$: Anzahl der Cluster
>    
> - **Hierarchical Clustering:**
>   - **Formel:** Dendrogramm-basierte Darstellung der Datencluster
>   - **Eigenschaften:** Bildet eine hierarchische Struktur der Datencluster.
>   - **Annahmen:** Keine spezifischen Verteilungsannahmen.
>   - **Degree of Freedom (DF):** Abhängig von der Höhe der Hierarchie
>   - **Verteilung:** Nicht-parametrisch
>   - **Größen:**
>     - $h$: Höhe des Dendrogramms


todo:
- generative vs discriminative beispiel mit smote
- bayes lda qda


![Pasted image 20240710230255.png](/img/user/Files/Pasted%20image%2020240710230255.png)![Pasted image 20240710230348.png](/img/user/Files/Pasted%20image%2020240710230348.png)![Pasted image 20240710230549.png](/img/user/Files/Pasted%20image%2020240710230549.png)

![Pasted image 20240710230803.png](/img/user/Files/Pasted%20image%2020240710230803.png)



## quick learning:


### Naive Bayes Klassifikator: Formel und Annahmen

#### Formel
Der Naive Bayes Klassifikator nutzt das Bayes-Theorem:

\[ P(C|X) \propto P(C) \prod_{i=1}^{n} P(x_i|C) \]

Dabei steht \( C \) für die Klasse und \( X = (x_1, x_2, \ldots, x_n) \) für die Merkmale. Die Vorhersage erfolgt durch Maximierung:

\[ \hat{C} = \arg\max_C P(C) \prod_{i=1}^{n} P(x_i|C) \]

#### Annahmen
1. **Bedingte Unabhängigkeit:** 
   - Jedes Merkmal \( x_i \) ist unabhängig von den anderen Merkmalen \( x_j \) gegeben die Klasse \( C \).
   
2. **Gleiche Wichtigkeit aller Merkmale:** 
   - Alle Merkmale tragen unabhängig voneinander zur Klassifizierung bei.

Diese Annahmen vereinfachen die Berechnungen erheblich und ermöglichen effiziente Klassifizierungsalgorithmen.


### Gesetzt der Kontinuitaet
ähnliche Dinge sind näher bei einander und unähnliche Dinge sind weiter ausseinander

### ETC
- Naive Bayes hat als annahme, dass alle Klassen unabhähgig von einande sind. 
- LDA hat als annhame, dass die Merkmale/Beobachtungen normalverteilt in den einzelnen Klassen sind. Ausserdem nimmt LDA an, dass alle Klassen die gleiche Kovarianz Matrix haben. Descion boundires sind linear.
- QDA ist wie LDA auch annahme merkamle in den einzelnen Klassen normalverteilt und jetzt noch die annahme, dass jede Klasse ihre eigene Kovarianz Matrix haben kann. Dadurch koennen die Descion Boundries quadratisch sein.

- Dikriminative Modelle trainieren die desicion boundry um die Klassen zu trennen.
- Generative Modelle trainieren die Warscheinlichverteilungsfunktion, um die Descion Boundries aufzustellen.

- Die Maximum Likelihood bei der Linearen Regression besagt, dass man zu den fitt waehlen soll also so die fehler minimieren, dass man alle Punkte in der normalverteilung bei der hoechsten wahrscheinlichkeit hat. ![Pasted image 20240711155604.png](/img/user/Files/Pasted%20image%2020240711155604.png)![Pasted image 20240711155631.png](/img/user/Files/Pasted%20image%2020240711155631.png)
- ![Pasted image 20240711155802.png](/img/user/Files/Pasted%20image%2020240711155802.png)

LR annahmen: Residuen normalverteilt, erwartungswert 0, linearitaet des fs, unabhaegigkeit der einzelnen Samples, keine Kolinearitat, konstante variance

- Der P Wert gibt an wie unwahrschienlich es ist, dass etwas zufaellig passiert ist wenn p 0.05 kann die H0 hyptothese verworfen werden.
- F-Statistic um zu ueber pruefen ob irgendeine parameter signifikant ist also besser als kein modell.
- Prediction interval berechnet, die unsicherheit des modelles und die unsicherheit der daten
- Die Additivitaet kann man auflockern mit interaktionen von dummy variablen
- hierachische prinzip, man muss die haupteffecte drinnen lassen auf wenn nicht significatin von bei den interactionen.
- Heteroskedazitaet die Fehler sind abhaegig von dem y
- homoskedazitaet die Fehler sind unabhaegig von dem Y wert

- high leverage points sind aussreisser, die nicht mehr in der verteilung der praedictoren sind.

![Pasted image 20240711163458.png](/img/user/Files/Pasted%20image%2020240711163458.png)
![Pasted image 20240711163525.png](/img/user/Files/Pasted%20image%2020240711163525.png)

log odds macht einen werte bereich zwischen minus unedlich und unedlich.
- Die Parameter in der Logistischen Funktion ändern nun nicht die Y anhängige variable sondern die odds . Das heisst negative beta kleinere odds heisst kleinere wahrscheinlichkeiten.
- Confounding: Zusammenhang von Korrelation und Kausalitaet, wir modelieren nie kausalitaet

Softmax bringt alle auf 1
![Pasted image 20240711164200.png](/img/user/Files/Pasted%20image%2020240711164200.png)
![Pasted image 20240711164502.png](/img/user/Files/Pasted%20image%2020240711164502.png)
![Pasted image 20240711164619.png](/img/user/Files/Pasted%20image%2020240711164619.png)

dieses f_k(x) muss jetzt modlliert werden.

![Pasted image 20240711164838.png](/img/user/Files/Pasted%20image%2020240711164838.png)


![Pasted image 20240711165042.png](/img/user/Files/Pasted%20image%2020240711165042.png)

QDA und LDA kann man dann in das bayesche theorem einsetzen:
![Pasted image 20240711165133.png](/img/user/Files/Pasted%20image%2020240711165133.png)

Naive bayes --> naive weil nimmt eine annahme dass alle klassen unabhaegig sind.
![Pasted image 20240711165617.png](/img/user/Files/Pasted%20image%2020240711165617.png)
Naive bayes ist wie LDA aber mit einer diagonal matrix sigma


poisson verteilung:
![Pasted image 20240711171519.png](/img/user/Files/Pasted%20image%2020240711171519.png)

![Pasted image 20240711171614.png](/img/user/Files/Pasted%20image%2020240711171614.png)