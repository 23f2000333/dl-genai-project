# DL-GENAI-PROJECT
# Smart MCQ Solver Challenge

Name: Mrinal Pandey
Roll No: 23f2000333

## Overview

This repository contains my solution for the Kaggle **Smart MCQ Solver Challenge**, where the objective is to predict the **Top-3 most likely answers** for multiple-choice questions using Large Language Models and parameter-efficient fine-tuning.

The competition is evaluated using **Mean Average Precision @ 3 (MAP@3)**.

---

## Competition

- Dataset: Smart MCQ Solver Challenge
- Training Samples: 2,000
- Test Samples: 500
- Evaluation Metric: MAP@3

Each question contains:

- Prompt
- Five options (A-E)

The objective is to rank the three most probable answers.

---

# Model

Base Model

- Qwen2.5-3B-Instruct

Fine Tuning

- LoRA
- 4-bit Quantization (QLoRA)
- HuggingFace TRL SFTTrainer

---

# Training Configuration

| Parameter | Value |
|-----------|------|
| Model | Qwen2.5-3B-Instruct |
| Fine-tuning | LoRA |
| Precision | 4-bit |
| Epochs | 2 |
| Learning Rate | 2e-4 |
| Optimizer | PagedAdamW8bit |

---

# Inference Pipeline

The inference pipeline evolved over multiple experiments.

## Version 1

- First-token logits
- Softmax over A-E

Leaderboard Score

**0.62427**

---

## Version 2

Generation-based inference

Prompt engineering with deterministic decoding.

Leaderboard Score

**0.72402**

---

## Version 3

Beam Search + Prompt Ranking

Improvements

- Beam Search
- Prompt Optimization
- Ranked option generation
- Beam reranking

Leaderboard Score

**0.73316**

---

# Repository Structure

```
smart-mcq-solver/

checkpoints/
docs/
notebooks/
submissions/

README.md
requirements.txt
.gitignore
```

---

# Results

| Method | Public MAP@3 |
|---------|-------------|
| Initial LoRA | 0.62427 |
| Generation Inference | 0.72402 |
| Beam Search + Ranking | **0.73316** |

---

# Future Work

- Retrieval-Augmented Generation (RAG)
- Cross-Encoder Re-ranking
- DistilBERT Baseline
- Ensemble Models
- Prompt Ensembling
- Self-consistency decoding

---

# Author

Mrinal Pandey
