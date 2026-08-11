# Week 8: RNNs, LSTMs & GRUs

**Course:** NPTEL - Natural Language Processing
**Week:** 8
**Status:** ✅ Completed / 🔲 In progress *(update as you go)*

---

## 📌 Topics Covered

- Limitations of fixed-window neural language models
- Recurrent Neural Networks (RNN)
- Vanishing/exploding gradient problem
- Long Short-Term Memory (LSTM)
- Gated Recurrent Units (GRU)
- Sequence modeling applications (tagging, language modeling)

---

## 1. Why RNNs?

Feedforward neural LMs (Week 7) use a fixed context window. RNNs instead
maintain a **hidden state** that is updated at every time step, theoretically
allowing them to condition on the entire preceding sequence:

```
ht = activation(Wx · xt + Wh · h(t-1) + b)
yt = softmax(Wy · ht + by)
```

The hidden state `ht` acts as a compressed summary of everything seen so far.

---

## 2. Vanishing / Exploding Gradients

Because the same weight matrix is applied repeatedly across time steps,
gradients during backpropagation-through-time (BPTT) can shrink toward zero
(vanishing) or grow unboundedly (exploding) over long sequences.

**Effect:** vanilla RNNs struggle to learn long-range dependencies.

**Partial fixes:** gradient clipping (for exploding), but vanishing
gradients need an architectural solution — LSTMs/GRUs.

---

## 3. LSTM (Long Short-Term Memory)

Introduces a separate **cell state** (`Ct`) that flows through time with
minimal transformation, plus gates that control information flow:

| Gate | Purpose |
|---|---|
| Forget gate | Decides what to discard from the cell state |
| Input gate | Decides what new information to add |
| Output gate | Decides what part of the cell state to expose as output |

```
ft = σ(Wf · [h(t-1), xt] + bf)      # forget gate
it = σ(Wi · [h(t-1), xt] + bi)      # input gate
Ct~ = tanh(Wc · [h(t-1), xt] + bc)  # candidate values
Ct = ft * C(t-1) + it * Ct~          # updated cell state
ot = σ(Wo · [h(t-1), xt] + bo)      # output gate
ht = ot * tanh(Ct)
```

The gating mechanism allows gradients to flow more easily across many time
steps, mitigating vanishing gradients.

---

## 4. GRU (Gated Recurrent Unit)

A simplified alternative to LSTM — merges the forget and input gates into a
single **update gate**, and combines cell state and hidden state:

| Gate | Purpose |
|---|---|
| Update gate | Balances how much of the past to keep vs. new info |
| Reset gate | Controls how much past info to forget when computing candidate state |

**GRU vs. LSTM:** fewer parameters, often trains faster, comparable
performance on many tasks — but LSTM can still edge out on tasks needing
finer-grained memory control.

---

## 5. Applications in NLP

- **Language modeling** — predict next word using full history, not fixed window
- **Sequence tagging** — POS tagging, NER using BiLSTM (processes sequence both forward and backward)
- **Sequence-to-sequence** — encoder-decoder RNNs for machine translation, summarization (sets up Week 9: Attention)

---

## 🧠 Key Takeaways

- RNNs process sequences step-by-step, maintaining a hidden state — a
  conceptual leap over the fixed-window neural LM.
- Vanilla RNNs suffer from vanishing gradients, limiting how far back they can
  "remember."
- LSTM/GRU gating mechanisms are the standard fix, enabling much longer
  effective memory.

---

## ❓ Open Questions / To Revisit

- [ ] Derive why vanilla RNN gradients vanish (multiply Jacobians across time steps)
- [ ] Implement a character-level LSTM language model on a small text corpus

---

## 🔗 Related Files

- [references.md](./references.md)
- [assets/](./assets/)
- [../code/week08_lstm_language_model.ipynb](../code/week08_lstm_language_model.ipynb)
