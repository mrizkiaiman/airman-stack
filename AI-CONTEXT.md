# AI Context

This file is a derived, current-state summary for future AI sessions. The records in [`learning-records/`](./learning-records/) are the source of truth. This file should summarize active records only and must not be treated as a mastery score.

Last reviewed: 2026-09-08

## Current AI-related understanding and workflows

### Agent configuration

- Understands and actively uses rules to shape AI-agent behavior.
- Understands and most often uses skills as the preferred mechanism for shaping AI-agent behavior and workflows.
- Understands hooks, but does not use them daily because agent activation can sometimes fail to align with the intended behavior even when the trigger appears correct.
- Understands sub-agents, but has not found a compelling best use case and generally prefers skills.

### Current tool preferences

| Tool | Current relationship | Important context |
| --- | --- | --- |
| Codex | Frequently used; favorite | Preferred general-purpose tool. |
| Claude Code | Former frequent favorite | Used often in early 2025 as a CLI-style tool; now less preferred than Codex. |
| Kiro | Currently used | Used because of an employer-provided limit; overall experience is positive. |
| Hermes | Used and considered acceptable | Can sometimes feel over-engineered. |
| OpenCode | Used and considered acceptable | Often times out. |
| OpenRouter | Strongly valued | Preferred when model flexibility matters. |
| Antigravity | Favorite plan-mode experience | Harness quality is disappointing. |
| Cursor | Former first-choice AI IDE | No longer used because of cost; Codex is preferred at the $20 price point. |
| 9router | Understood but rarely used | Token savings are not very useful when using Luna, which feels effectively unlimited; the relevant constraint is currently Kiro's limit. |

### Repository search

- `codebase-memory-mcp` is currently used for semantic, retrieval-augmented codebase search.
- Its benefit is subtle but increases confidence in AI-assisted repository investigation compared with ordinary string matching alone.

## Working preferences for future AI sessions

- Prefer skills over sub-agents unless a clear delegation benefit is demonstrated.
- Do not recommend hooks by default; explain the activation behavior and expected benefit first.
- Prefer Codex for general-purpose AI work unless another tool's specific strength is relevant.
- Consider OpenRouter when model flexibility is a priority.
- Use `codebase-memory-mcp` for repository discovery and relationship-aware search when available.
- Keep claims conservative: familiarity, preference, and usage should not be presented as mastery unless a later record provides stronger evidence.

## Active records

- [AI-0001 — Understanding agent configuration primitives](./learning-records/0001-agent-configuration-primitives.md)
- [AI-0002 — Current AI tool preferences and experience](./learning-records/0002-ai-tool-preferences.md)
- [AI-0003 — Using semantic codebase retrieval](./learning-records/0003-semantic-codebase-retrieval.md)
