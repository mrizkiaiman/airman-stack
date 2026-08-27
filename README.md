# Airman Stack

A provider-neutral collection of AI agent skills for development, productivity, and project-specific workflows.

Airman Stack packages each skill as a self-contained `SKILL.md` and makes the collection discoverable through the [`skills`](https://skills.sh/) CLI.

## Requirements

- Node.js and npm, including `npx`
- An agent or coding tool supported by the `skills` CLI

## Install from GitHub

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

Install the Oliaolio ticket workflow:

```bash
npx skills add mrizkiaiman/airman-stack --skill oliaolio-tickets
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

## Install from a local clone

```bash
git clone https://github.com/mrizkiaiman/airman-stack.git
cd airman-stack
```

The included npm scripts provide shortcuts for local discovery and installation:

```bash
npm run skills:list                 # List skills in the local repository
npm run skills:install              # Install from the local repository
npm run skills:install:all          # Install all skills
npm run skills:install:all:global   # Install all skills globally
```

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

## Add or update a skill

1. Create a directory at `skills/<skill-name>/`.
2. Add a `SKILL.md` with YAML frontmatter containing at least `name` and `description`.
3. Keep supporting files inside that skill directory when they are needed.
4. Add the skill to the appropriate group in both `skills.sh.json` and `.claude-plugin/marketplace.json`.
5. Verify discovery and formatting:

```bash
npx skills add . --list
git diff --check
```

Keep skills focused, reusable, and explicit about their safety boundaries. Prefer the smallest workflow that solves the problem without introducing project-specific assumptions unless the skill belongs in the Project-specific group.

## License

See [LICENSE](LICENSE).
