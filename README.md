# DL-GenAI Project
## Smart MCQ Solver Challenge

**Name:** Mrinal Pandey  
**Roll Number:** 23f2000333

---

## Project Overview

This repository contains my submission for the **Smart MCQ Solver Challenge** as part of the **Deep Learning for Generative AI** course.

The objective of the competition is to predict the **top three most likely answers** for multiple-choice questions containing a prompt and five answer options (A–E).

Model performance is evaluated using **Mean Average Precision at 3 (MAP@3)**.

---

## Dataset

- **Training Samples:** 2,000
- **Test Samples:** 500
- **Answer Choices:** A, B, C, D, E
- **Evaluation Metric:** MAP@3

Each sample consists of:

- Question Prompt
- Five Candidate Answers
- Correct Answer (Training Set)

The task is to rank the three most probable answer choices for every question.

---

## Repository Structure

```
DLGenAI-IITM/
│
├── docs/
├── notebooks/
├── checkpoints/
├── submissions/
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Models Implemented

### 1. BiLSTM (Built From Scratch)

A Bidirectional LSTM model implemented entirely in PyTorch using a custom vocabulary and embedding layer.

**Architecture**

```
Embedding
    ↓
BiLSTM
    ↓
Dropout
    ↓
Linear Layer
    ↓
Softmax
```

**Public MAP@3:** **0.74023**

---

### 2. CrossEncoder (Pretrained Model)

Model Used:

```
cross-encoder/ms-marco-MiniLM-L-6-v2
```

The model scores each question-answer pair independently and ranks the answer options according to their relevance.

**Public MAP@3:** **0.44887**

---

### 3. Qwen2.5 LoRA (Fine-Tuned LLM)

Base Model:

```
Qwen2.5-7B-Instruct
```

Fine-tuning Method:

- LoRA
- 4-bit Quantization (QLoRA)
- Hugging Face TRL SFTTrainer

The inference pipeline was improved over multiple experiments using prompt engineering and logit-based ranking strategies.

**Best Public MAP@3:** **0.75519**

---

## Training Configuration

### Qwen LoRA

| Parameter | Value |
|-----------|-------|
| Base Model | Qwen2.5-7B-Instruct |
| Fine-tuning | LoRA |
| Quantization | 4-bit QLoRA |
| Epochs | 2 |
| Learning Rate | 2e-4 |
| Optimizer | PagedAdamW8bit |

---

### BiLSTM

| Parameter | Value |
|-----------|-------|
| Embedding Dimension | 200 |
| Hidden Dimension | 256 |
| Layers | 1 |
| Dropout | 0.4 |
| Optimizer | Adam |
| Loss Function | CrossEntropyLoss |

---

## Experimental Progress

| Experiment | Public MAP@3 |
|------------|-------------:|
| Qwen LoRA (Initial Logit Scoring) | 0.62427 |
| Qwen LoRA (Generation-Based Inference) | 0.72402 |
| Qwen LoRA (Beam Search) | 0.73316 |
| BiLSTM (Built From Scratch) | 0.74023 |
| Qwen LoRA (Final Optimized Pipeline) | **0.75519** |

---

## Contents

The repository includes:

- Milestone notebooks
- Model implementation notebooks
- Experiment notebooks
- Training checkpoints
- Submission files
- Project documentation

---

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- PEFT (LoRA)
- TRL
- Sentence Transformers
- Scikit-learn
- Pandas
- NumPy
- Weights & Biases (W&B)

---
