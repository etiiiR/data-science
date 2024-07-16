---
{"dg-publish":true,"permalink":"/knowledge-db/machine-learning/natural-language-processing/transformer/transformer/"}
---


### Architectur
![Pasted image 20240429164626.png](/img/user/Files/Pasted%20image%2020240429164626.png)


### Feed forward


### Encoder

The encoder's role is to process and represent the input sequence (such as a sentence or a paragraph) in a meaningful way. It consists of multiple identical layers, each comprising two sub-layers:

1. A self-attention layer that helps the Transformer identify relationships between words in the input sequence and understand their relative importance.
    
2. A fully connected feed-forward network that performs additional processing on the input data.
    

The encoder takes the input sequence, processes it through multiple self-attention and feed-forward layers, and generates a "hidden" representation of the input sequence. This hidden representation captures the contextual information and meaning of the input sequence.

#### Example
1. takes the English words: {this, is, Amazing}
2. Generates then the embeddings for every word
3. similar words have closer numbers in their vectors

summary: The encoder learns what is english, what is grammar and what is context.

### Decoder

The decoder's role is to generate an output sequence (such as a translation or summary) based on the hidden representation produced by the encoder. It also consists of multiple identical layers, each comprising three sub-layers:

1. A self-attention layer that processes the output sequence generated so far.
    
2. An encoder-decoder attention layer that uses the encoder's hidden representation to understand the input sequence better.
    
3. A fully connected feed-forward network that performs additional processing on the input data.
    

The decoder starts with a "start-of-sequence" token and iteratively generates the output sequence, one token at a time. It uses the encoder's hidden representation to understand the input sequence and generate an output sequence that accurately reflects the meaning of the input sequence.


#### Example 
1. The Decoder takes the Embeddings from the Encoder and the previous already generated words translated words like french from the output.
2. With this Words knowledge combined it predicts know the next French word.
3. This happens in a loop one word at the time until the end of the sentence is reached.

summary: The decoder learns how english words relate to french words.

##### Single headed Attention
![Pasted image 20240429164445.png](/img/user/Files/Pasted%20image%2020240429164445.png)



##### Multiheaded headed Attention
![Pasted image 20240602144206.png](/img/user/Files/Pasted%20image%2020240602144206.png)


### Attention

![Pasted image 20240602143919.png](/img/user/Files/Pasted%20image%2020240602143919.png)

- words that are not colored are masked to zero

![Pasted image 20240602145409.png](/img/user/Files/Pasted%20image%2020240602145409.png)


#### Query Vector

#### Key Vector

#### Value Vector





### Vergleich zu anderen DLN

#### LSTM: 
- Much faster because it takes it simultaneously
- Words are passed in sequential
- Not truly Bidirectional

#### GRU

#### Seq2Seq


#### Attenation in Transformers
![Pasted image 20240602145135.png](/img/user/Files/Pasted%20image%2020240602145135.png)

the yellow one 512 dimensons vector doesnt have any context awarenss whiel the green ones has cause of the multiheaded attention


