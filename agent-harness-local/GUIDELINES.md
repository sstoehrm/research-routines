# Agent Harness (Local) — Research Guidelines

Scope for this topic: agent harnesses and frameworks that **run against local / self-hosted open-weights LLMs**, the serving backends that feed them, and which model × backend × harness combinations actually work in practice.

## What counts as in-scope

- **Harnesses / CLIs / IDE agents**: coding-agent CLIs (Aider, OpenHands, Plandex, Goose, Codex CLI with `--oss`, Letta Code, …), IDE extensions (Cline, Roo Code, Continue), orchestration frameworks (LangGraph, Smolagents, CrewAI, AutoGen, Agno, Dify, Qwen-Agent).
- **Serving backends**: llama.cpp / `llama-server`, Ollama, vLLM, SGLang, LM Studio, MLX / mlx-lm, TGI, TensorRT-LLM, ExLlamaV2, KoboldCpp, Aphrodite.
- **Model × backend × harness combos**: concrete stacks that work, organized by model size tier.
- **Tool-calling / function-calling plumbing**: chat templates, tool-call parsers, MCP support, common gotchas (JSON vs XML tags, streaming bugs, chat-template mismatches).

Out of scope: hosted-only agents (pure API wrappers with no local path), generic RAG libraries that are not used as agent runtimes, and framework comparisons that ignore local-LLM fit.

## Model size tiers

All tier-specific recommendations should slot into these buckets:

- **Small** (≤ 8B)
- **Medium** (8B – 32B)
- **Large** (32B – 100B)
- **XL** (100B+, usually MoE)

## Source discipline

- Prefer **project docs** (harness docs, backend docs, model cards on HuggingFace) and **GitHub issues / releases** over blog posts.
- When a claim comes from a blog / aggregator / Medium post, mark it **medium confidence**. When it comes from upstream docs or a release note, mark it **high confidence**.
- **Every URL must be real** — never fabricate model names, version numbers, or URLs. If a search surfaces a name that cannot be verified against a primary source, flag it in the Caveats section rather than presenting it as fact.
- Dates should be the most recent verifiable date (release tag, blog post, issue close date). If uncertain, write "date uncertain".

## Execution file format

One file per run: `YYYY-MM-DD.md`, dated the day the run executed (UTC).

Required structure:

1. **Run metadata** — date, window covered, scope notes.
2. **TL;DR** — 4-8 sentence summary of notable movement since last run.
3. **Harnesses / frameworks** — grouped by kind (coding-agent CLIs, IDE harnesses, orchestration libs), each with: what it is, status in 2026, local-LLM support notes, URL.
4. **Serving backends** — table of backends with tool-call support notes.
5. **Model × backend × harness combos** — one subsection per tier (Small / Medium / Large / XL). For each combo list model, backend, harness, rationale, and gotchas.
6. **Recommendations** — rig-specific picks (single-GPU workstation, Apple Silicon Mac, multi-GPU rig).
7. **Caveats** — flag any content that could not be verified against a primary source.

## House style

- Be specific: name the exact tool-call parser, the exact chat template, the exact quantization.
- Always mention the **gotcha** — chat-template mismatches, parser bugs, context-length caveats, quantization trade-offs. A combo without known gotchas is a combo that wasn't stress-tested.
- If a "works well" claim rests only on vendor marketing, say so.
- Avoid recommending models whose names or versions cannot be verified. If a search result mentions a plausible-but-unverified model, keep it in Caveats.
