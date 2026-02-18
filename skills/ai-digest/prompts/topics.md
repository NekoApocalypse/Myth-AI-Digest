# Topics & Taste

This document is the canonical definition of editorial scope for the Myth AI Digest.
It is referenced by Scout, Investigator, and Pre-Editor. Do not reinterpret it; apply it as written.

---

## In Scope: Topic Taxonomy

Classify an item as **in scope** if it substantively addresses one of the following:

1. **Frontier Models** — New SOTA releases or major capability updates. LLM, image, audio, multimodal.
   Examples: new model releases, major version updates, benchmark records broken.

2. **Agents & Agentic Tools** — Software that enables AI to *act*, not just respond.
   Examples: MCP, computer-use, browser agents, SWE-bench results, code execution frameworks.

3. **Novel Architecture** — Research that challenges or extends the Transformer paradigm.
   Examples: SSMs, Mamba, JEPA, new attention mechanisms, post-training techniques.

4. **Hardware & Inference** — Local inference breakthroughs, new chips, quantization, efficiency gains.
   Examples: running models on-device, new GPU/NPU announcements, GGUF/quantization tooling.

5. **Key Figures** — Direct technical statements, papers, or projects from: Amodei, Hassabis, Karpathy, Altman, LeCun, Bengio, Sutskever, or equivalents.
   Note: the names are a heuristic, not a hard filter. Unknown authors with strong technical substance qualify too.

---

## Breakout Override

Include regardless of topic category if **both** conditions are met:
- **Points > 100** AND **Comments > 20** at time of scan
- AND the content is substantive (not a repost, not a press release)

This catches high-signal items that don't fit neat categories: novel AI applications in biology, physics, history, or security; controversial technical debates; unexpected utility tools.

---

## Out of Scope: The Noise

Reject the following regardless of point count:

- "N ways to use ChatGPT for [non-technical task]" — productivity listicles
- Generic AI doom/acceleration op-eds with no technical content (unless by a Key Figure)
- Corporate press releases without code, architecture details, or reproducible results
- Thin wrappers: products built on top of APIs with no novel contribution
- Funding announcements, valuations, acquisitions (unless the technical implication is significant)

---

## Significance Ranking

When prioritizing between qualifying items (used by Pre-Editor when pool exceeds 10):

1. **Reproducible + accessible** — Has code, weights, or a working demo. Beats papers alone.
2. **Architectural** — Changes how something is built, not just how well it performs.
3. **Points relative to age** — High velocity (many points in few hours) outranks high absolute points.
4. **Breadth of implication** — "Enables local agents" beats "slightly better benchmark score."
5. **Key Figure signal** — Direct technical output from a key figure carries extra weight.
