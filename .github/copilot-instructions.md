# Copilot Instructions — Squad Teams Repo

## Purpose

This repository is a library of prompts for casting agentic teams using [Squad](https://github.com/bradygaster/squad). Each directory represents one specialist team and contains a single `squad-prompt.md` file that defines that team's composition, specialty, naming theme, tech stack, and casting context.

When someone clones or forks this repo, they can pick up any `squad-prompt.md`, send the casting prompt to the Squad agent in their own project, and immediately have a ready-made, well-contextualised team.

---

## Repository Structure

```
{team-name}-team/
└── squad-prompt.md   # Full team definition and casting prompt
```

Directory names follow the pattern `{kebab-case-specialty}-team` (e.g., `godot-game-dev-team`, `python-data-science-team`, `devops-platform-team`).

---

## Creating a New Squad Team

When a user says something like **"cast me a new squad team"**, **"create a team for X"**, or **"add a new team"**, guide them through the following process.

### Step 1 — Ask Required Questions

Ask both of these up front (you may ask them together in a single message):

1. **Team specialty** — What domain, technology, or purpose will this team focus on?
   - Examples: "Godot game development", "Python data science and ML", "React/Node.js full-stack", "DevOps and cloud infrastructure"

2. **Naming theme** — What theme should the agents' names be drawn from? This becomes the Squad naming universe for this team.
   - Examples: "Classic sci-fi characters", "Greek mythology", "Jazz musicians", "Arthurian knights", "Golden-age Hollywood directors"

### Step 2 — Ask Follow-up Questions

Based on the specialty, ask any additional questions needed to produce a high-quality prompt. Use your judgement on what is relevant — do not ask for information you can reasonably infer. Typical follow-ups include:

- What languages, frameworks, or tools does this team primarily work with?
- Are there specialist roles needed beyond the standard set (Lead, domain specialist(s), Tester)?
- What types of projects will this team most commonly tackle?
- Are there key conventions or non-negotiables this team must follow? (e.g., "always TDD", "GDScript only, no C#", "prefer functional patterns")
- Is there a specific target platform or runtime environment?

### Step 3 — Generate the Prompt

Once you have enough information:

1. Create a directory named `{kebab-case-specialty}-team/` at the repo root.
2. Create `squad-prompt.md` inside it using the template below.

---

## `squad-prompt.md` Template

Every file follows this exact structure. Fill in all `{placeholder}` values based on what the user described.

```markdown
# {Team Name}

## Summary

{A rich, 2–4 sentence natural-language description of what this team builds, what they specialise in,
and how they work together. Write this as if you were briefing a new team member on day one.
This also forms the basis of the Casting Prompt at the bottom.}

---

## Team Specialty

{Domain or technology focus — be specific. e.g., "Godot 4 game development using GDScript and the
built-in physics and scene system" rather than just "game development".}

## Naming Theme

**Universe:** {Theme name, e.g., "Classic sci-fi protagonists"}
**Style:** {A brief note on the feel — e.g., "Iconic, recognisable names from 70s–90s sci-fi cinema"}

## Tech Stack

- {Primary language or engine}
- {Key frameworks or libraries}
- {Target platform(s) or runtime}
- {Any notable tooling — linters, test frameworks, CI, etc.}

## Agents

| Name | Role | Core Responsibilities |
|------|------|----------------------|
| {CastName} | Lead | Architecture decisions, code review, scope management, sprint ceremonies |
| {CastName} | {Domain Specialist Role} | {Primary domain work for this specialty} |
| {CastName} | {Domain Specialist Role 2} | {Secondary specialist work, if warranted} |
| {CastName} | Tester | Test authoring, edge case discovery, quality assurance |
| Scribe | Memory Manager | Decisions log, cross-agent context, session history |
| Ralph | Monitor | Work queue, backlog triage, keep-alive |

> Add or remove specialist rows as needed. Scribe and Ralph are always present and must not be removed.

## Conventions

- {Key convention 1 — e.g., "Follow the official Godot GDScript style guide for all node and variable naming"}
- {Key convention 2}
- {Key convention 3}
- {Add more as relevant to the specialty}

## Casting Prompt

> Copy the passage below and send it to the Squad agent (via `copilot --agent squad`) in your target
> repo to cast this team. Run `squad init` first if you haven't already.

{A self-contained natural-language passage, 3–6 sentences, that tells the Squad agent exactly what
team to cast. Include the specialty, the naming theme, the tech stack, key roles, and any important
conventions. This should be complete enough to paste directly without additional context.

Example:
"I'm building a Godot 4 game in GDScript. Cast me a team that specialises in game design and
implementation using Godot's scene system, physics, and GDScript. Use classic sci-fi characters as
the naming universe. The team needs a Lead, a gameplay programmer, a UI/UX specialist, and a tester.
The team should always follow the official Godot GDScript style guide and prefer composition over
inheritance for scene design."}
```

---

## Guidelines

- **Scribe and Ralph are always included** in every team. Never omit them regardless of team size or specialty.
- **Team directory names** use kebab-case with a `-team` suffix that reflects the specialty (e.g., `rust-systems-team`, not `team-for-rust`).
- **Agent count:** Aim for 3–4 specialist agents (including Lead and Tester) plus Scribe and Ralph. Only add an agent if the role is genuinely distinct — avoid splitting responsibilities artificially.
- **The Casting Prompt section** must be self-contained. Someone should be able to copy it and paste it directly to the Squad agent without needing to read the rest of the file.
- **Naming theme consistency:** Names within a team should all come from the same universe and feel cohesive together. Squad allocates specific names during casting, but record the universe and style so it can be replicated.
- **Be specific in the specialty and conventions.** Vague prompts produce generic teams. The more concrete the domain context, the better Squad can shape each agent's charter.
