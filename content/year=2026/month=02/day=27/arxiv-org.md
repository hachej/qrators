---
download_date: "2026-02-27T12:00:00.000Z"
source_url: "https://arxiv.org/pdf/2602.11988"
added_by: "Christophe"
source_type: "arxiv"
title: "Evaluating AGENTS.md: Are Repository-Level Context Files Helpful for Coding Agents?"
---

# PDF

- https://arxiv.org/pdf/2602.11988

# Summary

- This paper tests whether repository-level context files (e.g. `AGENTS.md`, `CLAUDE.md`) actually help coding agents solve real GitHub issues.
- It introduces **AGENT BENCH**: 138 Python issue instances from repositories that already include developer-written context files.
- The authors compare three settings across multiple agents/models: no context file, LLM-generated context file, and developer-provided context file.
- Main result: **LLM-generated context files usually hurt performance and increase cost** (>20% inference cost increase on average), while developer-written files provide only small average gains (~+4%).
- Context files make agents run more tests and explore more files, and agents do follow many instructions in them—but these files often fail to provide useful high-level guidance.

## Key contributions

- New benchmark (**AGENT BENCH**) for evaluating repository context-file usefulness.
- Multi-agent, multi-model empirical comparison of no-context vs generated-context vs developer-context.
- Trace-level analysis explaining behavior changes (more testing/exploration, tool-use instruction following).
- Practical guidance: prefer concise, targeted human-authored context over auto-generated repository summaries.

## Notable limitations

- Focuses on Python repositories; transfer to other languages/ecosystems is uncertain.
- Benchmark size is modest (138 instances), from early-adopter repos using context files.
- Task framing is mostly test-driven bug/feature resolution, not all software engineering task types.
- Results depend on specific agents/models/prompts and mostly single-run evaluation.
