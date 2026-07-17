# Model Architectures

## Model 1 — BiLSTM

```
Input Text

↓

Embedding Layer

↓

Bidirectional LSTM

↓

Dropout

↓

Linear Layer

↓

Softmax

↓

Answer (A–E)
```

---

## Model 2 — Cross Encoder

```
Question

+

Candidate Option

↓

CrossEncoder

↓

Relevance Score

↓

Ranking
```

---

## Model 3 — Qwen LoRA

```
Prompt

↓

Qwen2.5-7B-Instruct

↓

LoRA Adapter

↓

Logit Scoring

↓

Circular Permutations

↓

Top-3 Prediction
```
