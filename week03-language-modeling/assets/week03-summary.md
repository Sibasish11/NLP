# Week 3 — Summary

**One-line takeaway:** Language models assign probabilities to word sequences using n-gram counts, but raw counts fail on unseen data — smoothing is what makes them usable.

## Must-know concepts
- A language model assigns P(w1, w2, ..., wn) to a word sequence.
- N-gram models approximate the chain rule using the Markov assumption (look back only n-1 words).
- MLE estimates probabilities directly from corpus counts.
- Smoothing redistributes probability mass to unseen n-grams: Laplace (Add-1), Add-k, Good-Turing, Kneser-Ney (best in practice).
- Perplexity is the standard intrinsic evaluation metric — lower is better.

## Key formulas
- Bigram probability (MLE): `P(wi | wi-1) = count(wi-1, wi) / count(wi-1)`
- Perplexity: `PP(W) = P(w1, w2, ..., wN) ^ (-1/N)`

## Common pitfalls / gotchas
- Without smoothing, a single unseen bigram makes the entire sentence probability zero.
- Lower perplexity doesn't always mean better performance on a downstream task — it's an intrinsic, not extrinsic, metric.
- Higher-order n-grams (trigram+) capture more context but suffer worse data sparsity.

## If you only remember one thing
> Smoothing exists solely to prevent zero probabilities from unseen n-grams — pick Kneser-Ney if you need the strongest classical approach.
