# 01 — GPU Fundamentals & VRAM Behavior

## 🎯 Objectives
- Understand GPU architecture at a practical, infra‑engineering level.
- Learn how VRAM is consumed by:
  - Model weights
  - Activations
  - KV cache
  - Batch size
  - Precision (FP32, FP16, BF16, INT8, INT4)
- Benchmark throughput (tokens/sec) vs batch size and precision.
- Build intuition for GPU bottlenecks: compute‑bound vs memory‑bound.

---

## 🧠 Core Concepts

### 1. GPU Architecture (Infra‑Relevant View)
- **SMs (Streaming Multiprocessors):** parallel compute units.
- **Tensor Cores:** specialized matrix‑multiply units for FP16/BF16/INT8.
- **Memory hierarchy:** registers → shared memory → L2 → VRAM.
- **Memory bandwidth** often limits LLM inference more than compute.

### 2. VRAM Budgeting
VRAM is consumed by:

| Component | Formula | Notes |
|----------|---------|-------|
| **Weights** | `params × precision_bytes` | FP16 = 2 bytes, INT8 = 1 byte |
| **Activations** | `batch × seq_len × hidden_dim × precision` | Training only |
| **KV Cache** | `batch × seq_len × num_layers × hidden_dim × 2 × precision` | Dominant cost in inference |
| **Optimizer states** | 2–4× model size | Training only |

### 3. Precision & VRAM
- FP32 → FP16 cuts VRAM in half.
- FP16 → INT8 cuts VRAM in half again.
- INT4 cuts VRAM by 75% vs FP16.

### 4. Throughput vs Latency
- **Batch size ↑** → throughput ↑, latency ↑.
- **Sequence length ↑** → KV cache ↑ → VRAM ↑ → throughput ↓.

---

## 🧪 Experiments to Run

### Experiment 1 — Measure VRAM usage for FP16 vs INT8
1. Load a 7B model in FP16.
2. Record VRAM usage.
3. Load the same model quantized to INT8.
4. Compare.

### Experiment 2 — Tokens/sec vs Batch Size
Run batch sizes: 1, 2, 4, 8, 16, 32  
Plot:
- p50 latency
- tokens/sec
- GPU utilization

### Experiment 3 — KV Cache Growth
Generate sequences of length:
- 32, 64, 128, 256, 512, 1024  
Record VRAM usage.

---

## 📊 Expected Results (Qualitative)
- INT8 should give ~40–50% VRAM savings.
- Batch size increases throughput until VRAM saturates.
- KV cache dominates VRAM at long sequence lengths.
- GPU utilization should approach 90–100% at high batch sizes.

---

## 🛠️ Useful Commands

### GPU Monitoring
```bash
watch -n 0.5 nvidia-smi
