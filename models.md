# Current Model Recommendations

> **Last updated:** 2026-04-01
> **Updated by:** SI Cycle 19
> **Benchmark reference:** [artificialanalysis.ai/leaderboards/models](https://artificialanalysis.ai/leaderboards/models)

Agents: **never assume your training data has current model names.** Models change faster than your knowledge. Check this file before selecting any external LLM model. If this file is >30 days old, escalate to the board requesting a model refresh.

---

## QA / Vision Evaluation

For analyzing screenshots, video, and evaluating web UI quality.

| Recommended | `gemini-2.5-flash` |
|---|---|
| Provider | Google (Gemini API) |
| Why | GA, strong multimodal vision, best price-performance, native video understanding |
| Env var | `GEMINI_QA_MODEL=gemini-2.5-flash` |

Preview alternative: `gemini-3.1-pro-preview` (higher quality, not yet GA).

## Voice / Speech-to-Speech

For real-time voice agents (Pipecat).

| Recommended | `gemini-3.1-flash-live-preview` |
|---|---|
| Provider | Google (Gemini Live API) |
| Why | Lowest latency, supports audio+video+tool-use simultaneously (March 2026) |

GA fallback: `gemini-live-2.5-flash-native-audio`.

## Image Generation

For product images, hero images, OG images.

| Recommended | `imagen-4.0-generate-001` |
|---|---|
| Provider | Google (Gemini API / Vertex AI) |
| Why | GA, strong photorealism with text rendering, $0.04/image. No new vendor needed. |

Fast variant: `imagen-4.0-fast-generate-001` ($0.02/image).

## General LLM Reasoning

When agents need a non-Claude external LLM (content generation, analysis, extraction).

| Recommended (stable) | `gemini-2.5-flash` |
|---|---|
| Recommended (best) | `gemini-3.1-pro-preview` |
| Provider | Google |
| Why | 2.5 Flash: GA workhorse, cheap, fast. 3.1 Pro: #1 on Artificial Analysis (score 57), still preview. |

## Code Generation / Agentic Work

DV agents run on Claude via Claude Max.

| Flagship | `claude-opus-4-6` (1M context, 128K output) |
|---|---|
| Balanced | `claude-sonnet-4-6` (faster, 64K output) |
| Light | `claude-haiku-4-5` (cost-sensitive tasks) |
| Provider | Anthropic |

## Embeddings

For semantic search / RAG if needed.

| Recommended | `gemini-embedding-002` |
|---|---|
| Provider | Google |
| Why | First native multimodal embedding model, #1 on MTEB multilingual. Text + image + video + audio in unified vector space. |

---

## Deprecation Warnings

- **Gemini 2.0 Flash** and **2.0 Flash-Lite** shut down **June 1, 2026**. Update any references to `gemini-2.5-flash`.

## How This File Is Maintained

- The SI cycle (Evolution) updates this file every 3 days using web research and benchmark data.
- Source of truth: `https://raw.githubusercontent.com/daemonventures/reference/main/models.md`
- Businesses fetch this URL before making model selection decisions.
