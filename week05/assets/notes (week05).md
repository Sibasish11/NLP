# Week 5: Syntactic Parsing

**Course:** NPTEL - Natural Language Processing
**Week:** 5
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- Context-Free Grammars (CFG)
- Constituency vs. dependency parsing
- CYK (Cocke-Younger-Kasami) parsing algorithm
- Probabilistic CFGs (PCFG)
- Dependency parsing basics (transition-based, graph-based)

---

## 1. Context-Free Grammars

A CFG defines valid sentence structures using production rules:

```
S  -> NP VP
NP -> DT NN | NNP
VP -> VBZ NP
```

Example derivation for "The dog chases cats":
```
S -> NP VP -> DT NN VP -> "The" NN VP -> "The" "dog" VBZ NP -> ...
```

---

## 2. Constituency vs. Dependency Parsing

| Aspect | Constituency Parsing | Dependency Parsing |
|---|---|---|
| Structure | Nested phrases (NP, VP, ...) | Word-to-word head-dependent links |
| Output | Parse tree with non-terminal nodes | Directed graph/tree over words |
| Grammar | Based on CFG | Based on grammatical relations (subject, object, etc.) |
| Common in | Formal grammar analysis | Modern NLP pipelines (faster, more direct for downstream tasks) |

---

## 3. CYK Algorithm

Dynamic programming algorithm for parsing with a CFG in **Chomsky Normal
Form (CNF)** — every rule is either `A -> B C` or `A -> a`.

- Builds a table where `cell[i][j]` holds the set of non-terminals that can
  generate the substring spanning positions i to j
- Bottom-up: combines smaller spans into larger ones
- Runs in O(n³ · |G|) time — n = sentence length, |G| = grammar size

---

## 4. Probabilistic CFG (PCFG)

Attaches probabilities to each production rule so multiple valid parses can
be ranked:

```
P(tree) = Π P(rule used at each node)
```

Used to pick the **most likely parse** among many grammatically valid ones —
resolves structural ambiguity (e.g., PP-attachment: "I saw the man with the
telescope").

---

## 5. Dependency Parsing Approaches

| Approach | Idea |
|---|---|
| Transition-based | Build the parse via a sequence of shift/reduce actions (like a stack-based parser), e.g., arc-standard |
| Graph-based | Score all possible arcs, find the maximum spanning tree (e.g., Eisner's algorithm, MST parsing) |

---

## 🧠 Key Takeaways

- CFGs formalize sentence structure but suffer from ambiguity without probabilities.
- CYK is the classic algorithm for CFG parsing but requires CNF conversion.
- Dependency parsing is more directly useful for many downstream NLP tasks
  (relation extraction, information extraction) since it captures head-dependent
  relations explicitly.

---

## ❓ Open Questions / To Revisit

- [ ] Convert a small CFG to Chomsky Normal Form by hand
- [ ] Run CYK on a toy sentence and trace the table fill

---

## 🔗 Related Files

- [references.md](./references.md)
- [assets/](./assets/)
- [../code/week05_cyk_parser.ipynb](../code/week05_cyk_parser.ipynb)
