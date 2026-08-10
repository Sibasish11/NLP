# Week 7: Neural Networks for NLP

**Course:** NPTEL - Natural Language Processing
**Week:** 7
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- Feedforward neural networks recap
- Why NLP moved from feature engineering to neural representations
- Neural language models
- Backpropagation refresher in the context of NLP
- Using pretrained embeddings as input features

---

## 1. From Feature Engineering to Representation Learning

Traditional NLP pipelines (Weeks 1-5) relied heavily on hand-crafted
features (n-grams, POS tags, parse structures). Neural approaches instead
**learn representations directly from data**, reducing manual feature
engineering.

---

## 2. Feedforward Neural Network Recap

A basic FFN:

```
h = activation(W1 · x + b1)
y = softmax(W2 · h + b2)
```

- `x` — input vector (e.g., concatenated word embeddings)
- `h` — hidden layer representation
- `y` — output distribution over classes/vocabulary

**Common activations:** ReLU, tanh, sigmoid
**Loss for classification:** cross-entropy

---

## 3. Neural Language Models (Bengio et al., 2003)

Predicts the next word using a fixed-size context window of previous words,
each represented as an embedding, concatenated and fed through an FFN:

```
P(wt | wt-n+1 ... wt-1) = softmax(FFN(embed(wt-n+1), ..., embed(wt-1)))
```

**Advantages over n-gram LMs:**
- Learns smooth, continuous representations (no sparsity problem)
- Generalizes to unseen n-grams via similarity in embedding space

**Limitation:** fixed context window — motivates RNNs (Week 8).

---

## 4. Backpropagation in NLP Context

Same chain-rule-based gradient computation as standard neural nets, but
gradients also flow back into the **embedding matrix**, meaning embeddings
get fine-tuned during training rather than staying static.

```
∂Loss/∂embedding(wi) — updates the specific word's vector based on
how it contributed to the prediction error
```

---

## 5. Using Pretrained Embeddings

Two common strategies when building an NLP model:

| Strategy | Description |
|---|---|
| Static | Load pretrained embeddings (Word2Vec/GloVe), freeze them during training |
| Fine-tuned | Initialize with pretrained embeddings, allow gradients to update them |

Fine-tuning often helps when there's enough task-specific data; frozen
embeddings help avoid overfitting on small datasets.

---

## 🧠 Key Takeaways

- Neural networks let NLP models learn representations instead of relying purely on hand-crafted features.
- Neural language models solve the sparsity problem of n-grams but are still limited by a fixed context window.
- Embeddings can be treated as learnable parameters, fine-tuned jointly with the rest of the network.

---

## ❓ Open Questions / To Revisit

- [ ] Implement Bengio's neural LM on a toy dataset
- [ ] Compare frozen vs. fine-tuned embeddings on a small classification task

---

## 🔗 Related Files

- [references.md](./references.md)
- [assets/](./assets/)
- [../code/week07_neural_lm.ipynb](../code/week07_neural_lm.ipynb)
