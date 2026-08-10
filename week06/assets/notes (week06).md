# Week 6: Distributional Semantics & Word Embeddings

**Course:** NPTEL - Natural Language Processing
**Week:** 6
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- Distributional hypothesis
- Count-based vs. prediction-based representations
- Word2Vec (CBOW and Skip-gram)
- Negative sampling & hierarchical softmax
- GloVe
- Evaluating word embeddings

---

## 1. Distributional Hypothesis

> "You shall know a word by the company it keeps." — J.R. Firth

Words that occur in similar contexts tend to have similar meanings. This is
the foundation for representing words as vectors derived from their
co-occurrence patterns.

---

## 2. Count-based Methods (Recap)

- **Co-occurrence matrix** — rows/columns are words, cells are co-occurrence counts within a window
- **TF-IDF weighting** — down-weights very common words
- **Dimensionality reduction** (e.g. SVD / LSA) — compresses sparse co-occurrence vectors into dense ones

These pre-date neural embeddings but share the same core intuition.

---

## 3. Word2Vec

Predicts context from words (or vice versa) using a shallow neural network,
producing dense low-dimensional word vectors as a byproduct of training.

| Architecture | Predicts |
|---|---|
| **CBOW** (Continuous Bag of Words) | Center word from surrounding context words |
| **Skip-gram** | Context words from the center word |

Skip-gram tends to work better for infrequent words; CBOW trains faster.

**Training objective (Skip-gram):**
```
maximize Σ Σ log P(w(t+j) | w(t))    for j in window, j != 0
```

---

## 4. Making Training Tractable

Computing the full softmax over the vocabulary is expensive. Two common fixes:

| Technique | Idea |
|---|---|
| Negative Sampling | Turn it into a binary classification: real context word vs. sampled "negative" words |
| Hierarchical Softmax | Represent vocabulary as a binary tree, reducing complexity to O(log V) |

---

## 5. GloVe (Global Vectors)

Combines the intuitions of count-based and prediction-based methods —
trains word vectors directly on **global co-occurrence statistics** rather
than local context windows, optimizing:

```
J = Σ f(Xij) (wi·wj + bi + bj − log Xij)²
```

where `Xij` is the co-occurrence count of words i and j.

---

## 6. Evaluating Word Embeddings

- **Intrinsic:** word similarity tasks, analogy tasks (`king - man + woman ≈ queen`)
- **Extrinsic:** performance on downstream tasks (NER, sentiment analysis, etc.) when embeddings are used as features

---

## 🧠 Key Takeaways

- Word embeddings turn the distributional hypothesis into dense, trainable vector representations.
- Skip-gram/CBOW are prediction-based; GloVe is a hybrid using global co-occurrence statistics directly.
- Analogy tasks (`vec(king) - vec(man) + vec(woman) ≈ vec(queen)`) are a striking demonstration of the linear structure embeddings capture.

---

## ❓ Open Questions / To Revisit

- [ ] Train a small Word2Vec model on a toy corpus and inspect nearest neighbors
- [ ] Compare GloVe vs. Word2Vec vectors on the same analogy test set

---

## 🔗 Related Files

- [references.md](./references.md)
- [assets/](./assets/)
- [../code/week06_word2vec.ipynb](../code/week06_word2vec.ipynb)
