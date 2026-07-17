# Training Configuration

## Qwen LoRA

Base Model

- Qwen/Qwen2.5-7B-Instruct

Quantization

- 4-bit NF4

LoRA

- Rank : 16
- Alpha : 32
- Dropout : 0.05

Target Modules

- q_proj
- k_proj
- v_proj
- o_proj
- gate_proj
- up_proj
- down_proj

Epochs

- 2

Optimizer

- paged_adamw_8bit

Learning Rate

- 2e-4

---

## BiLSTM

Embedding Size

- 200

Hidden Size

- 256

Layers

- 1

Dropout

- 0.4

Optimizer

- Adam

Loss

- CrossEntropyLoss

Epochs

- 10
