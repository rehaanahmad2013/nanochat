# nanochat training report

Generated: 2025-12-11 21:13:32

## Environment

### Git Information
- Branch: master
- Commit: 679edf5 (clean)
- Message: config saving

### Hardware
- Platform: Linux
- CPUs: 104 cores (208 logical)
- Memory: 1771.7 GB
- GPUs: 8x NVIDIA H100 80GB HBM3
- GPU Memory: 633.5 GB total
- CUDA Version: 12.8
- Hourly Rate: $24.00/hour

### Software
- Python: 3.10.12
- PyTorch: 2.8.0+cu128


### Bloat
- Characters: 422,103
- Lines: 10,468
- Files: 50
- Tokens (approx): 105,525
- Dependencies (uv.lock lines): 2,218

Run started: 2025-12-11 21:13:34

---

## Tokenizer training
timestamp: 2025-12-11 21:15:05

- max_chars: 2,000,000,000
- doc_cap: 10,000
- vocab_size: 65,536
- train_time: 84.1485
- num_special_tokens: 9
- token_bytes_min: 1
- token_bytes_max: 32
- token_bytes_mean: 6.9151
- token_bytes_std: 2.8736


## Tokenizer evaluation
timestamp: 2025-12-11 21:15:09

### Comparison with GPT-2

| Text Type | Bytes | GPT-2 Tokens | GPT-2 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 404 | 4.50 | 375 | 4.85 | +7.2% |
| korean | 893 | 745 | 1.20 | 721 | 1.24 | +3.2% |
| code | 1259 | 576 | 2.19 | 493 | 2.55 | +14.4% |
| math | 1834 | 936 | 1.96 | 966 | 1.90 | -3.2% |
| science | 1112 | 260 | 4.28 | 225 | 4.94 | +13.5% |
| fwe-train | 4208518 | 900364 | 4.67 | 856901 | 4.91 | +4.8% |
| fwe-val | 4908443 | 1059062 | 4.63 | 1010356 | 4.86 | +4.6% |

### Comparison with GPT-4

| Text Type | Bytes | GPT-4 Tokens | GPT-4 Ratio | Ours Tokens | Ours Ratio | Relative Diff % |
|-----------|-------|--------------|--------------|-------------|------------|-----------------|
| news | 1819 | 387 | 4.70 | 375 | 4.85 | +3.1% |
| korean | 893 | 364 | 2.45 | 721 | 1.24 | -98.1% |
| code | 1259 | 309 | 4.07 | 493 | 2.55 | -59.5% |
| math | 1834 | 832 | 2.20 | 966 | 1.90 | -16.1% |
| science | 1112 | 249 | 4.47 | 225 | 4.94 | +9.6% |
| fwe-train | 4208518 | 874799 | 4.81 | 856901 | 4.91 | +2.0% |
| fwe-val | 4908443 | 1029691 | 4.77 | 1010356 | 4.86 | +1.9% |


## Base model training
timestamp: 2025-12-12 00:17:47

- run: dummy
- device_type: 
- depth: 20
- max_seq_len: 2048
- num_iterations: -1
- target_flops: -1.0000
- target_param_data_ratio: 20
- device_batch_size: 32
- total_batch_size: 524,288
- embedding_lr: 0.2000
- unembedding_lr: 0.0040
- weight_decay: 0.0000
- matrix_lr: 0.0200
- grad_clip: 1.0000
- warmup_ratio: 0.0000
- warmdown_ratio: 0.2000
- final_lr_frac: 0.0000
- resume_from_step: -1
- eval_every: 250
- eval_tokens: 10,485,760
- core_metric_every: 2000
- core_metric_max_per_task: 500
- sample_every: 2000
- save_every: -1
- use_imaginary: True
- model_tag: 
- Number of parameters: 560,988,160
- Number of FLOPs per token: 3.491758e+09
- Calculated number of iterations: 21,400
- Number of training tokens: 11,219,763,200
- Tokens : Params ratio: 20.0000
- DDP world size: 8
- warmup_ratio: 0.0000
- warmdown_ratio: 0.2000
- final_lr_frac: 0.0000
- Minimum validation bpb: 0.8167
- Final validation bpb: 0.8167
- CORE metric estimate: 0.2064
- MFU %: 47.92%
- Total training flops: 3.917670e+19
- Total training time: 172.65m
- Peak memory usage: 75422.52MiB


## Base model loss
timestamp: 2025-12-12 00:18:24

