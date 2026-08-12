# Week 2 — Summary

**One-line takeaway:** Before any NLP model can work with text, it must be broken into tokens and normalized — and even this "simple" step is full of edge cases.

## Must-know concepts
- Regex is the foundational tool for pattern-based text extraction and cleaning.
- Tokenization splits text into words/sentences; tricky cases include punctuation, clitics ("I'm"), and multi-word expressions.
- Stemming (rule-based, crude) vs. lemmatization (dictionary-based, accurate but needs more resources).
- Porter Stemmer is the classic rule-based stemming algorithm.
- Morphology: stem, affix, inflection (grammatical change, same category) vs. derivation (new word, often new category).
- Edit distance measures string dissimilarity — used in spelling correction, fuzzy matching, alignment.

## Key formulas
- Levenshtein edit distance (dynamic programming):
```
dist(i,j) = min(
    dist(i-1,j) + 1,        # deletion
    dist(i,j-1) + 1,        # insertion
    dist(i-1,j-1) + cost    # substitution (0 if match, else 1)
)
```

## Common pitfalls / gotchas
- Sentence segmentation isn't just "split on period" — abbreviations like "Dr." break naive rules.
- Stemming can over-chop words to non-words (e.g., "studies" → "studi"); lemmatization avoids this but is slower and needs POS info.
- Don't confuse inflection (walk → walked, same category) with derivation (happy → happiness, category change).

## If you only remember one thing
> Tokenization and normalization decisions made in Week 2 quietly affect every downstream NLP step — get them wrong and everything after inherits the error.
