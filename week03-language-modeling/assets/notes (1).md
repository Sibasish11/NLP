# Week 3: Language Modeling (N-grams)

**Course:** NPTEL - Natural Language Processing
**Week:** 3
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- What is a language model?
- N-gram models (unigram, bigram, trigram)
- Estimating probabilities with Maximum Likelihood
- Smoothing techniques (Laplace, Add-k, Good-Turing, Kneser-Ney)
- Perplexity as an evaluation metric
- Sparsity problem & out-of-vocabulary words

---

## 1. What is a Language Model?

A language model assigns a probability to a sequence of words:

```
P(w1, w2, ..., wn)
```

Used for: speech recognition, machine translation, autocomplete, spelling
correction — anywhere you need to judge "how likely is this sentence."

---

## 2. N-gram Models

Chain rule of probability:

```
P(w1...wn) = P(w1) · P(w2|w1) · P(w3|w1,w2) · ... · P(wn|w1...wn-1)
```

The **Markov assumption** simplifies this — an n-gram model only looks back
`n-1` words:

| Model | Approximation |
|---|---|
| Unigram | P(wi) |
| Bigram | P(wi \| wi-1) |
| Trigram | P(wi \| wi-2, wi-1) |

**MLE estimate** for a bigram:

```
P(wi | wi-1) = count(wi-1, wi) / count(wi-1)
```

---

## 3. Smoothing

Raw MLE gives **zero probability** to unseen n-grams, which is a problem
since it makes the whole sentence probability zero. Smoothing redistributes
probability mass to unseen events.

| Technique | Idea |
|---|---|
| Laplace (Add-1) | Add 1 to every count | simplest, often over-smooths |
| Add-k | Add fractional k instead of 1 | tunable, still crude |
| Good-Turing | Re-estimate counts using frequency-of-frequencies | more principled |
| Kneser-Ney | Uses continuation probability, considered state-of-the-art for n-grams | most commonly used in practice |

---

## 4. Perplexity

Standard intrinsic evaluation metric for language models — inverse
probability of the test set, normalized by number of words:

```
PP(W) = P(w1, w2, ..., wN) ^ (-1/N)
```

**Lower perplexity = better model** (model is less "surprised" by the test data).

---

## 🧠 Key Takeaways

- N-gram models trade off context length vs. data sparsity.
- Smoothing is essential — without it, unseen n-grams break the model.
- Perplexity lets you compare language models on the same test set, but doesn't
  guarantee better downstream task performance.

---

## ❓ Open Questions / To Revisit

- [ ] Work through Good-Turing re-estimation by hand on a toy corpus
- [ ] Understand why Kneser-Ney's continuation probability outperforms simple backoff

---

## 🔗 Related Files

- [references.md](./references.md)
- [assets/](./assets/)
- [../code/week03_ngram_lm.ipynb](../code/week03_ngram_lm.ipynb)
