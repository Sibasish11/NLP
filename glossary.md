# Glossary

A running list of key NLP terms encountered across the course, in
alphabetical order. Add a `(Week N)` tag so you can trace a term back to
where it was introduced.

---

### A

**Ambiguity** — When a linguistic unit (word, phrase, sentence) has more
than one possible interpretation. Occurs at lexical, syntactic, semantic,
and pragmatic levels. *(Week 1)*

### B

**Backpropagation** — Algorithm for computing gradients of the loss with
respect to network parameters via the chain rule, used to train neural
models including embeddings. *(Week 7)*

**Backpropagation Through Time (BPTT)** — Extension of backpropagation for
recurrent networks; unrolls the RNN across time steps to compute gradients. *(Week 8)*

**Bigram** — A sequence of two consecutive words/tokens, used to estimate
`P(wi | wi-1)` in n-gram language models. *(Week 3)*

### C

**CBOW (Continuous Bag of Words)** — Word2Vec architecture that predicts a
center word from its surrounding context words. *(Week 6)*

**Chomsky Normal Form (CNF)** — A CFG form where every rule is either
`A -> B C` or `A -> a`; required for the CYK parsing algorithm. *(Week 5)*

**Context-Free Grammar (CFG)** — A set of production rules defining valid
syntactic structures for a language, independent of context. *(Week 5)*

**Corpus** — A large, structured collection of text used for training or
evaluating NLP models.

**CYK Algorithm** — Dynamic programming algorithm for parsing sentences
using a CFG in Chomsky Normal Form. *(Week 5)*

### D

**Dependency Parsing** — Syntactic analysis that represents grammatical
structure as directed head-dependent relations between words, rather than
nested phrases. *(Week 5)*

**Discourse** — The level of linguistic analysis concerned with meaning
across multiple sentences. *(Week 1)*

**Distributional Hypothesis** — The idea that words occurring in similar
contexts tend to have similar meanings ("you shall know a word by the
company it keeps"). *(Week 6)*

### E

**Edit Distance (Levenshtein Distance)** — Minimum number of insertions,
deletions, and substitutions needed to transform one string into another. *(Week 2)*

**Emission Probability** — In an HMM, the probability of observing a word
given a hidden tag: `P(wi | ti)`. *(Week 4)*

### G

**GloVe (Global Vectors)** — Word embedding method that trains vectors
directly on global word co-occurrence statistics. *(Week 6)*

**Good-Turing Smoothing** — Smoothing technique that re-estimates counts
based on the frequency of frequencies, giving unseen events a non-zero
probability. *(Week 3)*

**GRU (Gated Recurrent Unit)** — Simplified recurrent unit with update and
reset gates, an alternative to LSTM with fewer parameters. *(Week 8)*

### H

**Hidden Markov Model (HMM)** — A statistical model with hidden states
(e.g., POS tags) generating observed outputs (e.g., words), used for
sequence labeling tasks like POS tagging. *(Week 4)*

### K

**Kneser-Ney Smoothing** — Advanced smoothing technique using continuation
probability; considered state-of-the-art among n-gram smoothing methods. *(Week 3)*

### L

**Laplace (Add-1) Smoothing** — Simplest smoothing technique; adds 1 to
every n-gram count to avoid zero probabilities. *(Week 3)*

**Lemmatization** — Reducing a word to its dictionary base form (lemma)
using vocabulary and morphological analysis. *(Week 2)*

**LSTM (Long Short-Term Memory)** — RNN variant with a separate cell state
and gating mechanisms (forget, input, output gates) that mitigate the
vanishing gradient problem. *(Week 8)*

### M

**Markov Assumption** — Simplifying assumption that the probability of the
next unit depends only on a limited number of preceding units, not the
entire history. *(Weeks 3, 4)*

**Maximum Likelihood Estimation (MLE)** — Estimating probabilities directly
from observed counts in a corpus, e.g. `P(wi | wi-1) = count(wi-1,wi)/count(wi-1)`. *(Week 3)*

**Morphology** — The study of word structure: stems, affixes, inflection,
and derivation. *(Weeks 1, 2)*

### N

**N-gram** — A contiguous sequence of n words/tokens, the basic unit of
classical language models. *(Week 3)*

**Named Entity Recognition (NER)** — Task of identifying and classifying
named entities (people, organizations, locations, etc.) in text.

**Negative Sampling** — Training trick for Word2Vec that turns softmax
prediction into binary classification against a small number of sampled
"negative" words, making training tractable. *(Week 6)*

### P

**Penn Treebank Tagset** — Widely used set of ~45 POS tags (NN, VB, JJ,
DT, etc.). *(Week 4)*

**Perplexity** — Intrinsic evaluation metric for language models; the
inverse probability of the test set normalized by length. Lower is better. *(Week 3)*

**PCFG (Probabilistic CFG)** — A CFG where each production rule has an
associated probability, used to rank competing parses. *(Week 5)*

**Pragmatics** — The level of linguistic analysis concerned with meaning in
context — real-world knowledge and speaker intent. *(Week 1)*

**Porter Stemmer** — Classic rule-based algorithm for stemming English
words by stripping suffixes in a cascade of rules. *(Week 2)*

### S

**Semantics** — The level of linguistic analysis concerned with the meaning
of words and sentences. *(Week 1)*

**Skip-gram** — Word2Vec architecture that predicts context words from a
given center word. *(Week 6)*

**Smoothing** — Techniques for redistributing probability mass to unseen
n-grams so the model never assigns zero probability. *(Week 3)*

**Stemming** — Crude, rule-based chopping of word affixes to approximate a
common root form. *(Week 2)*

**Syntax** — The level of linguistic analysis concerned with the
grammatical structure of sentences. *(Week 1)*

### T

**Tokenization** — Splitting text into meaningful units (tokens), typically
words or subwords. *(Week 2)*

**Transition Probability** — In an HMM, the probability of moving from one
hidden state (tag) to another: `P(ti | ti-1)`. *(Week 4)*

**Trigram** — A sequence of three consecutive words/tokens. *(Week 3)*

### V

**Vanishing/Exploding Gradient Problem** — Phenomenon where gradients
shrink toward zero or grow unboundedly across many time steps in RNNs,
making it hard to learn long-range dependencies. *(Week 8)*

**Viterbi Algorithm** — Dynamic programming algorithm for finding the most
probable hidden state sequence in an HMM efficiently, avoiding brute-force
enumeration. *(Week 4)*

### W

**Word2Vec** — Family of shallow neural network models (CBOW, Skip-gram)
that learn dense word embeddings by predicting context from words or vice
versa. *(Week 6)*

---

## 📝 Notes on Maintaining This File

- Add new terms as you progress through later weeks — keep alphabetical order.
- Tag each entry with `(Week N)` so you can trace it back to its source notes.
- If a term evolves in meaning across weeks (e.g., "attention" will show up
  again more prominently once Transformers are covered), just extend the
  existing entry rather than duplicating it.
