# Current Model Recommendations

> **Last updated:** 2026-08-14
> **Benchmark reference:** [artificialanalysis.ai/leaderboards/models](https://artificialanalysis.ai/leaderboards/models)

Agents: **never assume your training data has current model names.** Models change faster than your knowledge. Check this file before selecting any external LLM model. If this file is >30 days old, escalate to the board requesting a model refresh.

---

## QA / Vision Evaluation

For analyzing screenshots, video, and evaluating web UI quality. Quality is paramount — always use the best available model.

| Recommended | `gemini-3.7-flash` (at `thinkingLevel: "high"`) |
|---|---|
| Provider | Google (Gemini API) |
| Why | Founder directive 2026-08-14: `gemini-3.7-flash` (released 2026-08-13) replaces `gemini-3.1-pro-preview` for QA/vision — judged higher quality at high reasoning effort, and far cheaper. Always run at `thinkingConfig.thinkingLevel: "high"`. |
| Env var | `GEMINI_QA_MODEL=gemini-3.7-flash` |

## Voice / Speech-to-Speech

For real-time voice agents (Pipecat).

| Recommended | `gemini-3.1-flash-live-preview` |
|---|---|
| Provider | Google (Gemini Live API) |
| Why | Lowest latency, supports audio+video+tool-use simultaneously (March 2026) |

GA fallback: `gemini-live-2.5-flash-native-audio`.

## Text-to-Speech / Pre-Call Greetings

For synthesizing audio ahead of time (e.g. per-customer greeting PCMs that play on call connect while Gemini Live warms up). Not the live mid-call path — that's Gemini Live above.

| Recommended | `gemini-3.1-flash-tts-preview` |
|---|---|
| Provider | Google (Gemini API) |
| Why | Low-latency speech generation, single or multi-speaker. Supersedes `gemini-2.5-flash-preview-tts`. |
| Output | 24kHz 16-bit mono PCM |

Supersedes: `gemini-2.5-flash-preview-tts` (still functional; existing cached PCMs are not force-migrated).

## Image Generation / Editing

For product images, hero images, OG images, and any image editing.

| Recommended | `gemini-3.1-flash-image-preview` |
|---|---|
| Provider | Google (Gemini API) |
| Why | Native generation and editing in one model. Use for all image needs. |

## General LLM Reasoning

When agents need a non-Claude external LLM (content generation, analysis, extraction).

| Recommended | `gemini-3.7-flash` (at `thinkingLevel: "high"`) |
|---|---|
| Provider | Google |
| Why | Founder directive 2026-08-14: `gemini-3.7-flash` (released 2026-08-13) replaces `gemini-3.1-pro-preview` as the default external-LLM/reasoning model — judged higher quality at high reasoning effort, and far cheaper. Always run at `thinkingConfig.thinkingLevel: "high"`. |

Low-latency alternative: `gemini-3.1-flash-lite-preview` (only when ultra-low latency is required).

## Deep Research / Multi-Step Investigation

For multi-step research with citations — market analysis, opportunity evaluation, competitor scans. Async Interactions API, 10-20 min per run.

| Recommended | `deep-research-max-preview-04-2026` |
|---|---|
| Provider | Google (Gemini Interactions API) |
| Why | Deepest Deep Research variant. Multimodal input, cited reports, visualizations, MCP tool support. Fleet routes via ops `research-cli.js` / MCP `gemini_start_research`. |
| Endpoint | `POST /v1beta/interactions` with `agent` field |

Standard alternative: `deep-research-preview-04-2026` (faster, shallower).

Supersedes: `deep-research-pro-preview-12-2025`.

## Embeddings

For semantic search / RAG if needed.

| Recommended | `gemini-embedding-002` |
|---|---|
| Provider | Google |
| Why | First native multimodal embedding model, #1 on MTEB multilingual. Text + image + video + audio in unified vector space. |

---

## Deprecation Warnings

- **`gemini-3.1-pro-preview`** RETIRED **2026-08-14** (founder directive) — replaced everywhere by `gemini-3.7-flash` at `thinkingLevel: "high"` (QA/vision + general reasoning). Do not select `gemini-3.1-pro-preview` for any new work.
- **Gemini 2.0 Flash** and **2.0 Flash-Lite** shut down **June 1, 2026**. Update any references.
- **`deep-research-pro-preview-12-2025`** superseded by `deep-research-max-preview-04-2026` on 2026-04-21.

## How This File Is Maintained

- The SI cycle (Evolution) proposes updates; changes require **board approval** before merging.
- Source of truth: `https://raw.githubusercontent.com/daemonventures/reference/main/models.md`
- Businesses fetch this URL before making model selection decisions.
