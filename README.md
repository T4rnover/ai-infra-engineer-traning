# 🚀 AI Infrastructure Engineer — 12‑Week Training Plan

A complete, production‑grade, hands‑on training program designed to take you from “LLM user” to **AI Infrastructure Engineer** capable of running high‑throughput inference, distributed training, scalable RAG systems, and full observability pipelines.

This repository includes:
- Weekly modules with labs, notes, and benchmarks  
- vLLM + TensorRT‑LLM inference optimization  
- Distributed training (DDP, FSDP, DeepSpeed)  
- Kubernetes model serving + autoscaling  
- Vector DB RAG pipelines  
- Prompt caching + cost optimization  
- Observability with OpenTelemetry, Prometheus, Grafana  
- A full capstone project with deployment artifacts  

All training materials use **free** resources and open‑source tools.

---

# 12‑Week AI Infrastructure Engineer Training Plan

A fully actionable, free curriculum covering GPU fundamentals, vLLM/TensorRT‑LLM, distributed training, RAG pipelines, observability, and production‑grade model serving.

This plan is designed for engineers who want hands‑on, production‑oriented AI infrastructure skills without paid courses.

---

## 📚 Overview

**Duration:** 12 Weeks  
**Focus Areas:**
- GPU/VRAM fundamentals, quantization, batching  
- vLLM, TensorRT‑LLM, inference optimization  
- KV caching, speculative decoding, throughput engineering  
- Distributed training (DDP, FSDP, ZeRO, DeepSpeed)  
- Model serving, autoscaling, Kubernetes  
- Vector DBs, RAG pipelines  
- Prompt caching, cost optimization  
- Observability & tracing for LLM apps  

All modules use **free** resources: NVIDIA DLI, Coursera (audit), Hugging Face, and open‑source tools.

---

# 🗓️ Weekly Breakdown

---

## **Week 1 — GPU & VRAM Fundamentals**
**Objectives**
- GPU architecture, tensor cores, memory bandwidth  
- VRAM budgeting: weights, activations, KV cache, batch size  

**Hands‑on**
- Run FP16 vs INT8 models  
- Measure VRAM with `nvidia-smi`  
- Benchmark tokens/sec vs batch size  

**Sources**
- NVIDIA DLI: Fundamentals of Accelerated Computing  
- AI Infra Curriculum (GitHub)

---

## **Week 2 — Quantization, Batching & Throughput**
**Objectives**
- INT8/INT4 quantization (GPTQ, AWQ, BitsAndBytes)  
- Throughput vs latency tradeoffs  

**Hands‑on**
- Quantize a 7B model  
- Compare FP16 vs INT8 vs INT4 throughput  
- Plot latency vs batch size  

**Sources**
- Hugging Face quantization notebooks  
- BitsAndBytes docs  

---

## **Week 3 — vLLM Fundamentals**
**Objectives**
- PagedAttention  
- Continuous batching  
- KV cache paging  

**Hands‑on**
- Serve a 7B model with vLLM  
- Benchmark concurrency & tokens/sec  
- Compare vLLM vs HF Transformers  

**Sources**
- vLLM GitHub examples  
- HF vLLM cookbook  

---

## **Week 4 — TensorRT‑LLM & Kernel Optimization**
**Objectives**
- Graph optimization  
- Kernel fusion  
- Quantization‑aware inference  

**Hands‑on**
- Convert a model to TensorRT‑LLM  
- Benchmark vs vLLM  
- Inspect fused kernels  

**Sources**
- TensorRT‑LLM GitHub  
- NVIDIA DLI TensorRT modules  

---

## **Week 5 — KV Caching & Speculative Decoding**
**Objectives**
- KV cache growth & memory impact  
- Prefix caching  
- Draft‑model speculative decoding  

**Hands‑on**
- Enable prefix caching in vLLM  
- Test speculative decoding  
- Measure break‑even points  

**Sources**
- vLLM speculative decoding docs  
- HF speculative decoding examples  

---

## **Week 6 — Distributed Training (DDP, FSDP, ZeRO, DeepSpeed)**
**Objectives**
- Data parallel vs model parallel  
- FSDP sharding  
- ZeRO‑1/2/3  
- Offloading  

**Hands‑on**
- Train a small model with DDP  
- Repeat with FSDP  
- Repeat with DeepSpeed ZeRO‑3  
- Compare VRAM & step time  

**Sources**
- PyTorch FSDP tutorial  
- DeepSpeed examples  
- AI Infra Curriculum  

---

## **Week 7 — Model Serving Architecture**
**Objectives**
- Control plane vs data plane  
- GPU worker pools  
- Streaming  
- Multi‑model routing  

**Hands‑on**
- Deploy vLLM behind FastAPI  
- Add queueing & health checks  
- Implement streaming responses  

**Sources**
- vLLM serving examples  
- FastAPI docs  

---

## **Week 8 — Autoscaling & Load Testing**
**Objectives**
- HPA based on queue depth  
- GPU warmup & cold starts  
- p95 latency SLOs  

**Hands‑on**
- Deploy vLLM on Kubernetes  
- Add autoscaling  
- Load test with Locust or k6  
- Plot p50/p95/p99 latency  

**Sources**
- Kubernetes HPA docs  
- Locust load testing  

---

## **Week 9 — Vector Databases & Retrieval Pipelines**
**Objectives**
- Chunking strategies  
- Embedding models  
- ANN indexes (HNSW, IVF, PQ)  
- Re‑ranking  

**Hands‑on**
- Build a RAG pipeline with Chroma or Milvus  
- Use BGE/E5 embeddings  
- Add re‑ranking  
- Measure recall@k & latency  

**Sources**
- Chroma docs  
- Milvus bootcamp  
- HF RAG cookbook  

---

## **Week 10 — Prompt Caching & Cost Optimization**
**Objectives**
- Full‑response caching  
- Prefix/KV caching  
- Logit caching  
- Model size vs cost tradeoffs  

**Hands‑on**
- Implement KV prefix caching  
- Add Redis response caching  
- Measure cost/request before & after  

**Sources**
- vLLM prefix caching docs  
- Redis OSS  

---

## **Week 11 — Observability for LLM Apps**
**Objectives**
- OpenTelemetry tracing  
- Token‑level metrics  
- Retrieval hit rate  
- Semantic monitoring  

**Hands‑on**
- Add tracing around retrieval, inference, post‑processing  
- Build dashboards for latency, tokens/request, cost, errors  

**Sources**
- OpenTelemetry docs  
- Prometheus + Grafana  

---

## **Week 12 — Capstone Project**

Choose one:

### **Option A — High‑Throughput RAG Service**
- vLLM serving  
- Vector DB  
- Re‑ranking  
- Autoscaling  
- Observability  
- Prompt caching  

### **Option B — Distributed Training Pipeline**
- Train with FSDP or DeepSpeed  
- Log metrics  
- Evaluate  
- Package for inference  

### **Option C — GPU‑Optimized Inference Stack**
- TensorRT‑LLM  
- vLLM  
- Speculative decoding  
- Prefix caching  
- Benchmark suite  

**Deliverables**
- Architecture diagram  
- Benchmarks  
- Observability dashboards  
- Deployment manifests  
- Reproducible README  

---

## 🧩 License
This training plan is free to use, modify, and distribute.

---

## 🛠️ Contributions
Pull requests for improvements, additional labs, or new modules are welcome.



# 📁 Repository Structure

