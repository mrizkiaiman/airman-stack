---
name: record
description: Capture a durable AI-related learning, capability, achievement, preference, workflow, or judgment in this repository. Use this skill whenever the user asks to record, log, save, track, capture, or add something they learned or experienced with AI, even if they provide the input as a casual list or in Indonesian. Draft the English record first, ask for explicit confirmation, then update learning-records/, its index and inventory tables, and AI-CONTEXT.md.
disable-model-invocation: true
argument-hint: "What AI-related learning, experience, preference, or achievement should be recorded?"
---

# Record AI learning

Use this skill to turn a user's AI-related experience into a durable, Git-versioned record for future AI sessions.

The repository's source of truth is `learning-records/`. `AI-CONTEXT.md` is a derived summary of active records. The user may speak Indonesian or another language in chat, but every file written to the repository must be clear English.

## Workflow

### 1. Read the current state

Before drafting or writing anything, read:

- `learning-records/README.md` — the authoritative scope, schema, numbering, index, inventory, and replacement rules.
- `AI-CONTEXT.md` — the current derived context.
- The filenames under `learning-records/` — to determine the next sequence number from the highest existing filename.

Do not assume the next number from memory, and do not reserve a number for a draft.

### 2. Filter for AI relevance

Record only a durable change where AI is central. Valid subjects include:

- Understanding AI-agent configuration or behavior.
- Using AI tools, models, agents, skills, hooks, sub-agents, MCP servers, or related workflows.
- Building or evaluating AI-specific artifacts such as skills, prompts, agents, or workflows.
- Forming a durable judgment about working with AI.

Do not record a general software skill merely because AI helped acquire it. For example, learning React with AI assistance is out of scope unless the actual learning is about using AI to learn, build, or reason about React.

If the input is out of scope, say so briefly and do not draft or write a record. If the boundary is ambiguous, ask one focused clarification question.

### 3. Check whether the input is record-worthy

A record must describe a durable change, useful baseline, meaningful achievement, or important judgment that should affect future AI sessions. Do not turn a session summary, a list of names, or something merely mentioned into a claim of mastery.

Evidence is required. Acceptable evidence includes:

- A demonstrated explanation or decision.
- A concrete use case or workflow the user has used.
- An artifact the user created or evaluated.
- A clearly stated prior experience or preference, recorded conservatively as self-report.

If the user has only encountered a concept and gives no evidence of understanding or use, explain what is missing and ask for a concrete example. Do not invent evidence.

### 4. Decide whether this is new, additive, or corrective

Use one record for one meaningful change. Group closely related facts only when they describe one coherent change; avoid creating a record for every individual tool name.

- **Already recorded / no-op:** If the input is materially equivalent to an active record and adds no new evidence or changed state, do not draft or write another record. Tell the user where it is already captured and ask whether they have a new development to add.
- **New or additive:** create a new sequential record.
- **A changed current preference or workflow:** create a new record when the change is durable, and update the affected inventory/context entry.
- **A correction or substantive replacement:** create a new record, keep the old record, and mark the old one as `status: replaced` with `replaced_by: AI-NNNN`. Remove the old current claim from `AI-CONTEXT.md`.
- **A composite record replacement:** If only one claim in an older record containing several related facts changes, create a replacement record that restates the still-current facts and incorporates the corrected claim. Mark the entire composite record as replaced so active records cannot contain conflicting current claims.
- **A minor clarification or typo:** edit the existing file only if no substantive meaning changes.

Keep historical records. Never silently rewrite a substantive change.

### 5. Draft before writing

Translate the user's meaning into natural English while preserving product names, code identifiers, and technical terms. Keep the certainty level conservative. Do not add skills, mastery, dates, or usage frequency that the user did not state or demonstrate.

Show the complete proposed record before changing any repository file. Use this structure:

```md
---
id: AI-NNNN
date: YYYY-MM-DD
status: active
---

# Short title

## Change

What changed in the user's AI-related understanding, capability, judgment, preference, workflow, or achievement.

## Evidence

The concrete evidence supporting the change, including when it is explicitly self-reported experience.

## Impact

How future AI sessions should work differently.
```

Also explain any intended changes to:

- the record index row;
- the concepts or tools inventory tables, if applicable;
- `AI-CONTEXT.md`;
- an older record, if this is a replacement.

Ask for explicit confirmation before writing. Treat responses such as `yes`, `approve`, `save it`, or an equivalent clear approval as confirmation. If the user asks for changes, revise the draft and ask again. If the user declines, make no repository changes.

### 6. Write only after confirmation

After explicit confirmation:

1. Re-read the current filenames and files if the conversation may have changed them. Determine the next number from the highest existing filename.
2. Create `learning-records/NNNN-short-dash-case-title.md` using the confirmed English draft.
3. Add a row to the **Record index** table in `learning-records/README.md` with the linked ID, confirmation date, status, and a concise faithful summary.
4. Update the **Concepts and mechanisms** or **Tools used** inventory table when the record establishes a new item or changes an existing relationship. Keep rows for replaced records and update status when needed.
5. Update `AI-CONTEXT.md` as a derived current-state summary:
   - include only active current knowledge and preferences;
   - add the active record link;
   - update working preferences or tool notes when relevant;
   - remove or revise claims that a replacement invalidates;
   - do not add a mastery score or session journal.
6. For a replacement, update the old record's frontmatter and its index row:

```yaml
status: replaced
replaced_by: AI-NNNN
```

If the old record is composite, the new replacement record must preserve the still-current facts from the old record while correcting the changed fact. Repoint every active inventory and context link that relied on the old record to the replacement record; do not leave current rows pointing only to a replaced record. This keeps the active record set internally consistent without deleting history.

Do not write anything before the confirmation boundary, including the new record, a placeholder row, or a context draft.

### 7. Validate the result

After writing:

- Confirm the new filename and frontmatter ID use the same sequence number.
- Confirm the date is the confirmation date.
- Confirm `Evidence` is present and faithful to the user's claim.
- Confirm every new or changed Markdown link points to an existing file.
- Confirm `AI-CONTEXT.md` does not present replaced knowledge as current.
- Confirm all new repository content is in English, while preserving technical names.
- Run `git diff --check` when available.

Report the files changed and the validation result briefly.

## Output discipline

- Speak to the user in their preferred chat language.
- Write repository content in English.
- Prefer one useful record over several shallow records.
- Never infer mastery from exposure.
- Never write a record or update derived context without explicit user confirmation.
- Keep the detailed record as the history and `AI-CONTEXT.md` as the compact current snapshot.
