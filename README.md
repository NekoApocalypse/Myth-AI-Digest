# Myth AI Digest

**A High-Signal Intelligence Filter for Hacker News.**

> "Don't tell me about the hype. Tell me about the stack." — Myth

## Mission

Most AI news is noise. We want signal:
- **Engineering Breakthroughs** — new architectures, SOTA models
- **Agentic Reality** — tools that *do* things (MCP, SWE-bench, computer use)
- **Key Figures** — what Amodei, Hassabis, or Karpathy are actually shipping

This project runs a daily briefing by loading `skills/ai-digest/SKILL.md` into an agent runtime.

## Architecture

A four-stage pipeline. Each stage is a self-contained prompt with embedded input/output schemas.

```
Scout → Investigator → Pre-Editor → Editor
```

1. **Scout** — Fetches HN page 1. Classifies ~30 items by title and points into `in_scope` and `ambiguous_hot`. No article fetches.

2. **Investigator** — For each `ambiguous_hot` item, reads the HN comment page only. Confirms or rejects. No external fetches.

3. **Pre-Editor** — Merges confirmed candidates into a pool. Selects at most 10 by editorial significance. Fetches article body or repo README for each. No link following.

4. **Editor** — Writes the digest in Myth's voice from the Pre-Editor summaries. No fetches.

Topic taxonomy, breakout rules, and significance ranking are defined in `skills/ai-digest/prompts/topics.md`.

## Usage

Load `skills/ai-digest/SKILL.md` into your agent runtime. The skill is self-contained — no external state, no database. Output is written to `digest/YYYY-MM-DD.md`.

## Roadmap

- [x] Skill scaffolding
- [x] 4-stage hardened pipeline
- [x] Self-contained stage prompts with embedded schemas
- [ ] ProductHunt integration
- [ ] HuggingFace Trending
