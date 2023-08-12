latent Dirichlet allocation
- peform topic detection on large document sets, determining what the main `topics` are in a large unlabeled set of texts. 

> A '`topic`' is a collection of words that tend to co-occur often.

LDA does not work directly on text data. First, it is necessary to convert the documents into a simple vector representation. This representation will then be used by LDA to determine the topics. Each entry of a 'document vector' will correspond with the number of times a word occurred in the document.

**In conclusion**, we will convert a list of titles into a list of vectors, all with length equal to the vocabulary. For example, _'Analyzing machine learning trends with neural networks.'_ would be transformed into `[1, 0, 1, ..., 1, 0]`.

**example**
```python3

```

