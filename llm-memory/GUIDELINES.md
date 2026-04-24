# LLM Memory — Research Guidelines

Scope for this topic folder. Every execution should produce one dated
report under `llm-memory/` that conforms to these guidelines.

## What belongs here

- Papers, preprints, and blog posts about **memory systems for LLMs**,
  with a bias toward work that is practical for **local / open-weight
  models** (i.e. can be reproduced on a workstation or single-node GPU,
  no closed API required).
- New open-source **memory frameworks / libraries** (Letta, mem0, Zep,
  MemOS, supermemory, etc.) or substantial releases of existing ones.
- New **benchmarks or evaluations** for long-term memory
  (LoCoMo, LongMemEval, MemTrack, MemoryBench, etc.).
- Architectural ideas that affect memory even if not sold as "memory"
  (e.g. Titans/MIRAS, test-time training, KV-cache compression,
  state-space models with persistent state).

## Out of scope

- Generic RAG tutorials that do not introduce a new technique.
- Memory features that only exist in closed commercial products
  (ChatGPT memory, Gemini memory) unless they are accompanied by
  a paper or reproducible description.
- Marketing posts without concrete technical content.

## File layout

- `GUIDELINES.md` — this file, the contract for the topic.
- `YYYY-MM-DD.md` — one file per research execution. Never overwrite
  previous runs; always add a new dated file.

## Report structure (per execution)

1. **Brief summary** — 3–6 sentences, what changed in the field since
   the last report.
2. **Items** — one `##` section per paper / release / post, with:
   - `Source:` one or more links
   - `Date:` publication date if known
   - `Why it matters for local models:` one paragraph
   - `In-depth insights:` key claims, architecture, numbers,
     limitations
3. **Open questions / follow-ups** — short list.

## Quality rules

- Always link the **primary source** (arXiv, GitHub, official blog).
  Secondary coverage is optional and must be labelled as such.
- Prefer peer-reviewed or preprint sources to vendor marketing.
- Record concrete numbers (benchmark scores, context lengths, param
  counts) instead of adjectives.
- When a paper claims a benchmark win, note the baseline and the gap.
- Call out whether weights / code are released and under what license.
- If something is only relevant to closed models, say so explicitly
  and justify inclusion.
