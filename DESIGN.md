# AI Digest: System Design

## 1. Core Philosophy: Semantic & Genetic
This project is not just a scraper; it is an **intelligence filter**.
- **Semantic:** We look for *meaning* (e.g., "new architecture"), not just keywords (e.g., "Transformer").
- **Genetic:** The system prompt is the DNA. It evolves. We define abstract traits of "high signal" content so the system adapts to new jargon without code changes.
- **Temporal:** We track the *lifecycle* of a story (velocity, debate ratio) to catch sleepers and ignore flash-in-the-pan hype.

## 2. The Genetic Curator (System Prompt)
*This is the "DNA" of the agent.*

**Role:** Technical Intelligence Analyst.
**Objective:** Separate engineering breakthroughs from marketing noise.

**Scan Strategy (The Signals):**
1.  **Frontier Shifts:** New models, architectures (SSM, MoE), or training paradigms.
2.  **Agentic Reality:** Tools that enable *action* (MCP, Browser Use, SWE-bench), not just chat.
3.  **The Architects:** Statements from key figures (Amodei, Hassabis, Karpathy, etc.). *Note: The list of names is a heuristic, not a filter.*
4.  **Vibe Check:** Safety research, jailbreaks, and alignment failures that imply real-world fragility.

**Breakout Rules (The "Viral" Override):**
- **Developer Swarm:** GitHub repos with >100 points in <4 hours. (Implies utility).
- **The Debate:** Comments > Points * 0.8. (Implies controversy/nuance).
- **Unexpected Utility:** Novel applications of AI in non-obvious domains (Bio, History, Physics).

## 3. Mechanisms

### A. The Source
- **Primary:** Hacker News (Front Page + Page 2).
- **Future:** HuggingFace Trending, ArXiv (filtered).

### B. Temporal Logic (State Management)
We maintain a state file (`history.json`) to track:
- `firstSeen`: When did it hit the front page?
- `peakScore`: Max points.
- `velocity`: Points per hour.
- `status`: `new` -> `pending` -> `digested` -> `archived`.

**Deduplication Rules:**
1.  **Identity:** Match by Item ID.
2.  **Resurface:** Only re-notify if a "digested" item doubles its score or comments (indicating a "second wind" or major update).
3.  **Decay:** Archive items after 7 days.

## 4. Architecture
- **Runtime:** Node.js Script (`digest.js`) triggered via Cron.
- **Intelligence:** LLM Call (OpenClaw) to parse/filter titles.
- **Storage:** Local JSON (sqlite later if needed).
- **Output:** Markdown summary sent via Telegram/Messaging.
