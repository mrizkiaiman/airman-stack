# AI Learning Records

This directory stores durable records of the repository owner's AI-related learning, capabilities, judgments, workflows, and achievements.

## Record index

Use this table for a quick overview. Open the linked record for the full context, evidence, and impact.

| ID                                                  | Record                             | Date       | Status | Quick summary                                                                                            |
| --------------------------------------------------- | ---------------------------------- | ---------- | ------ | -------------------------------------------------------------------------------------------------------- |
| [AI-0001](./0001-agent-configuration-primitives.md) | Agent configuration primitives     | 2026-09-08 | Active | Rules and skills are the default mechanisms; hooks and sub-agents are understood but not daily defaults. |
| [AI-0002](./0002-ai-tool-preferences.md)            | AI tool preferences and experience | 2026-09-08 | Active | Current tool preferences, usage history, constraints, and trade-offs across AI tools.                    |
| [AI-0003](./0003-semantic-codebase-retrieval.md)    | Semantic codebase retrieval        | 2026-09-08 | Active | Semantic retrieval increases confidence in repository investigation beyond ordinary string matching.     |

Keep the table synchronized with the files in this directory. Add a row for every new record, preserve rows for replaced records, and update a row when its status changes.

## AI inventory

These tables provide a quick, readable inventory of the AI-related concepts I understand and the tools I have used. The linked records contain the full context, evidence, and impact.

### Concepts and mechanisms

| Item       | Current relationship            | Notes                                                                                                             | Record                                              |
| ---------- | ------------------------------- | ----------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| Rules      | Understands and actively uses   | Uses rules to shape AI-agent behavior.                                                                            | [AI-0001](./0001-agent-configuration-primitives.md) |
| Skills     | Understands and uses most often | Preferred mechanism for shaping AI-agent behavior and workflows.                                                  | [AI-0001](./0001-agent-configuration-primitives.md) |
| Hooks      | Understands; not used daily     | Activation behavior can sometimes fail to align with the intended behavior even when the trigger appears correct. | [AI-0001](./0001-agent-configuration-primitives.md) |
| Sub-agents | Understands; not a default      | Has not found a compelling best use case and generally prefers skills.                                            | [AI-0001](./0001-agent-configuration-primitives.md) |

### Tools used

| Tool                  | Current relationship       | Notes                                                                                                                              | Record                                           |
| --------------------- | -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Codex                 | Frequently used; favorite  | Preferred general-purpose tool.                                                                                                    | [AI-0002](./0002-ai-tool-preferences.md)         |
| Claude Code           | Former frequent user       | Used often in early 2025 as a CLI-style tool; now leans more toward Codex.                                                         | [AI-0002](./0002-ai-tool-preferences.md)         |
| Kiro                  | Currently used             | Used because of an employer-provided limit; overall experience is positive.                                                        | [AI-0002](./0002-ai-tool-preferences.md)         |
| Hermes                | Used; generally acceptable | Can sometimes feel over-engineered.                                                                                                | [AI-0002](./0002-ai-tool-preferences.md)         |
| OpenCode              | Used; generally acceptable | Often times out.                                                                                                                   | [AI-0002](./0002-ai-tool-preferences.md)         |
| OpenRouter            | Strongly valued            | Valuable because of its flexibility.                                                                                               | [AI-0002](./0002-ai-tool-preferences.md)         |
| Antigravity           | Used; favorite plan mode   | Plan mode is a favorite, but harness quality is disappointing.                                                                     | [AI-0002](./0002-ai-tool-preferences.md)         |
| Cursor                | Former first-choice AI IDE | No longer used because of cost; at the $20 price point, Codex is preferred.                                                        | [AI-0002](./0002-ai-tool-preferences.md)         |
| 9router               | Understands; rarely used   | Token savings are not very useful with Luna, which feels effectively unlimited; the relevant constraint is currently Kiro's limit. | [AI-0002](./0002-ai-tool-preferences.md)         |
| `codebase-memory-mcp` | Currently used             | Semantic retrieval subtly increases confidence in repository investigation beyond ordinary string matching.                        | [AI-0003](./0003-semantic-codebase-retrieval.md) |

Keep these inventory tables synchronized with the active records. Update the relevant row when a preference or usage pattern changes, and add a new row when a new AI-related concept or tool is established.

## Scope

Include a record only when AI is central to the subject. Valid subjects include:

- Understanding AI-agent configuration and behavior.
- Using AI tools, models, agents, skills, hooks, sub-agents, MCP servers, or related workflows.
- Building or evaluating AI-specific artifacts such as skills, prompts, agents, or workflows.
- Forming a durable judgment about how to work with AI.

Do not record a general software skill merely because AI helped acquire it. For example, learning React with AI assistance is out of scope unless the record is specifically about using AI to learn, build, or reason about React.

## File naming

Use sequential filenames:

```text
0001-short-dash-case-title.md
0002-another-title.md
```

The frontmatter `id` uses the `AI-` prefix and matches the sequence number:

```yaml
id: AI-0001
```

The `date` is the date the record is confirmed, not necessarily the date when the underlying experience happened.

## Record format

Every record uses this structure:

```md
---
id: AI-0001
date: 2026-09-08
status: active
---

# Short title

## Change

What I now understand, can do, or have successfully created in an AI-related context.

## Evidence

A concrete example, use case, artifact, decision, or self-reported prior experience that supports the change.

## Impact

How this changes the way future AI sessions should work with me.
```

`Evidence` is required. A topic being mentioned or explained is not enough to establish a record, although a clearly stated prior experience may be recorded as such.

## Replacing a record

Use `status: replaced` when a later record changes or corrects the substantive meaning of an earlier record. Keep the old file and add:

```yaml
replaced_by: AI-0004
```

Create a new record for the updated understanding. If the old record contains several related facts, restate the facts that remain current in the replacement record before marking the composite record as replaced. Repoint active inventory and context links that relied on the old record to the replacement record. Do not silently rewrite history. Minor typo and clarity fixes do not require a new record.

If a proposed change is already represented by an active record and adds no new evidence or changed state, do not create a duplicate. Point to the existing record and ask whether there is a new development to capture.

## Writing workflow

The AI should draft a record and ask for confirmation before saving it. After the record is confirmed, update `AI-CONTEXT.md` so it reflects active records only. A replaced record must not continue to be presented as current knowledge.

These records are not a session journal. Create one only for a durable change, useful baseline, meaningful achievement, or important judgment that should affect future AI sessions.
