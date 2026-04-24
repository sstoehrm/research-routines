# LLM Memory — Research Guidelines

Scope for this topic: papers, releases, and notable engineering work on **memory for LLMs, with a bias toward local / open-weights deployment** (Llama, Qwen, Mistral, DeepSeek, Gemma, Phi, etc.).

## What counts as in-scope

- **Architectural memory**: long-context attention, sparse / linear attention, SSM / recurrent hybrids, test-time-learned memory modules, KV-cache compression and quantization.
- **External memory systems**: agent memory layers (Mem0, Letta/MemGPT, Zep, MemMachine, HippoRAG, A-MEM, LangMem, Memobase, …), vector + graph hybrid stores, episodic/semantic stores.
- **Benchmarks**: LOCOMO, LongMemEval, BABILong, RULER, needle-in-a-haystack variants, Aider long-context evals.
- **Tooling / runtimes**: KV-compression libraries (kvpress, turboquant), llama.cpp / vLLM / SGLang memory features, MLX memory features.

Out of scope: generic long-context *marketing* claims with no open method, closed-model-only features unless they inform open research, and RAG pipelines that are not explicitly memory-oriented.

## Source discipline

- Prefer **primary sources**: arXiv, official project blogs, GitHub READMEs and release notes.
- Every claim should have a clickable URL in the execution file. No link → the claim does not ship.
- Dates must be the most recent *verifiable* date (paper revision, release tag, blog post). If uncertain, write "date uncertain" rather than guess.
- If an item only appears in SEO / aggregator content, flag it as medium- or low-confidence inline.

## Execution file format

One file per run: `YYYY-MM-DD.md`, dated the day the run executed (UTC).

Required structure:

1. **Run metadata** — date, window covered, any scope notes.
2. **TL;DR** — 4-8 sentence summary of what's new, what matters for local deployment.
3. **Papers** — one subsection per paper, containing:
   - Title, authors/org, date, URL(s)
   - 3-5 sentence summary oriented toward local deployment
   - One-line "key mechanism"
4. **Releases / news** — same shape as Papers, for non-paper items.
5. **State of the field** — 3-4 sentences on where the field is moving and what is still unsolved.
6. **Caveats** — anything the author was unsure about (e.g. unusual arXiv ID, blog with uncertain provenance, model names the author could not independently verify).

## Cadence and selection

- Target 6-10 high-quality items per run. Prefer quality over volume.
- Look back roughly 6 months; include older anchor works only if they are still actively cited or updated.
- De-duplicate: if two sources cover the same release, cite the primary one.

## House style

- Lead with the concrete mechanism; avoid marketing language ("revolutionary", "game-changing").
- Call out trade-offs explicitly (token cost, VRAM, accuracy contested).
- When benchmark numbers are disputed, say so and link both sides.
