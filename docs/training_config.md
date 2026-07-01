# Training Configuration

## Dataset

Training Samples: 2000

Validation Samples: 200

Test Samples: 500

Evaluation Metric:

MAP@3

---

## Base Model

Qwen2.5-3B-Instruct

---

## Fine-Tuning

Method:

LoRA

Precision:

4-bit Quantization

Trainer:

TRL SFTTrainer

---

## Hyperparameters

Epochs:

2

Learning Rate:

2e-4

Optimizer:

PagedAdamW8bit

Batch Size:

1

Gradient Accumulation:

4

Maximum Sequence Length:

1024

Warmup Steps:

5

---

## Checkpoints

checkpoint-225

checkpoint-450

Final Model:

checkpoint-450

---

## Final Leaderboard Score

0.73316
