# Current Model Recommendations

> **Last updated:** 2026-04-01
> **Benchmark reference:** [artificialanalysis.ai/leaderboards/models](https://artificialanalysis.ai/leaderboards/models)

Agents: **never assume your training data has current model names.** Models change faster than your knowledge. Check this file before selecting any external LLM model. If this file is >30 days old, escalate to the board requesting a model refresh.

---

## QA / Vision Evaluation

For analyzing screenshots, video, and evaluating web UI quality. Quality is paramount — always use the best available model.

| Recommended | `gemini-3.1-pro-preview` |
|---|---|
| Provider | Google (Gemini API) |
| Why | #1 on Artificial Analysis (score 57), best multimodal reasoning. Preview latency is irrelevant for QA. |
| Env var | `GEMINI_QA_MODEL=gemini-3.1-pro-preview` |

## Voice / Speech-to-Speech

For real-time voice agents (Pipecat).

| Recommended | `gemini-3.1-flash-live-preview` |
|---|---|
| Provider | Google (Gemini Live API) |
| Why | Lowest latency, supports audio+video+tool-use simultaneously (March 2026) |

GA fallback: `gemini-live-2.5-flash-native-audio`.

## Image Generation / Editing

For product images, hero images, OG images, and any image editing.

| Recommended | `gemini-3.1-flash-image-preview` |
|---|---|
| Provider | Google (Gemini API) |
| Why | Native generation and editing in one model. Use for all image needs. |

## General LLM Reasoning

When agents need a non-Claude external LLM (content generation, analysis, extraction).

| Recommended | `gemini-3.1-pro-preview` |
|---|---|
| Provider | Google |
| Why | #1 on Artificial Analysis (score 57). Default choice for all external LLM calls. |

Low-latency alternative: `gemini-3.1-flash-lite-preview` (only when ultra-low latency is required).

## Embeddings

For semantic search / RAG if needed.

| Recommended | `gemini-embedding-002` |
|---|---|
| Provider | Google |
| Why | First native multimodal embedding model, #1 on MTEB multilingual. Text + image + video + audio in unified vector space. |

---

## Deprecation Warnings

- **Gemini 2.0 Flash** and **2.0 Flash-Lite** shut down **June 1, 2026**. Update any references.

## How This File Is Maintained

- The SI cycle (Evolution) proposes updates; changes require **board approval** before merging.
- Source of truth: `https://raw.githubusercontent.com/daemonventures/reference/main/models.md`
- Businesses fetch this URL before making model selection decisions.
