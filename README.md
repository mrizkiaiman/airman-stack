# Airman Stack

A collection of agent skills for coding, planning, research, and project work. Each skill is a separate `SKILL.md` package that the `skills` CLI can install.

## Install

List the skills in the stack:

```bash
npx skills add mrizkiaiman/airman-stack --list
```

Install one skill:

```bash
npx skills add mrizkiaiman/airman-stack --skill research
```

Install several skills:

```bash
npx skills add mrizkiaiman/airman-stack \
  --skill grill-me \
  --skill research \
  --skill teach
```

Install every skill globally:

```bash
npx skills add mrizkiaiman/airman-stack --skill '*' --global
```

The `--skill` flag takes skill names, not group names. `Development`, `Productivity`, and `Project-specific` organize the list for browsing.

## Skills

### Development

Skills for writing, reviewing, and planning code.

- `code-review`: Review changes against project standards and requirements.
- `grill-with-docs`: Question a plan and record the decisions.
- `grilling`: Challenge a plan or design before implementation.
- `handoff`: Prepare a concise handoff for another agent or session.
- `implement`: Implement work from a specification or ticket.
- `improve-codebase-architecture`: Find and assess architecture improvements.
- `no-use-effect`: Replace direct React `useEffect` usage with other patterns.
- `shadcn`: Add, debug, and customize shadcn/ui components.
- `to-spec`: Turn a conversation into a structured specification.
- `to-tickets`: Break a plan into implementation tickets.
- `ui-ux-pro-max`: Plan and review product interfaces.
- `unslop`: Remove generic, artificial-sounding writing.

### Productivity

Skills for research, learning, and planning.

- `grill-me`: Improve an idea through a focused interview.
- `research`: Research a topic and save the findings in the repository.
- `teach`: Learn a skill or concept through guided explanations.

### Project-specific

Skills that connect to project or personal workflows.

- `reflect-tickets`: List and plan Reflect tickets for review.
- `oliaolio-tickets`: List active Oliaolio tickets and propose execution plans.

## Repository layout

```text
.
├── skills/
│   └── <skill-name>/SKILL.md       # Individual skill packages
├── .claude-plugin/
│   └── marketplace.json             # Interactive marketplace groups
├── skills.sh.json                   # skills.sh grouping metadata
├── package.json                     # Local CLI shortcuts
└── LICENSE
```

Skills live at `skills/<skill-name>/SKILL.md` so the CLI can find them directly. The two grouping files organize the same skills for browsing and installation.

## Upstream references

These projects are references for skill design and engineering workflows. Their skills are not included automatically.

- [mattpocock/skills](https://github.com/mattpocock/skills/tree/main/skills): Skills for engineering, productivity, and other workflows.
- [Cursor pstack](https://github.com/cursor/plugins/tree/main/pstack): A Cursor plugin built around `/poteto-mode` and engineering playbooks.

If a skill is copied or adapted, add its original URL to that skill’s `SKILL.md` or supporting documentation. Keep any required license or attribution notice.

## License

See [LICENSE](LICENSE).
