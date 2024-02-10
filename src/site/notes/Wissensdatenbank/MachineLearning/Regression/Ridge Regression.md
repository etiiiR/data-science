---
{"sticker":"emoji//1f7e7","dg-publish":true,"permalink":"/wissensdatenbank/machine-learning/regression/ridge-regression/","dgPassFrontmatter":true}
---

Ridge Regression ist eine Form der linearen Regression, die Regularisierung verwendet, um Overfitting zu verhindern und die Koeffizienten zu schrumpfen. Der Hauptparameter, der in der Ridge Regression eingestellt wird, ist der Regularisierungsparameter alpha. Ein höherer Wert von alpha erhöht die Stärke der Regularisierung, was zu kleineren Koeffizienten führt.

## Definition

> [!NOTE]
> Natürlich! Die Ridge Regression erweitert die normale lineare Regression um einen Regularisierungsterm. Die Kostenfunktion \( J \) für die Ridge Regression ist wie folgt:
> $$
>J(\theta) = \frac{1}{2m} \sum_{i=1}^{m} (h_\theta(x^{(i)}) - y^{(i)})^2 + \frac{\alpha}{2} \sum_{j=1}^{n} \theta_{j^2 }
>$$

Hierbei ist:

- $h_\theta(x^{(i)})$  die Vorhersage des Modells für den i-ten Datenpunkt.
- $y^{(i)}$  der tatsächliche Wert des i-ten Datenpunkts.
- $m$ die Anzahl der Datenpunkte.
- $\theta$ der Vektor der Modellparameter, wobei \( \theta_j \) der j-te Parameter ist.
- n die Anzahl der Features (ohne den Bias-Term).
- $\alpha$ der Regularisierungsparameter.

Der erste Term ist der durchschnittliche quadratische Fehler (Mean Squared Error, MSE) der Vorhersagen. Der zweite Term ist der Regularisierungsterm, der die Größe der Koeffizienten bestraft. Beachten Sie, dass der Regularisierungsterm nicht den Bias-Term \( \theta_0 \) beinhaltet.


## Python code

``` python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import Ridge
from sklearn.metrics import mean_squared_error
from sklearn.datasets import load_boston

# Daten laden
data = load_boston()
X = data.data
y = data.target

# Daten teilen
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Modell erstellen und trainieren
ridge = Ridge(alpha=1.0)  # alpha ist der Regularisierungsparameter
ridge.fit(X_train, y_train)

# Vorhersagen und Performance bewerten
train_pred = ridge.predict(X_train)
test_pred = ridge.predict(X_test)

print("Trainingsfehler (MSE):", mean_squared_error(y_train, train_pred))
print("Testfehler (MSE):", mean_squared_error(y_test, test_pred))

```

## Math
![Pasted image 20231002132830.png](/img/user/Organisation/Files/Pasted%20image%2020231002132830.png)



## Beobachtungen

- Das Modell wird weniger komplex, auch schon mit kleinem λ 
- Grosse λ können zu Underfitting führen
- Die Koeffizienten sind zwar klein, aber nicht Null. Dies ist ein wichtiger Punkt, der später erklärt wird.