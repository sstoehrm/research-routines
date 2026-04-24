# Agent Harness (Local) — Research Guidelines

Scope for this topic folder. Every execution should produce one dated
report under `agent-harness-local/` that conforms to these guidelines.

## What belongs here

- **Agent harnesses** — the code around an LLM that does tool-calling,
  planning, session management, context handling, error recovery —
  that can be run against a **local / self-hosted** model.
- **Inference backends** usable as an "LLM engine" for a harness:
  llama.cpp, vLLM, SGLang, TensorRT-LLM, LM Studio, Ollama, LocalAI,
  etc. — with emphasis on tool-calling correctness and concurrency.
- **Model + harness combinations** that are known to work well,
  broken out by model size category.
- **MCP** (Model Context Protocol) support in local stacks.
- Notable open-source releases (OpenHarness, Hermes Agent, OpenCode,
  Aider, Plandex, llama-agent, etc.).

## Out of scope

- Purely cloud-hosted agents with no local path (e.g. closed-source
  agent SaaS). Mention only for contrast.
- Non-agentic inference benchmarks (pure tok/sec without tool-calling
  context) — link them but don't feature them.
- Generic LangChain tutorials.

## File layout

- `GUIDELINES.md` — this file.
- `YYYY-MM-DD.md` — one file per research execution.

## Report structure (per execution)

1. **Brief summary** — what changed in the local-agent stack since the
   previous report.
2. **Harnesses** — `##` section per notable harness: repo, license,
   status, what it's good at, known issues.
3. **Backends** — `##` section per notable backend with the same
   fields, plus tool-calling support matrix notes.
4. **Model + harness combinations that work well** — grouped into
   explicit size categories:
   - **Tiny** (≤4B params)
   - **Small** (4B–14B)
   - **Medium** (14B–32B)
   - **Large** (32B–70B)
   - **XL / MoE** (>70B total, incl. 100B+ MoE)

   Each entry should list: model, quantization / precision, backend,
   harness, hardware tested, what it's good for, and a source link.
5. **Open questions / follow-ups**.

## Quality rules

- Prefer primary sources: GitHub repos, release notes, official docs.
- Always note the **license** of a harness or backend.
- For any "this combo works" claim, link the source / report / blog
  it comes from. Don't assert combos that aren't published.
- Record concrete numbers (tok/sec, concurrency, tool-call success
  rate) where available; flag adjectives as unverified.
- Note whether MCP and parallel tool calls are supported — these are
  the two features most often misrepresented.
- Distinguish **inference backend** (the thing that runs the model)
  from **harness** (the loop around the model). Don't conflate them.
