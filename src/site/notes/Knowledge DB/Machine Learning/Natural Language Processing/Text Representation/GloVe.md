---
{"dg-publish":true,"permalink":"/knowledge-db/machine-learning/natural-language-processing/text-representation/glo-ve/","noteIcon":""}
---

longform: Global Vectodoc

### Usecase of GloVe
It has the same Usecase as Word2Vec but it uses its global context for the embedding of the words into multidimensionalv vectors.


1. Build the Term cooccurence matrix
2. Matrix factorization
3. Vectorrepresenation of Words
4. Use similarity like cosine sim 
5. Use Probality Ratio P(k|word) and with that it calculate the relation to the words getting the Words closer toghether.
6. backprop: Optimizes probality ratio


**GloVe: Global Vectors for Word Representation**

- **Overview**: 
  GloVe is a method for obtaining distributed representations of words by aggregating global word-word co-occurrence statistics from a corpus. The model is designed to capture both local and global contextual information in its embeddings.

- **Advantages over Word2Vec**:
  - **Global Statistical Information**: Unlike Word2Vec, which relies on local context data within a specific window around each word, GloVe constructs embeddings by examining statistics across the entire corpus.
  - **Efficient Use of Statistics**: GloVe trains on non-zero entries of a word-context co-occurrence matrix, improving efficiency and scalability.
  - **Robust Word Embeddings**: By integrating both global and local contexts, GloVe embeddings tend to capture a broader range of semantic and syntactic nuances.

- **Co-occurrence Matrix Example**:
  The co-occurrence matrix is the cornerstone of the GloVe model. Here's a simplified example to illustrate what it might look like for a small vocabulary:

  Suppose we have a tiny corpus: "the cat sat on the mat."

  - **Vocabulary**: {the, cat, sat, on, mat}
  - **Window Size**: 1 (each word is paired with its immediate neighbors)

  The resulting co-occurrence matrix could be:

  |       | the | cat | sat | on | mat |
  |-------|-----|-----|-----|----|-----|
  | **the** |  0  |  2  |  1  | 1  |  1  |
  | **cat** |  2  |  0  |  1  | 0  |  0  |
  | **sat** |  1  |  1  |  0  | 1  |  0  |
  | **on**  |  1  |  0  |  1  | 0  |  1  |
  | **mat** |  1  |  0  |  0  | 1  |  0  |

  In this matrix:
  - **Rows and columns** represent words.
  - **Matrix elements** indicate how often each pair of words occurs within the chosen window size around each other in the corpus.
  
  For instance, "the" and "cat" appear together 2 times within the window size of 1 word in the text.

This example is highly simplified. In real scenarios, the matrix is large, sparse, and constructed from extensive text corpora to capture meaningful statistical relationships between words effectively.