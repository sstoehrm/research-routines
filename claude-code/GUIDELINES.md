# Claude Code — Research Guidelines

Scope for this topic: recent additions and notable activity in the **Claude Code plugin and skill ecosystem**, plus release-note items that affect plugins / skills.

## What counts as in-scope

- **Plugins**: Anthropic-authored, partner, and community plugins in any Claude Code marketplace (anthropics/claude-plugins-official, ClaudePluginHub, Claude-Plugins.dev, ClaudeMarketplaces, ccplugins, etc.).
- **Skills**: SKILL.md-driven capabilities — bundled in Claude Code, published by Anthropic, or published by the community.
- **Release-note items** that are plugin- or skill-adjacent: hook changes, new `/slash` commands from Anthropic, SDK features, marketplace infrastructure.
- Notable **ecosystem infrastructure**: plugin package managers (ccpi), plugin directories, skills collections.

Out of scope: general Claude Code feature coverage that is not plugin/skill-relevant, and IDE-extension content that is not a plugin.

## Source discipline

- Prefer **primary sources**: `docs.claude.com` / `code.claude.com`, Anthropic blog, `github.com/anthropics/*`, release pages, plugin repo READMEs and `marketplace.json`.
- Every item must have a real URL. **Never fabricate plugin names, authors, or URLs.** If a plugin name appears only in SEO content, omit it or label it as "unverified".
- For plugin install hints, use the `/<command>` form the user actually runs (e.g. `/plugin install <name>@<marketplace>`). Do not guess marketplace names — verify against the plugin repo's `marketplace.json`.
- Dates: pin to release tag / commit / blog post date where possible. Write "date uncertain" rather than guess.

## Execution file format

One file per run: `YYYY-MM-DD.md`, dated the day the run executed (UTC).

Required structure:

1. **Run metadata** — date, window covered.
2. **TL;DR** — 4-8 sentence summary of what's new.
3. **Release-note highlights** — plugin- and skill-relevant items from the last 2-3 months of Claude Code releases.
4. **Plugins** — grouped by origin:
   - Official Anthropic marketplace
   - Partner / ecosystem
   - Notable community
   Each plugin: name, author, 2-3 sentence description, invoke/install hint, URL.
5. **Skills** — bundled (in Claude Code CLI), official Anthropic repo, and community collections. Each: name, purpose, invoke hint, URL.
6. **Ecosystem notes** — directories / package managers / relevant meta-changes.
7. **Caveats** — flag anything that could not be verified against a primary source.

## House style

- Be concrete: say what the plugin/skill *does* in one line, not what it *promises*.
- Call out when something is **bundled** vs. **marketplace** vs. **community** — install path matters.
- If a plugin / skill's value rests on a paid service (Composio, Datadog, etc.), say so.
- Prefer counts that come from primary-source counters (GitHub stars, marketplace listing size) over claimed rankings in blog posts.
