# Claude Code — Research Guidelines

Scope for this topic folder. Every execution should produce one dated
report under `claude-code/` that conforms to these guidelines.

## What belongs here

- New or meaningfully updated **Claude Code plugins**
  (MCP-based extensions installed via `/plugin`).
- New or meaningfully updated **Claude Code skills**
  (markdown-based workflow bundles, user- or plugin-provided).
- New **marketplaces** or large curated collections.
- Changelog entries that affect plugin / skill behaviour
  (e.g. skill loading semantics, `/skills` UI, `disableSkillShellExecution`,
  MCP `maxResultSizeChars`).
- Notable related CLIs that interact with Claude Code
  (ccpi package manager, ultrareview, etc.).

## Out of scope

- Generic Claude.ai features that don't touch Claude Code.
- API-only features that aren't exposed through Claude Code plugins
  or skills.
- Self-promotion from single authors without traction (no users /
  stars / installs).

## File layout

- `GUIDELINES.md` — this file.
- `YYYY-MM-DD.md` — one file per research execution.

## Report structure (per execution)

1. **Brief summary** — what's new in the plugin / skill ecosystem
   since the last report.
2. **Plugins** — `##` section per notable plugin with:
   - `Source:` repo and/or marketplace link
   - `Install:` the install path (marketplace, `/plugin`, manual)
   - `License:`
   - `What it does / why it matters:`
   - `Notes / caveats:` (permissions, hooks used, token impact)
3. **Skills** — same structure, grouped separately.
4. **Changelog items that affect plugins/skills** — concise bullets
   with source links.
5. **Open questions / follow-ups**.

## Quality rules

- Prefer primary sources: the plugin/skill repo, the Anthropic docs
  (`code.claude.com/docs`), or the official changelog.
- When citing an aggregator, check the linked repo before including.
- Record the **license** for every plugin / skill listed.
- Do not recommend a skill/plugin that requires unusual permissions
  without calling that out explicitly.
- Note whether a plugin is in the **Anthropic-managed marketplace**
  (`anthropics/claude-plugins-official`) vs. a third-party one.
- Flag any skill that modifies CLAUDE.md, hooks, or settings.json —
  those have outsized effects.