- train bpb: 1.8244
- val bpb: 1.8145
- sample 0: <|bos|>The capital of France is the capital of the of the of the of the of the of the of the
- sample 1: <|bos|>The chemical symbol of gold is a symbol of a
A symbol of a
A symbol of a
A
- sample 2: <|bos|>If yesterday was Friday, then tomorrow will be
If tomorrow was was was was was was was was was was was was a
- sample 3: <|bos|>The opposite of hot is
The opposite of hot is is is is is is is is is is the
- sample 4: <|bos|>The planets of the solar system are: the solar system are the solar system are the solar system are the solar system are
- sample 5: <|bos|>My favorite color is the color is the color is the color is the color is the shape is the
- sample 6: <|bos|>If 5*x + 3 = 13, then x is 3 3 3 4 4 3 4 3


## Base model evaluation
timestamp: 2025-12-12 00:22:08

- Model: base_model (step 21400)
- CORE metric: 0.0223
- hellaswag_zeroshot: 0.0609
- jeopardy: 0.0000
- bigbench_qa_wikidata: 0.0103
- arc_easy: 0.1162
- arc_challenge: -0.0546
- copa: 0.2400
- commonsense_qa: 0.0581
- piqa: 0.1143
- openbook_qa: -0.0240
- lambada_openai: 0.0532
- hellaswag: 0.0180
- winograd: 0.0037
- winogrande: 0.0324
- bigbench_dyck_languages: 0.0010
- agi_eval_lsat_ar: 0.0380
- bigbench_cs_algorithms: 0.0061
- bigbench_operators: 0.0476
- bigbench_repeat_copy_logic: 0.0000
- squad: 0.0005
- coqa: 0.0157
- boolq: -0.4236
- bigbench_language_identification: 0.1772


## Midtraining
timestamp: 2025-12-12 00:31:17

- run: dummy
- device_type: 
- dtype: bfloat16
- num_iterations: -1
- max_seq_len: 2048
- device_batch_size: 32
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- init_lr_frac: 1.0000
- weight_decay: 0.0000
- eval_every: 150
- eval_tokens: 10,485,760
- total_batch_size: 524,288
- dry_run: 0
- Number of iterations: 809
- DDP world size: 8
- Minimum validation bpb: 0.4042


## Chat evaluation mid
timestamp: 2025-12-12 00:38:06

- source: mid
- task_name: None
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- device_type: 
- ARC-Easy: 0.4095
- ARC-Challenge: 0.2850
- MMLU: 0.3222
- GSM8K: 0.0417
- HumanEval: 0.0732
- SpellingBee: 0.9883
- ChatCORE metric: 0.2431


## Chat SFT
timestamp: 2025-12-12 00:40:29

- run: dummy
- source: mid
- device_type: 
- dtype: bfloat16
- device_batch_size: 4
- num_epochs: 1
- num_iterations: -1
- target_examples_per_step: 32
- unembedding_lr: 0.0040
- embedding_lr: 0.2000
- matrix_lr: 0.0200
- weight_decay: 0.0000
- init_lr_frac: 0.0200
- eval_every: 100
- eval_steps: 100
- eval_metrics_every: 200
- eval_metrics_max_problems: 1024
- Training rows: 22,439
- Number of iterations: 701
- Training loss: 0.5413
- Validation loss: 1.0398


## Chat evaluation sft
timestamp: 2025-12-12 00:46:15

- source: sft
- task_name: None
- dtype: bfloat16
- temperature: 0.0000
- max_new_tokens: 512
- num_samples: 1
- top_k: 50
- batch_size: 8
- model_tag: None
- step: None
- max_problems: None
- device_type: 
- ARC-Easy: 0.4167
- ARC-Challenge: 0.2952
- MMLU: 0.3231
- GSM8K: 0.0478
- HumanEval: 0.0793
- SpellingBee: 0.9805
- ChatCORE metric: 0.2479


## Summary

- Characters: 422,103
- Lines: 10,468
- Files: 50
- Tokens (approx): 105,525
- Dependencies (uv.lock lines): 2,218

| Metric          | BASE     | MID      | SFT      | RL       |
|-----------------|----------|----------|----------|----------|
| CORE            | 0.0223   | -        | -        | -        |
| ARC-Challenge   | -        | 0.2850   | 0.2952   | -        |
| ARC-Easy        | -        | 0.4095   | 0.4167   | -        |
| GSM8K           | -        | 0.0417   | 0.0478   | -        |
| HumanEval       | -        | 0.0732   | 0.0793   | -        |
| MMLU            | -        | 0.3222   | 0.3231   | -        |
| ChatCORE        | -        | 0.2431   | 0.2479   | -        |

Total wall clock time: 3h32m
