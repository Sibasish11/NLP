# Week 4 — Summary

**One-line takeaway:** POS tagging is a sequence labeling problem where HMMs model tag transitions and word emissions, and Viterbi finds the best tag sequence efficiently.

## Must-know concepts
- POS tagging assigns grammatical categories (noun, verb, etc.) based on context, not word identity alone.
- Penn Treebank tagset is the standard (~45 tags: NN, VB, JJ, DT, etc.).
- Approaches: rule-based (hand-written rules/lexicon), HMM (stochastic), MaxEnt/CRF (discriminative), neural (later weeks).
- HMM finds T* = argmax P(T|W) using transition probabilities P(ti|ti-1) and emission probabilities P(wi|ti).
- Viterbi algorithm finds the optimal tag sequence via dynamic programming, avoiding exponential brute force.

## Key formulas
- HMM decomposition: `T* = argmax P(W|T) · P(T)`
- Transition probability: `P(ti | ti-1) = count(ti-1, ti) / count(ti-1)`
- Emission probability: `P(wi | ti) = count(wi, ti) / count(ti)`
- Viterbi complexity: O(N·T²) — N = sentence length, T = number of tags

## Common pitfalls / gotchas
- The same word can take different tags depending on context ("book" as noun vs. verb) — this is exactly what makes tagging non-trivial.
- Don't confuse transition probability (tag→tag) with emission probability (tag→word) — they model different things in the HMM.
- Brute-force enumeration of tag sequences is exponential; Viterbi's DP trick is what makes HMM tagging practical.

## If you only remember one thing
> POS tagging is about finding the most probable sequence of hidden tags given observed words — Viterbi is the algorithm that makes this tractable.
