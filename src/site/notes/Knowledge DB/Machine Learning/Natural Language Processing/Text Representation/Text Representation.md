---
{"dg-publish":true,"permalink":"/knowledge-db/machine-learning/natural-language-processing/text-representation/text-representation/","noteIcon":""}
---

### Textbereinigung
Textbereinigung ist der Prozess, unerwünschte oder irrelevante Informationen aus den Textdaten zu entfernen. Dies kann umfassen:
- **Entfernen von Sonderzeichen und Zahlen**, die für die spezifische Analyse nicht benötigt werden.
- **Entfernen von Stoppwörtern** wie "und", "ist" oder "die", die häufig vorkommen, aber meist wenig zur Bedeutung des Textes beitragen.
- **Kleinbuchstaben-Umwandlung**, um die Konsistenz zu erhöhen und die Anzahl der einzigartigen Tokens zu reduzieren.
- **Entfernen von HTML-Tags**, wenn Texte aus dem Web extrahiert werden.

### Tokenisierung

Tokenisierung ist der Prozess der Aufteilung von Text in kleinere Einheiten (Tokens), typischerweise Wörter oder Sätze.
- **Wort-Tokenisierung** zerlegt den Text in Wörter oder Phrasen.
- **Satz-Tokenisierung** zerlegt den Text in einzelne Sätze, was nützlich für Aufgaben wie die Sentiment-Analyse sein kann.

**Wort-Tokenisierung:**  
Text: "Hello World!"  
Tokens: ["Hello", "World"]

**Satz-Tokenisierung:**  
Text: "Hello World! Wie geht es dir?"  
Tokens: ["Hello World!", "Wie geht es dir?"]

### Normalisierung
Normalisierung bezieht sich auf Prozesse, die Textdaten vereinheitlichen, um sie einfacher zu analysieren:
- **Stemming** reduziert Wörter auf ihren Stamm oder die Wurzel, oft durch Abschneiden von Präfixen und Suffixen.
- **Lemmatisierung** reduziert Wörter auf ihre Grundform, aber im Gegensatz zum Stemming, basiert dieser Prozess auf einer tatsächlichen linguistischen Analyse, um sicherzustellen, dass das transformierte Wort auch ein gültiges Wort ist.


**Stemming:**  
Text: "Cats running ran."  
Gestemmt: ["Cat", "run", "ran"]

**Lemmatisierung:**  
Text: "The mice ate the cheese."  
Lemmatisiert: ["The", "mouse", "eat", "the", "cheese"]

### Stopfwort-Entfernung
Das Entfernen von Stoppwörtern kann helfen, die Datenmenge zu reduzieren und den Fokus auf bedeutungsvollere Wörter zu legen.


Text: "The quick brown fox jumps over the lazy dog."  
Ohne Stoppwörter: ["quick", "brown", "fox", "jumps", "over", "lazy", "dog"]

### Part-of-Speech-Tagging
Part-of-Speech-Tagging (POS-Tagging) ist das Markieren von Wörtern in einem Text (Token) als Substantive, Verben, Adjektive usw. Dies ist besonders nützlich für syntaktische und semantische Analysen.

Text: "Apple is looking at buying U.K. startup for $1 billion."  
POS-Tagging:

- Apple (Nomen)
- is (Verb)
- looking (Verb)
- at (Präposition)
- buying (Verb)
- U.K. (Nomen)
- startup (Nomen)
- for (Präposition)
- $1 billion (Numeral)

### Named Entity Recognition (NER)
NER ist der Prozess der Identifikation und Klassifikation von Namen spezifischer Entitäten in Texten (z.B. Personen, Orte, Organisationen). Dies ist wichtig für viele Anwendungen wie automatische Zusammenfassung oder Verbesserung von Suchalgorithmen.

Text: "Angela Merkel met with Barack Obama in Berlin."  
NER-Ergebnisse:

- Angela Merkel (Person)
- Barack Obama (Person)
- Berlin (Ort)

