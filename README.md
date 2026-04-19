# Squad Teams

A curated library of team prompts for [Squad](https://github.com/bradygaster/squad) — the AI agent team framework for GitHub Copilot.

Each directory in this repo is a ready-made team definition. Pick a team, copy its casting prompt, and paste it into the Squad agent in your own project. Your team is cast and ready to work.

---

## What is Squad?

Squad gives you a human-directed AI development team through GitHub Copilot. You describe what you're building; Squad casts a team of named specialists — a Lead, domain experts, a Tester, Scribe, and Ralph — that live in your repo as files, persist across sessions, and share decisions.

See the [Squad documentation](https://bradygaster.github.io/squad/) and [GitHub repo](https://github.com/bradygaster/squad) for full setup instructions.

---

## How to Use a Team from This Repo

### Prerequisites

- [Node.js](https://nodejs.org/) installed
- [GitHub Copilot](https://github.com/features/copilot) access
- A project repo you want to cast a team into

### Steps

1. **Install the Squad CLI** in your target project:
   ```bash
   npm install -g @bradygaster/squad-cli
   ```

2. **Initialise Squad** in your target project:
   ```bash
   cd your-project
   squad init
   ```

3. **Browse the teams** in this repo and pick one that fits your project.

4. **Open the team's `squad-prompt.md`** and copy the passage under **Casting Prompt**.

5. **Open Copilot Chat**, select the Squad agent, and paste the casting prompt:
   ```
   copilot --agent squad
   ```

6. Squad will propose the team roster. Confirm, and the agents are cast and ready.

---

## Available Teams

| Team | Specialty | Naming Universe |
|------|-----------|-----------------|
| [Godot Game Dev](./godot-game-dev-team/squad-prompt.md) | 2D game development in Godot 4 with GDScript | Rick and Morty characters |

---

## Repository Structure

```
{team-name}-team/
└── squad-prompt.md   # Full team definition and self-contained casting prompt
```

Each `squad-prompt.md` contains:

- **Summary** — what the team builds and how they work together
- **Team Specialty** — the specific domain and technology focus
- **Naming Theme** — the universe Squad will draw agent names from
- **Tech Stack** — languages, frameworks, tools, and target platforms
- **Agents** — the full roster with roles and responsibilities
- **Conventions** — non-negotiable rules the team always follows
- **Casting Prompt** — a self-contained passage ready to paste directly into the Squad agent

---

## Adding a New Team

Open this repo in VS Code with GitHub Copilot and say:

> "Cast me a new squad team"

Copilot will guide you through the process — asking about the team's specialty, naming theme, tech stack, roles, and conventions — then generate the directory and `squad-prompt.md` automatically.

Alternatively, follow the template in [`.github/copilot-instructions.md`](.github/copilot-instructions.md) to write a prompt by hand.

---

## Contributing

Pull requests for new team prompts are welcome. Each team should:

- Live in its own `{kebab-case-specialty}-team/` directory
- Contain a single `squad-prompt.md` following the standard template
- Include Scribe and Ralph (always required by Squad)
- Have a self-contained Casting Prompt section that works without additional context

---

## License

MIT
