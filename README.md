# NPTEL - Natural Language Processing: Course Notes & Implementation
 
A structured, week-by-week documentation of the NPTEL *Natural Language
Processing* course — covering theory notes, worked derivations, reference
material, and hands-on implementations for every major topic from
tokenization through neural sequence models.
 
This repository is both a personal study log and a reusable reference for
anyone working through the same course or the broader NLP curriculum it
follows.
 
---
 
## About
 
| | |
|---|---|
| **Course** | NPTEL — Natural Language Processing |
| **Format** | 12-week video lecture series with weekly assignments |
| **Scope of this repo** | Structured notes, glossary, references, and code for each week |
| **Status** | In progress — updated as the course is completed |
 
The goal of this repository is not just to store notes, but to build a
coherent, navigable reference: each week stands alone with its own notes and
sources, while the glossary and code folders tie concepts together across
the full course.
 
---
 
## Repository Structure
 
```
nptel-nlp-notes/
├── README.md
├── LICENSE
├── glossary.md                          Cross-week glossary of key terms
├── resources.md                         External links, papers, books
│
├── week01-introduction-to-nlp/
│   ├── notes.md
│   ├── references.md
│   ├── assets/
│   └── slides/
├── week02-text-processing/
├── week03-language-modeling/
├── week04-pos-tagging/
├── week05-parsing/
├── week06-word-embeddings/
├── week07-neural-networks-for-nlp/
├── week08-rnn-lstm/
├── week09-.../
├── week10-.../
├── week11-.../
├── week12-.../
│
├── code/                                Jupyter notebooks, one or more per week
│   ├── week02_tokenization.ipynb
│   ├── week03_ngram_lm.ipynb
│   └── ...
│
├── assignments/                         Graded assignment questions and solutions
│   └── assignment1/
│
└── cheatsheets/                         Quick-reference sheets on specific subtopics
```
 
Each week folder follows a consistent format:
 
- **`notes.md`** — structured lecture notes with definitions, formulas, and worked examples
- **`references.md`** — papers, textbook chapters, and external resources cited or relevant to that week
- **`assets/`** — diagrams, screenshots, and figures
- **`slides/`** — lecture slide captures, where applicable
---
 
## Progress
 
| Week | Topic | Status |
|---|---|---|
| 01 | Introduction to NLP | Complete |
| 02 | Text Processing & Tokenization | Complete |
| 03 | Language Modeling (N-grams) | Complete |
| 04 | Part-of-Speech Tagging | Complete |
| 05 | Syntactic Parsing | Complete |
| 06 | Distributional Semantics & Word Embeddings | Complete |
| 07 | Neural Networks for NLP | Complete |
| 08 | RNNs, LSTMs & GRUs | Complete |
| 09 | Sequence-to-Sequence & Attention | Not started |
| 10 | Transformers | Not started |
| 11 | Pretrained Language Models (BERT and beyond) | Not started |
| 12 | Applications & Case Studies | Not started |
 
*Update this table as each week is completed.*
 
---
 
## Topics Covered
 
- Foundations of NLP and sources of linguistic ambiguity
- Text preprocessing: tokenization, normalization, stemming, lemmatization
- Statistical language modeling and smoothing techniques
- Part-of-speech tagging with Hidden Markov Models and the Viterbi algorithm
- Constituency and dependency parsing, including the CYK algorithm
- Distributional semantics and word embeddings (Word2Vec, GloVe)
- Neural network foundations for NLP tasks
- Recurrent architectures: RNN, LSTM, GRU
- *(Upcoming)* Attention mechanisms, Transformers, and pretrained language models
---
 
## Notes on Content
 
All notes are written in my own words while following the course's lecture
sequence and terminology. Formulas and algorithmic descriptions are included
for reference and revision, not as a substitute for watching the original
lectures. Where a concept draws directly on a specific paper or textbook,
that source is cited in the corresponding `references.md`.
 
---
 
## Glossary
 
[`glossary.md`](./glossary.md) maintains a running, alphabetized reference
of every key term introduced in the course, tagged with the week it first
appears in. Useful for quick lookups without digging through individual
week notes.
 
---
 
## Code
 
Hands-on implementations accompanying the notes live in [`code/`](./code),
organized as one notebook per week (or per major topic within a week).
These are meant to be run and modified, not just read — most include a
"try it yourself" section at the end.
 
**Primary stack:** Python, NLTK, spaCy, gensim, PyTorch
 
---
 
## Usage
 
Clone the repository and browse by week, or jump directly to a topic using
the structure above:
 
```bash
git clone https://github.com/<your-username>/nptel-nlp-notes.git
cd nptel-nlp-notes
```
 
To run the notebooks:
 
```bash
pip install -r requirements.txt
jupyter notebook code/
```
 
---
 
## Contributing
 
This is primarily a personal study repository, but corrections, better
explanations, or additional resources are welcome. Feel free to open an
issue or pull request if you spot an error or have a suggestion.
 
---
 
## License
 
This project is licensed under the [MIT License](./LICENSE). Course
content itself belongs to NPTEL and the respective instructors; these notes
are an independent, original summary intended for personal study and
reference.
 
---
 
## Acknowledgements
 
Based on the NPTEL *Natural Language Processing* course. All credit for the
underlying course content goes to the instructor(s) and NPTEL. This
repository reflects my own understanding and summarization of the material.
 
