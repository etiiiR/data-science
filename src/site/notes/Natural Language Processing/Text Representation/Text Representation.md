---
{"_filters":[],"_contexts":[],"_links":[],"_sort":{"field":"rank","asc":false,"group":false},"dg-publish":true,"permalink":"/natural-language-processing/text-representation/text-representation/","dgPassFrontmatter":true}
---

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

