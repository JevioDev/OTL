# OTL

**Design judgment for AI agents.**

Most coding agents can write CSS. The harder problem is knowing why a visual decision belongs to one product and becomes generic in another.

OTL gives coding agents a structured design reasoning process: understand the product and implementation context, form a Visual Thesis, make decisions with a WHY Test, implement in the existing stack, and correct the result through independent visual and implementation-quality gates.

## Why OTL exists

AI-generated interfaces often repeat familiar structures: the same hero, cards, section rhythm, typography behavior, and decorative treatment. Aesthetic novelty is easily confused with design quality.

OTL addresses that failure through reasoning, not another set of style defaults. A gradient, card, serif, monospace face, or centered hero can all be right when the product gives them a job.

## How it works

`Product Read + Implementation Recon -> Design Read -> Visual Thesis -> Shape -> Design Language -> Implement -> Visual Evidence Loop + Implementation Quality Gate -> Correct -> Ship`

The **Visual Thesis** is one product-specific sentence describing how the interface should communicate. The **WHY Test** asks what product fact, user need, content property, or interaction requires each prominent decision. The rendered review then checks the result on actual desktop and mobile viewports when the environment permits it.

## Core ideas

- context before aesthetics;
- composition before components;
- decisions need reasons;
- anti-slop is diagnosis, not a blacklist;
- rendered output is evidence;
- implementation quality is a separate evidence layer;
- specificity matters more than novelty.

## Example

Bad: "Use monospace because this is a developer product."

OTL: "Use monospace for machine-generated identifiers where character shape aids scanning; keep primary interface text in a highly legible UI face."

## Installation

The repository root is the skill. Clone it once, then place that directory at the host's skills location:

```sh
git clone https://github.com/JevioDev/OTL.git
```

- **Claude Code:** `.claude/skills/otl/`
- **Codex:** `~/.codex/skills/otl/` (on Windows: `%USERPROFILE%\\.codex\\skills\\otl\\`)
- **Cursor:** `.cursor/skills/otl/`

The same folder works across hosts: keep `SKILL.md`, `references/`, and `agents/` together. After installation, invoke it as `$otl` where the host supports explicit skill invocation. If you installed an earlier release, update its invocation to `$otl`.

## Structure

```text
SKILL.md       entrypoint and workflow
references/    task-specific guidance, loaded progressively
agents/        host UI metadata
```

References are intentionally split by decision type. Load only the files relevant to the current task; redesigns additionally use `redesign.md`, `anti-slop.md`, and `visual-review.md`.

## Why Otl Aicher

OTL is named for Otl Aicher's systems-oriented approach to visual communication, legibility, and meaningful signs. The inspiration is philosophical, not stylistic: OTL borrows systems thinking, not Swiss aesthetics, and does not attempt to reproduce Aicher's visual style.

## Influences

OTL is informed by Anthropic's frontend-design, Impeccable, and Taste Skill. Its own focus is the combination of design reasoning, Visual Thesis, contextual decision tests, and a rendered correction loop.

## License

MIT. It keeps a small tooling skill easy to reuse, fork, and adapt while preserving attribution.
