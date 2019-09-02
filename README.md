Play with Google's Universal Sentence Encoder
---------------------------------------------

Universal Embeddings: embeddings that are pre-trained on a large
corpus and can be plugged in a variaety of downstream task models.

The [Universal Sentence Encoder](https://tfhub.dev/google/universal-sentence-encoder/2) encodes text into high-dimensional vectors that can be used for 
text classification, semantic similarity, clustering and other natural language tasks.

**Multi-task learning:** combine several training objectives in one training schema thus better generalized on downstream tasks.


![Recent trend in Universal Word/Sentence Embeddings](https://miro.medium.com/max/4620/1*ZZrMm_-SnUhATja5a_z7tg.png)

## Wird Enbed.
- **Wrd2vec / Glove:** Context independent - the one numeric representation of a word regardless of where the words occurs in a sentence. Input is words and output word embeddings.
- **ELMo and BERT:** Context dependent - generate different word embeddings for a word that captures the context of a word.
    - ELMo is a character based model thus able to handle out-of-vocabulary words.
    - BERT input is subwords - it strikes a balance between character based and word based representations. Handles OOV.
- **FastText vectors:** Imporved version of word2vec. The improvement is that inclusion of character n-grams, which allows computing word representations for words that did not appear in the training data. It is available in 157 languages.


Reference: 
https://medium.com/huggingface/universal-word-sentence-embeddings-ce48ddc8fc3a