# Myth AI Digest

**A High-Signal, Genetic Intelligence Filter for Hacker News.**

> "Don't tell me about the hype. Tell me about the stack." — Myth

## 🎯 Mission
Most AI news is noise ("10 ChatGPT prompts for marketing"). We want **signal**:
- **Engineering Breakthroughs** (New Architectures, SOTA Models).
- **Agentic Reality** (Tools that *do* things: MCP, SWE-bench).
- **Key Figures** (What Amodei, Hassabis, or Karpathy are actually saying).

This project automates the role of a **Technical Intelligence Analyst** who scans HN, filters for these "Genetic Traits," and produces a daily briefing.

## 🧬 Architecture: The Genetic Skill
Instead of a fragile scraper, we use a **LLM-driven Protocol**:

1.  **Scout (The Filter):**
    - Scans `news.ycombinator.com`.
    - Applies `skills/ai-digest/prompts/scout.md` to identify "Candidate" items based on abstract concepts (not just keywords).
2.  **Audit (The Verification):**
    - Fetches the content/comments.
    - Verifies claims (is it code or just a blog?).
3.  **Editor (The Synthesis):**
    - Synthesizes `skills/ai-digest/prompts/editor.md`.
    - Writes the final digest to `digest/YYYY-MM-DD.md`.
4.  **Memory:**
    - `data/stash.json`: Tracks the lifecycle of every item to prevent duplicates and detect "sleeper hits."

## 🚀 Usage
*Currently manual trigger via OpenClaw Agent:*

```bash
# In the OpenClaw workspace
openclaw run skills/ai-digest
```

## 🗺️ Roadmap
- [x] Genetic Prompt Design
- [x] Skill Scaffolding
- [ ] Automated Cron Trigger (Daily 09:00 UTC+8)
- [ ] ArXiv Integration (Research Papers)
- [ ] HuggingFace Trending (Model Weights)
