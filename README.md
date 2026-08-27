# Airman Stack

List the skills available in the stack:

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

> `--skill` accepts individual skill names. `Development`, `Productivity`, and `Project-specific` are display groupings, not installable skill names.

## Available skills

### Development

Engineering workflows, implementation guidance, and development standards.

- `code-review` — review changes against project standards and requirements
- `grill-with-docs` — stress-test a plan while capturing decisions in documentation
- `grilling` — rigorously challenge a plan or design
- `handoff` — prepare a compact handoff for another agent or session
- `implement` — implement work from a specification or ticket
- `improve-codebase-architecture` — identify and evaluate architecture improvements
- `no-use-effect` — enforce alternatives to direct React `useEffect` usage
- `shadcn` — work with shadcn/ui components and registries
- `to-spec` — turn a conversation into a structured specification
- `to-tickets` — break a plan into implementation tickets
- `ui-ux-pro-max` — apply UI/UX design intelligence to product interfaces
- `unslop` — remove generic or artificial-sounding writing

### Productivity

Research, learning, and planning workflows.

- `grill-me` — sharpen an idea through a focused interview
- `research` — investigate a topic and capture sourced findings in the repository
- `teach` — learn a skill or concept with guided explanations

### Project-specific

Workflows connected to specific project or personal integrations.

- `reflect-tickets` — list and plan Reflect tickets for review
- `oliaolio-tickets` — list active Oliaolio tickets and propose concise execution plans

## Repository layout

```text
.
├── skills/
│   └── <skill-name>/SKILL.md       # Individual skill packages
├── .claude-plugin/
│   └── marketplace.json             # Interactive marketplace grouping
├── skills.sh.json                   # skills.sh grouping metadata
├── package.json                     # Local CLI shortcuts
└── LICENSE
```

Skills intentionally live at `skills/<skill-name>/SKILL.md` so the CLI can discover them directly. The grouping files provide organization for interactive installation and browsing without changing the individual skill names.

## License

See [LICENSE](LICENSE).