### Parsing
Syntaktisches Parsing hilft zu verstehen, wie ein Satz strukturiert ist, was wichtig für Aufgaben wie die Übersetzung oder das Verständnis komplexer Fragen ist.

Text: "The small cat ate the big mouse."  
Parsing-Ergebnis könnte etwa so aussehen:

- The small cat (Subjekt)
- ate (Verb)
- the big mouse (Objekt)
### Wort-Embeddings
Nach der Bereinigung und Normalisierung des Textes können Techniken wie Word2Vec, GloVe oder FastText verwendet werden, um Wörter in Vektoren umzuwandeln. Diese Vektoren repräsentieren semantische Bedeutungen und können in vielen fortschrittlichen NLP-Modellen verwendet werden.

Durch die effektive Anwendung dieser Schritte in der Textvorbereitung kann die Leistung von NLP-Modellen erheblich verbessert werden, da die Qualität und Konsistenz der Eingabedaten direkt die Ergebnisse beeinflusst.



### Word2Vec  
Ein Modell, das Wörter in dichte Vektorräume abbildet, basierend auf deren Kontext. Es gibt zwei Architekturen: Continuous Bag of Words (CBOW) und Skip-Gram. Das Ziel ist es, Wörter mit ähnlichen Bedeutungen nahe beieinander im Vektorraum zu positionieren.

![Pasted image 20240428174512.png](app://6fccb7f67acf71637368b9c2f369c9ef4c1a/C:/Users/roeti/OneDrive%20-%20Coop%20Genossenschaft/Dokumente/Obsidian/Privat/Organisation/Pasted%20image%2020240428174512.png?1714319112736)


### FastText  
Ähnlich wie Word2Vec, jedoch mit der Fähigkeit, Subwörter oder n-Gramme von Buchstaben während des Trainings zu berücksichtigen. FastText bietet bessere Leistung für seltene Wörter und in Sprachen mit reicher Morphologie.

## TF-IDF (Term Frequency-Inverse Document Frequency)
Ein statistisches Maß zur Bewertung, wie wichtig ein Wort in einem Dokument im Vergleich zu einem Korpus ist. TF-IDF kombiniert die Häufigkeit eines Wortes im Dokument mit der inversen Häufigkeit des Wortes über mehrere Dokumente hinweg.

### PPMI (Positive Pointwise Mutual Information)
Eine statistische Technik zur Quantifizierung der Assoziation zwischen zwei Wörtern, basierend auf der Wahrscheinlichkeit ihres gemeinsamen Auftretens im Vergleich zur Wahrscheinlichkeit ihres unabhängigen Auftretens. PPMI bevorzugt seltenere Wortpaare, die häufig zusammen auftreten.

### Sparse und Dense Vectors 
Sparse Vectors sind durch hohe Dimensionalität mit vielen Nullen charakterisiert, typisch für One-Hot-Encoding und Bag-of-Words-Modelle. Dense Vectors haben eine niedrigere Dimensionalität, aber jede Dimension trägt eine reichhaltige Menge an Informationen, typisch für Word2Vec und GloVe.

### GloVe (Global Vectors for Word Representation)
Ein Modell zur Wortvektorrepräsentation, das auf der Matrixfaktorisierung basiert und globale Wort-Wort-Ko-Okkurrenzstatistiken berücksichtigt.
Insgesamt ermöglicht GloVe durch seine Fähigkeit, die Beziehungen zwischen Wörtern in einem Vektorraum darzustellen, eine effektive und tiefgreifende Analyse von Sprache, was es zu einem wertvollen Werkzeug in verschiedenen NLP-Anwendungen macht.

### Stetic Emdedding**
Statische Embeddings, wie Word2Vec und GloVe, repräsentieren Wörter als feste Vektoren in einem hochdimensionalen Raum, basierend auf deren Gebrauch und Kontext im Trainingsdatensatz. Diese Vektoren fangen die semantischen und syntaktischen Ähnlichkeiten zwischen den Wörtern ein, sind jedoch nicht in der Lage, unterschiedliche Bedeutungen eines Wortes in verschiedenen Kontexten zu erfassen.

