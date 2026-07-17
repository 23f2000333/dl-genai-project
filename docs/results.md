# Experimental Results

| Model | Category | Public MAP@3 |
|--------|----------|-------------:|
| CrossEncoder MS-MARCO | Pretrained | 0.44887 |
| BiLSTM | Built From Scratch | 0.74023 |
| Qwen2.5 LoRA | Fine-tuned LLM | 0.73607 |
| Qwen2.5 LoRA (Optimized) | Fine-tuned LLM | **0.75519** |

## Best Performing Model

Qwen2.5-7B-Instruct + LoRA

Inference Strategy

- Logit Scoring
- Circular Permutations
- Temperature Calibration

Public Leaderboard Score

**0.75519**
