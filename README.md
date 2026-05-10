<div align="center">

<br>

<pre>
 ______     ______     __   __     __     ______   __  __
/\___  \   /\  ___\   /\ "-.\ \   /\ \   /\__  _\ /\ \_\ \
\/_/  /__  \ \  __\   \ \ \-.  \  \ \ \  \/_/\ \/ \ \  __ \
  /\_____\  \ \_____\  \ \_\\"\_\  \ \_\    \ \_\  \ \_\ \_\
  \/_____/   \/_____/   \/_/ \/_/   \/_/     \/_/   \/_/\/_/
</pre>

<br>

# ZENITH-AMD

**AI-Powered Contract Risk Analysis**

<br>

[![License](https://img.shields.io/badge/License-MIT-informational?style=flat-square&labelColor=0d1117&color=238636)](https://github.com/Zenith-AMD)
[![Built on AMD](https://img.shields.io/badge/Infrastructure-AMD%20Developer%20Cloud-informational?style=flat-square&labelColor=0d1117&color=ed1c24)](https://developer.amd.com)
[![ROCm](https://img.shields.io/badge/GPU-ROCm%20Accelerated-informational?style=flat-square&labelColor=0d1117&color=7c3aed)](https://rocm.docs.amd.com)
[![Go](https://img.shields.io/badge/Backend-Go-informational?style=flat-square&labelColor=0d1117&color=00ADD8)](https://go.dev)
[![React](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-informational?style=flat-square&labelColor=0d1117&color=61DAFB)](https://react.dev)
[![Mistral 7B](https://img.shields.io/badge/Model-Mistral%207B-informational?style=flat-square&labelColor=0d1117&color=f97316)](https://mistral.ai)
[![Ollama](https://img.shields.io/badge/Inference-Ollama-informational?style=flat-square&labelColor=0d1117&color=white)](https://ollama.com)

<br>

> *Contract law is complex. Access to intelligent analysis should not be.*

<br>

</div>

---
[Frontend](https://github.com/Zenith-AMD/Zenith-frontend) &nbsp;&middot;&nbsp; [Backend](https://github.com/Zenith-AMD/back) &nbsp;&middot;&nbsp;
---
<div align="center">

### Zerith is a production-grade contract intelligence platform.
### It ingests legal documents, isolates risk, and surfaces structure — fast.

</div>

---

<br>

## Overview

Zerith is purpose-built for one thing: making contract analysis fast, reliable, and accessible without a legal team. It combines a Go backend, a chunked inference pipeline, and local GPU inference via Ollama and Mistral 7B to deliver structured analysis on documents of any size — from short NDAs to enterprise-scale agreements.

The system is deployed over HTTPS, reverse-proxied through Caddy, accelerated by ROCm on AMD hardware, and served through a React frontend with a deliberately minimal, high-quality UX.

This is not a wrapper around a third-party API. Every layer of the stack is owned, configured, and optimized.

<br>

---

## Why Zerith Exists

Modern contracts are long, dense, and written to obscure liability. Most individuals — and many small organizations — sign agreements without a complete understanding of what they contain. Legal review is expensive, slow, and inaccessible at scale.

Existing AI tools either route sensitive documents through third-party cloud APIs (a privacy concern for legal material), produce generic summaries with no structural insight, or fail entirely on large documents due to context window limitations.

Zerith was built to solve the real problem: **give anyone a fast, private, structured understanding of what a contract actually says and where the risk lives.**

<br>

---

## Core Features

<br>

<div align="center">

| Capability | Description |
|---|---|
| **Contract Summarization** | Concise, structured summaries of full legal documents |
| **Risk Clause Detection** | Identifies and flags clauses with elevated legal or financial risk |
| **Important Clause Extraction** | Surfaces key obligations, termination terms, and liability provisions |
| **Multi-Jurisdiction Support** | Handles contracts written under varying legal frameworks |
| **Real-Time AI Analysis** | Streamed inference with low-latency response pipeline |
| **GPU-Accelerated Inference** | Full ROCm acceleration on AMD hardware via Ollama |
| **Chunked Document Processing** | Handles large documents beyond standard context window limits |
| **Dark / Light Mode** | Full theme support with system preference detection |
| **HTTPS Deployed Infrastructure** | Production-grade reverse proxy with TLS termination via Caddy |

</div>

<br>

---

## Architecture

<br>

```
                        ┌─────────────────────────────┐
                        │        React Frontend        │
                        │   Vite  /  Tailwind  /  FM   │
                        └──────────────┬──────────────┘
                                       │  HTTPS
                                       │  (Caddy Reverse Proxy)
                        ┌──────────────▼──────────────┐
                        │          Go Backend          │
                        │   REST API  /  Auth  /  IO   │
                        └──────────────┬──────────────┘
                                       │
                        ┌──────────────▼──────────────┐
                        │       Chunking Pipeline      │
                        │  Document segmentation for   │
                        │  context-window compliance   │
                        └──────────────┬──────────────┘
                                       │
                        ┌──────────────▼──────────────┐
                        │      Ollama  +  Mistral 7B   │
                        │   Local inference  /  API    │
                        └──────────────┬──────────────┘
                                       │
                        ┌──────────────▼──────────────┐
                        │      ROCm GPU Inference      │
                        │   AMD Developer Cloud Host   │
                        └─────────────────────────────┘
                                       │
                        ┌──────────────▼──────────────┐
                        │    Structured JSON Response  │
                        │  Summary / Risk / Clauses    │
                        └─────────────────────────────┘
```

<br>

Each request enters through the React frontend, is authenticated and routed by the Go backend, segmented by the chunking layer for arbitrarily large documents, passed to Ollama running Mistral 7B, accelerated by ROCm on AMD GPU hardware, and returned as a deterministic structured response.

<br>

---

## Repositories

<br>

<div align="center">

| Repository | Description | Stack |
|---|---|---|
| [**Zenith-frontend**](https://github.com/Zenith-AMD/Zenith-frontend) | User interface, document upload, analysis display, theme system | React, Vite, TailwindCSS, Framer Motion |
| [**back**](https://github.com/Zenith-AMD/back) | API server, inference orchestration, chunking pipeline, Ollama integration | Go, Ollama, Mistral 7B, ROCm |

</div>

<br>

---

## Technology Stack

<br>

<div align="center">

| Layer | Technology | Role |
|---|---|---|
| **Frontend Framework** | React + Vite | UI rendering, hot-reload development |
| **Styling** | TailwindCSS | Utility-first layout and theming |
| **Animation** | Framer Motion | Transitions, micro-interactions |
| **Backend Language** | Go | High-performance API server |
| **Inference Runtime** | Ollama | Local model serving and API abstraction |
| **Language Model** | Mistral 7B | Document analysis and structured output |
| **GPU Acceleration** | ROCm | AMD GPU compute for inference workloads |
| **Cloud Infrastructure** | AMD Developer Cloud | Hosted GPU instance |
| **Reverse Proxy / TLS** | Caddy | HTTPS termination, automatic certificate management |

</div>

<br>

---

## Performance

<br>

Benchmarks measured end-to-end: document upload through structured analysis response, on AMD Developer Cloud GPU infrastructure.

<br>

<div align="center">

| Document Size | Word Count | Inference Time | Throughput |
|---|---|---|---|
| Short contract | ~578 words | **~4.7 seconds** | ~123 words/sec |
| Medium contract | ~700 words | **~5.5 seconds** | ~127 words/sec |
| Long contract | ~6,000 words | **~9.2 seconds** | ~652 words/sec |

</div>

<br>

> The chunked pipeline means inference time does not scale linearly with document length. Larger documents benefit from parallelized chunk processing, yielding proportionally higher throughput at scale.

<br>

---

## Infrastructure

<details>
<summary><strong>AMD Developer Cloud + ROCm</strong></summary>

<br>

Zerith's inference stack runs on AMD Developer Cloud GPU instances. ROCm (Radeon Open Compute) provides the GPU abstraction layer that Ollama targets for hardware-accelerated inference. Getting ROCm to correctly expose GPU devices to the Ollama runtime required explicit device configuration — this was one of the more technically involved parts of the deployment.

ROCm enables competitive inference performance on AMD GPUs without the CUDA ecosystem, making the full stack portable to AMD hardware at any deployment scale.

<br>

</details>

<details>
<summary><strong>Ollama + Mistral 7B</strong></summary>

<br>

Ollama provides a local inference API that abstracts model loading, GPU scheduling, and request handling. Mistral 7B was selected for its balance of instruction-following fidelity, context window size, and inference speed at this parameter scale.

The backend communicates with Ollama's REST API, passing structured prompts and parsing structured JSON responses to build the final analysis output.

<br>

</details>

<details>
<summary><strong>Caddy Reverse Proxy</strong></summary>

<br>

Caddy handles TLS termination, HTTP-to-HTTPS redirection, and reverse proxying to the Go backend. Its automatic certificate management via ACME eliminates the operational overhead of manual TLS configuration and keeps the deployment production-grade without additional infrastructure.

<br>

</details>

<details>
<summary><strong>Chunking Pipeline</strong></summary>

<br>

Contracts exceeding practical context window limits are segmented into overlapping chunks by the Go backend before being dispatched to Ollama. Each chunk is analyzed independently, and the results are merged and reconciled into a single coherent structured output. This approach makes Zerith functional on arbitrarily large documents without model fine-tuning or RAG infrastructure.

<br>

</details>

<br>

---

## Engineering Philosophy

Zerith was not built to demonstrate what AI can theoretically do. It was built to demonstrate what AI can reliably do in production.

Every design decision was made through the lens of practical deployment:

- **Latency over capability** — A system that responds in 5 seconds is more useful than one that responds in 60 with marginally better output.
- **Local inference over cloud APIs** — Sensitive legal documents should not leave the deployment environment through a third-party API boundary.
- **Structured outputs over prose** — Analysis results are deterministic JSON, not free-form text, which makes them renderable, diffable, and programmatically useful.
- **Ownership of the full stack** — Every layer — from the frontend to the GPU inference process — is configured and controlled, not abstracted away by a managed service.
- **Reliability over features** — A smaller, well-functioning feature set outperforms a larger, brittle one in every real-world deployment context.

<br>

---

## Challenges Solved

<br>

<div align="center">

| Challenge | Resolution |
|---|---|
| **ROCm GPU detection** | Explicit device environment configuration to surface AMD GPUs correctly to the Ollama runtime |
| **Ollama GPU passthrough** | Resolved device visibility and driver compatibility between ROCm and Ollama's hardware detection layer |
| **Reverse proxy deployment** | Configured Caddy for TLS termination with correct upstream routing to the Go API server |
| **Large document inference** | Built a chunking and result-merging pipeline to handle documents beyond Mistral 7B's context window |
| **Latency optimization** | Minimized round-trip time through prompt engineering, response streaming, and eliminating unnecessary intermediate processing |
| **Deployment stability** | Hardened process management and service recovery to maintain uptime under variable inference load |

</div>

<br>

---

## Future Scope

The current system is a functional, deployed foundation. The following directions represent the natural extension of this architecture:

<br>

- **Semantic Embeddings** — Move beyond chunk-based processing to vector-indexed contract retrieval, enabling clause-level search and cross-document comparison.
- **Multilingual Support** — Extend analysis capabilities to contracts written in non-English jurisdictions. Legal language has structural patterns that transfer across languages.
- **Enterprise Integrations** — Webhook and API integrations with DocuSign, Notion, and Salesforce to embed contract intelligence inside existing legal workflows.
- **Collaborative Review Systems** — Multi-user annotation layers on top of AI analysis, enabling legal teams to dispute, confirm, and augment model outputs.
- **Legal Retrieval Systems** — RAG-based citation of relevant case law and jurisdiction-specific precedents alongside contract analysis.
- **Fine-Tuned Legal Models** — Domain-specific fine-tuning on contract corpora for improved clause classification precision over general-purpose instruction models.

<br>

---

## Open Source

Zenith-AMD is fully open source. Both repositories are public, documented, and structured for external contribution.

If you work on Go backends, LLM inference infrastructure, legal technology, or frontend systems — and this work is relevant to problems you care about — contributions are welcome.

**How to contribute:**

1. Fork the relevant repository
2. Create a feature branch with a descriptive name
3. Commit with clear, scoped messages
4. Open a pull request against `main` with context on the change

For larger changes or architectural proposals, open an issue first to align on direction before building.

<br>

---

## Team

<div align="center">

| | |
|---|---|
| **Origin** | Built during the AMD AI Hackathon |
| **Organization** | Zenith-AMD |
| **Infrastructure** | AMD Developer Cloud |
| **Stack** | Go / React / Ollama / Mistral 7B / ROCm / Caddy |

</div>

<br>

Zerith was designed, built, and deployed as a complete system during the AMD AI Hackathon — from architecture decisions and GPU environment setup to frontend UX and production deployment. The scope was intentionally ambitious: a working, HTTPS-deployed, GPU-accelerated AI platform within a compressed timeline.

<br>

---

## Screenshots

<div align="center">

<!-- Hero / Landing -->
> `[ Screenshot: Landing page — dark mode ]`

<!-- Analysis Interface -->
> `[ Screenshot: Contract upload and analysis result view ]`

<!-- Risk Detection Panel -->
> `[ Screenshot: Risk clause detection panel ]`

<!-- Mobile View -->
> `[ Screenshot: Mobile responsive layout ]`

</div>

<br>

---

<div align="center">

**ZENITH-AMD**

[Frontend](https://github.com/Zenith-AMD/Zenith-frontend) &nbsp;&middot;&nbsp; [Backend](https://github.com/Zenith-AMD/back) &nbsp;&middot;&nbsp; [AMD Developer Cloud](https://developer.amd.com) &nbsp;&middot;&nbsp; [ROCm](https://rocm.docs.amd.com)

<br>

*Built with precision. Deployed with intent.*

<br>

---

MIT License &nbsp;&middot;&nbsp; Zenith-AMD &nbsp;&middot;&nbsp; AMD AI Hackathon

</div>
