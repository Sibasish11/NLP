# Week 2: Text Processing & Tokenization

**Course:** NPTEL - Natural Language Processing
**Week:** 2
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- Regular expressions for text processing
- Tokenization (word & sentence level)
- Word normalization (case folding, stemming, lemmatization)
- Edit distance
- Morphology: stems, affixes, inflection vs. derivation
- Basics of n-grams (leading into Week 3)

---

## 1. Regular Expressions

Regex is the first tool for pattern-based text processing — useful for search,
cleaning, and simple extraction tasks before moving to statistical methods.

Common patterns:

| Pattern | Meaning |
|---|---|
| `.` | any character |
| `*` | zero or more of preceding |
| `+` | one or more of preceding |
| `?` | zero or one of preceding |
| `[abc]` | any one of a, b, c |
| `[^abc]` | any character except a, b, c |
| `\d`, `\w`, `\s` | digit, word character, whitespace |
| `^`, `$` | start / end of line |

> 📝 *Add specific regex examples from the lecture (e.g. matching emails, dates).*

---

## 2. Tokenization

Splitting text into meaningful units (tokens) — usually words or subwords.

**Challenges:**
- Punctuation handling: `"U.S.A."`, `"don't"`, `"Mr. Smith"`
- Language-specific issues: no whitespace in Chinese/Japanese
- Clitics: `"I'm"` → `"I"` + `"'m"`
- Multi-word expressions: `"New York"`, `"ice cream"`

**Sentence segmentation** — deciding where a sentence ends (periods are
ambiguous: `"Dr."` vs. end of sentence).

---

## 3. Word Normalization

| Technique | Description | Example |
|---|---|---|
| Case folding | Lowercase everything | "The" → "the" |
| Stemming | Crude chopping of affixes (rule-based) | "studies" → "studi" |
| Lemmatization | Reduce to dictionary base form (uses vocabulary + morphology) | "studies" → "study" |

**Porter Stemmer** — classic rule-based stemming algorithm covered as the
standard example.

---

## 4. Edit Distance

Measures how dissimilar two strings are — minimum number of insertions,
deletions, and substitutions to transform one string into another.

Used for:
- Spelling correction
- DNA sequence alignment
- Fuzzy string matching

**Levenshtein Distance** — most common edit distance metric, computed via
dynamic programming.

```
dist(i, j) = min(
    dist(i-1, j) + 1,        # deletion
    dist(i, j-1) + 1,        # insertion
    dist(i-1, j-1) + cost    # substitution (cost = 0 if chars match, else 1)
)
```

---

## 5. Morphology Basics

- **Stem** — core meaning-bearing unit of a word (e.g., "walk" in "walking")
- **Affix** — morpheme attached to a stem (prefix, suffix, infix, circumfix)
- **Inflection** — modifies word for grammatical purposes, doesn't change category
  (e.g., "walk" → "walked")
- **Derivation** — creates a new word, often changes category
  (e.g., "happy" → "happiness")

---

## 🧠 Key Takeaways

- Tokenization looks simple but has many edge cases language models must handle.
- Stemming is fast but crude; lemmatization is more accurate but needs more resources (dictionary/POS info).
- Edit distance is a foundational tool reused throughout NLP (alignment, correction, evaluation).

---

## ❓ Open Questions / To Revisit

- [ ] Implement Porter Stemmer by hand to understand the rule cascades
- [ ] Compare NLTK's stemmer vs. lemmatizer output on the same text

---

## 🔗 Related Files

- [references.md](./references.md) — papers, links, and further reading
- [assets/](./assets/) — diagrams and screenshots from lectures
- [../code/week02_tokenization.ipynb](../code/week02_tokenization.ipynb) — hands-on tokenization & edit distance code
