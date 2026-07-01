# Experiment Log

| Run | Experiment | MAP@3 |
|------|-----------|-------|
| 1 | Initial LoRA + First Token Logits | 0.62427 |
| 2 | Generation-based Inference | 0.72402 |
| 3 | Beam Search + Prompt Ranking | **0.73316** |

---

## Experiment 1

Inference

First token logits

Observation

Model learned useful reasoning but inference strategy limited performance.

---

## Experiment 2

Generation based decoding

Improvement

+0.09975 MAP

---

## Experiment 3

Beam Search

Prompt Ranking

Beam Re-ranking

Improvement

+0.00914 MAP

---

Current Best Score

0.73316
