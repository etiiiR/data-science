---
{"dg-publish":true,"permalink":"/knowledge-db/machine-learning/natural-language-processing/text-representation/fast-text/","noteIcon":""}
---

**FastText: Enhanced Word Representations with Subword Information**


- **Overview**:
  FastText is an extension of the Word2Vec model that incorporates subword information by breaking words down into smaller pieces (subwords). This approach allows FastText to generate word embeddings not only for words present in the training corpus but also for out-of-vocabulary (OOV) words.

- **Advantages over Word2Vec**:
  - **Handling of Rare and Unknown Words**: FastText can produce embeddings for OOV words by summing the vectors of its subword components, which is not possible with traditional Word2Vec.
  - **Richer Word Representations**: By considering subword information (like prefixes, suffixes, and roots), FastText captures more morphological information, which is particularly beneficial for agglutinative languages such as Turkish or Finnish.
  - **Robustness to Typos**: The subword approach helps in dealing with typos and misspellings, as similar words will share many of the same subword units.

- **Example of Subword Usage**:
  Let’s consider the word "apple". FastText would break this down into subwords (with a chosen subword length of 3 to 6 characters):
  
  - **Subwords of Length 3**: app, ppl, ple
  - **Subwords of Length 4**: appl, pple
  - **Subwords of Length 5**: apple
  
  For each of these subwords, embeddings are pre-trained, and the final vector for "apple" is derived by summing the vectors of these subwords along with the whole word itself.

- **Embedding Matrix Example**:
  The embedding matrix in FastText is built by combining the vectors of subwords for each word. Here is a conceptual example for the word "apple", assuming simple numerical vectors for illustration:

  | Subword | Vector          |
  |---------|-----------------|
  | app     | [0.1, -0.2, 0.3]|
  | ppl     | [0.0, 0.1, -0.1]|
  | ple     | [-0.1, 0.0, 0.2]|
  | appl    | [0.2, -0.1, 0.0]|
  | pple    | [0.1, 0.1, 0.1] |
  | apple   | [0.3, 0.2, -0.2]|

  The final embedding for "apple" would be the sum of these vectors, which captures both the full word and its constituent parts. This allows the model to leverage deeper morphological information than Word2Vec, which only considers the word as a whole entity.

This enhanced method provides significant improvements, particularly in dealing with diverse linguistic phenomena and enhancing the model's ability to generalize from its training data.