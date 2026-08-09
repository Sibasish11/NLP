# Week 4: Part-of-Speech Tagging

**Course:** NPTEL - Natural Language Processing
**Week:** 4
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- What is POS tagging and why it matters
- Tagsets (Penn Treebank tagset)
- Rule-based vs. stochastic taggers
- Hidden Markov Models (HMM) for tagging
- Viterbi algorithm
- Evaluation of taggers

---

## 1. What is POS Tagging?

Assigning a grammatical category (noun, verb, adjective, etc.) to each word
in a sentence, based on both its definition and its context.

```
"The/DT dog/NN barks/VBZ loudly/RB"
```

Ambiguity is the core challenge: **"book"** can be a noun ("read a book") or
verb ("book a flight") — context decides.

---

## 2. Tagsets

The **Penn Treebank tagset** is the most widely used (~45 tags), e.g.:

| Tag | Meaning | Example |
|---|---|---|
| NN | Singular noun | dog |
| NNS | Plural noun | dogs |
| VB | Verb, base form | run |
| VBZ | Verb, 3rd person singular present | runs |
| JJ | Adjective | quick |
| DT | Determiner | the |
| IN | Preposition | in, of, on |

---

## 3. Approaches to Tagging

| Approach | Idea |
|---|---|
| Rule-based | Hand-written rules + lexicon (e.g. Brill tagger uses transformation rules) |
| HMM (stochastic) | Models tag sequence as a Markov chain, words as emissions |
| Maximum Entropy / CRF | Discriminative models using rich features |
| Neural (BiLSTM, etc.) | Learns representations directly, covered in later weeks |

---

## 4. Hidden Markov Model for POS Tagging

Goal: find the most likely tag sequence `T` given a word sequence `W`.

```
T* = argmax P(T|W) = argmax P(W|T) · P(T)
```

Using Markov + independence assumptions:

```
P(T) ≈ Π P(ti | ti-1)          — transition probabilities
P(W|T) ≈ Π P(wi | ti)          — emission probabilities
```

**Transition probability:** `P(ti | ti-1) = count(ti-1, ti) / count(ti-1)`
**Emission probability:** `P(wi | ti) = count(wi, ti) / count(ti)`

---

## 5. Viterbi Algorithm

Dynamic programming algorithm to efficiently find the most probable tag
sequence, avoiding brute-force enumeration of all possible tag sequences
(which grows exponentially with sentence length).

- Builds a trellis of (word, tag) states
- At each step keeps only the best path leading to each state
- Backtrack from the final state to recover the optimal tag sequence

---

## 🧠 Key Takeaways

- POS tagging is a **sequence labeling** problem — context matters more than
  the word in isolation.
- HMMs formalize tagging as finding the most probable hidden state sequence
  given observations (words).
- Viterbi makes this tractable in O(N·T²) instead of exponential time.

---

## ❓ Open Questions / To Revisit

- [ ] Trace through Viterbi by hand on a 4-5 word sentence
- [ ] Compare HMM tagger accuracy vs. NLTK's default tagger on a sample text

---

## 🔗 Related Files

- [references.md](./references.md)
- [assets/](./assets/)
- [../code/week04_hmm_pos_tagger.ipynb](../code/week04_hmm_pos_tagger.ipynb)
