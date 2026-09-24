---
name: otl
description: "Design judgment for coding agents: derive interface decisions from product context, build a coherent visual language, and validate rendered and implementation quality. Use for new UI, redesigns, design systems, and frontend polish; do not use it as a generic aesthetic preset."
metadata:
  short-description: Context-led frontend design and visual QA
---

# OTL

OTL is a design reasoning skill for coding agents. It helps an agent make visual decisions that belong to the product, audience, content, and use context instead of repeating a familiar AI interface pattern.

The name honors Otl Aicher. Carry forward his respect for legibility, systems, and meaningful signs; do not turn Swiss typography, strict grids, or any other historical style into an OTL default. The inspiration is philosophical, not stylistic: OTL borrows systems thinking, not Swiss aesthetics.

## Operating principle

Design must emerge from context. Every noticeable decision is a hypothesis about what helps this product work. Before implementation, the agent should be able to complete:

> I chose X because Y about this product, user, content, or interaction requires it.

This is an internal quality test, not a requirement to expose a design essay to the user. When the sentence cannot be completed without saying that something is modern, premium, clean, creative, or fashionable, revisit the decision.

Do not turn the skill's anti-patterns into permanent bans. A centered hero, a card, a gradient, a serif, a monospace face, or an established design system is correct when the context earns it. The question is whether the same choice would be made for an unrelated product.

### WHY Test

For every prominent choice, ask:

- What product fact, user need, content property, or interaction requires this choice?
- Is it encoding information, hierarchy, interaction, identity, or useful pacing?
- Would I make the same decision for an unrelated product?
- Would removing it improve the composition or make the task less clear?

If the answer collapses to "modern", "premium", "clean", "creative", or "on trend", treat the choice as unproven. Keep the test internal unless the user asks for the reasoning.

## When to use this skill

Use this skill when an agent is asked to:

- build or redesign a web page, product surface, dashboard, website, or frontend flow;
- improve a real product UI such as an operational workflow, form, table, editor, settings area, or mobile flow;
- establish or repair a visual system, component language, or responsive composition;
- improve visual quality, distinctiveness, hierarchy, motion, or interaction polish;
- review an implemented interface and make it ship-ready.

Treat a task as substantial when it changes a complete surface or flow, responsive composition, visual system, or more than one interactive state. For a small, purely mechanical UI edit, apply only the relevant principles and do not invent a full design process.

### Size the task before choosing the process

Use the lightest process that can answer the design question:

- **Small edit:** one localized style, copy, spacing, or state change. Inspect the owning component and nearby tokens, apply the relevant WHY Test, then run the narrowest useful check.
- **Substantial surface:** a page, flow, responsive composition, visual-system change, or multiple states. Use the full workflow and both quality gates.
- **Unclear scope:** begin with a short recon. Promote the task to substantial if the change affects hierarchy, responsive behavior, shared primitives, or more than one state.

Do not produce a design brief for a small edit. Do not compress a substantial redesign into a collection of local CSS tweaks.

## Workflow

### 1. Understand

Start with two compact reads: the product context and the implementation context. Mark assumptions explicitly and do not treat an existing repository as an empty canvas.

#### Product Read

Establish:

- product or subject matter;
- audience, expertise, and use environment;
- primary user goal and most important action;
- surface type and information hierarchy;
- content characteristics, including length, density, language, and data variability;
- incumbent visual language and recognizable brand assets;
- platform, technical, accessibility, and performance constraints;
- references supplied by the user and what they are evidence for;
- existing versus new design work.

#### Implementation Recon

For a substantial implementation task, inspect only what will affect the decision:

- framework, package manager, styling architecture, and installed dependencies;
- existing design system, semantic tokens, component primitives, and ownership boundaries;
- typography source, icon system, motion primitives, and accessibility primitives;
- responsive conventions, routing/state conventions, and relevant documentation or source of truth.

Record the useful constraints and extension points, not a giant inventory. This recon prevents a design decision from accidentally forking healthy behavior or solving a system problem with local overrides.

If the repository contains an existing product, audit it before changing its visual language. Separate `KEEP`, `CHANGE`, `REMOVE`, and `INTRODUCE`, then define how the new direction will coexist with or migrate from the incumbent system. Do not discard a recognizable identity because it differs from personal taste.

If a missing fact would lead to two materially different design directions, ask one short question. Otherwise infer conservatively and proceed.

For a substantial surface, write a compact surface contract before coding: visitor mode (`Persuade`, `Operate`, `Read`, or `Experience`), primary task, proof or content the surface must carry, realistic content/data range, route topology, important states, and finish criteria. Keep this separate from durable product facts and from treatment details.

### 2. Write a Design Read

Describe the interface's character in one or two sentences without naming CSS treatments. Include the audience tension it must resolve. For example: "A developer-facing network utility that must feel technically credible while remaining legible to operators who do not think in network primitives."

Then set a small set of design axes from 0 to 5. Use the axes to change decisions, not to decorate a plan:

| Axis | Low end | High end |
| --- | --- | --- |
| Compositional variance | predictable alignment and repeated regions | deliberate shifts, asymmetry, or editorial pacing |
| Information density | spacious, few simultaneous choices | compact, comparison-oriented, data-rich |
| Expression | quiet and transparent | visibly authored and emotionally specific |
| Motion intensity | static or feedback-only | choreographed transitions and spatial continuity |
| UI familiarity | conventional controls and patterns | novel interaction or custom visual grammar |

Choose only axes that affect the surface. High expression or variance never excuses weak hierarchy. High familiarity is often the right decision for critical or repeated workflows.

For each selected axis, write the consequence in plain language (for example, “high density means comparison rows need stronger scan anchors”). If an axis does not change a later decision, remove it.

### 3. Define a Visual Thesis

Write one product-specific sentence before coding. It should describe the visual mechanism and the job it performs, not a mood word. A useful thesis names the subject, the user need, and the source of visual character.

Weak: "A modern, premium, minimal interface."

Stronger: "Make invisible routing behavior understandable through directional relationships and calm operational surfaces, so a non-specialist can diagnose a path without reading a network diagram."

Spend boldness in one or a few places. If the thesis makes typography the identity, keep motion, backgrounds, and component silhouettes quieter. If the interaction is the expressive element, do not also make every surface loud.

Turn the thesis into a short decision ledger before coding. Record three to seven high-signal decisions, each with `choice`, `because`, and `check`. The check must be observable in the rendered result or implementation (for example, “long labels remain scannable at 320px”). This keeps the thesis operational instead of rhetorical.

#### Optional divergence

When the brief is ambiguous and the choice is high-value, explore 2-3 genuine directions before implementation. Name the axis of divergence: composition, hierarchy, density, interaction model, typography role, visual metaphor, or motion language. Changing only color, radius, shadow, or one font is cosmetic variation, not a new direction. Keep this optional for normal tasks.

### 4. Shape the composition

Before choosing components, decide:

- what the eye sees first and why;
- the reading and action order;
- dominant and supporting visual masses;
- where space expands, compresses, or becomes quiet;
- the alignment system, grid behavior, and any intentional tension;
- how the composition transforms on small screens;
- which content deserves grouping and which should remain unboxed.

Components serve composition. Composition must not become a container for a library of components. Sketch a rough page map or wireframe when the surface is substantial.

Choose one primary action and no more than two or three secondary actions for the first view. Define the route topology before naming component sections. Required source content may need to appear on the page without becoming a global navigation route, and a section anchor is not automatically a product-level destination.

### 5. Build a design language

Choose typography, color roles, spacing, shape, borders, elevation, iconography, and motion as a coherent response to the thesis. Reuse existing primitives when they are healthy. Select a real design system because its interaction model, accessibility behavior, platform, and ecosystem fit the product - never because its screenshots resemble a moodboard. OTL is framework-independent: use the project's existing React, Vue, Svelte, plain HTML/CSS, native component system, or legacy stack unless a change is necessary and justified.

Read only the relevant references from the routing table below. Do not load every reference by default.

### 6. Implement with discipline

Use the existing stack unless a change is necessary. Check dependencies before adding one. Keep semantic HTML, responsive behavior, actual content length, and states in scope: loading, empty, error, disabled, focus, and success where relevant. Do not add decorative complexity that cannot survive the content or the mobile layout.

Before creating a new primitive, inspect existing components, variants, tokens, dependencies, and authoritative documentation. Preserve behavior and accessibility infrastructure while composing the presentation around it. Existing primitives own behavior; composition owns presentation. This does not require every surface to look like a library or a standard card.

Copy is part of the interface. Use concrete user language and action labels. Remove filler such as "unlock the power of", "seamlessly", "next-generation", or "elevate" when it does not communicate a product fact.

### 7. Review the result

For any substantial UI task, rendered review is a required completion step whenever a browser, preview, or screenshot tool is available. Record the evidence level and do not treat source inspection as a substitute.

After implementation, open the running result and inspect it as a user. If the environment supports screenshots or browser automation, capture at least one representative desktop and one mobile viewport, plus relevant states. Use one bounded review pass to inspect all target captures together, fix material findings in a batch, then run one confirmation pass. Check the screenshots for hierarchy, balance, type, spacing, contrast, density, alignment, repetition, identity, and responsive degradation.

Code is not visual evidence. Rendered output is visual evidence. Never trust JSX, templates, CSS, or a clean detector result alone to validate visual design.

#### VISUAL EVIDENCE LOOP

`render -> inspect -> critique -> correct -> re-check`

This loop owns hierarchy, information architecture, composition, typography, rhythm, density, identity, responsive visual behavior, and accidental AI defaults. Correct in this order when useful: remove, simplify, recompose, clarify hierarchy, correct behavior, refine treatment, then add polish. Never polish a structurally weak decision.

#### IMPLEMENTATION QUALITY GATE

`inspect/test -> find deterministic defects -> fix -> verify`

Run the gate separately from visual review for substantial production web UI. It owns semantics, interaction behavior, accessibility, content resilience, platform behavior, relevant performance, and state behavior. Use [references/web-quality.md](references/web-quality.md), [references/accessibility.md](references/accessibility.md), and [references/mobile-web.md](references/mobile-web.md) as relevant. A screenshot cannot prove these properties, and source inspection cannot prove visual quality.

#### Content Stress Test

Before shipping a substantial surface, test the cases that can change its geometry or meaning: long or localized text, empty content, missing media, large values, multiline content, loading, error, or a dense dataset. Test only states relevant to the surface. A composition validated only with ideal content has not been validated.

Run both gates to completion. If screenshots or browser automation are unavailable, use the closest available rendered preview and state the evidence level (`rendered preview reviewed` or `source-only - visual review blocked`); do not claim visual QA was completed from source code alone.

Keep an evidence matrix for substantial surfaces. For each material capability, record the strongest evidence actually obtained, its status (`proven`, `partial`, `unverified`, or `blocked`), and the remaining limitation. Static presence, build success, runtime behavior, rendered appearance, IA topology, and accessibility are separate evidence layers. A report must not use one layer to claim another.

For stateful surfaces, include named scenario coverage in the matrix: entry, discovery/input, inspection, recovery, responsive, and keyboard/accessibility as applicable. A feature is not runtime-proven because its handler or label appears in source.

Classify findings before correcting them:

1. **Structural:** wrong hierarchy, broken responsive composition, missing state, or unusable interaction. Fix first.
2. **Legibility:** type scale, contrast, wrapping, focus visibility, or density problems.
3. **Treatment:** color nuance, border, radius, shadow, icon alignment, or motion refinement.

After each correction, re-check the affected viewport and state. Stop when the decision ledger checks pass, no material unresolved structural or legibility findings remain, and treatment changes would be preference-only. Any remaining structural or legibility finding must be explicitly blocked or out of scope.

### 8. Ship

Before finishing, confirm that the final surface has a clear dominant element, a stable hierarchy, usable controls, realistic content behavior, accessible focus and contrast, reduced-motion behavior, and one coherent visual language. Remove or justify any non-essential flourish during the final pass.

## Progressive disclosure

Read a reference only when the task makes it relevant:

| Situation | Read |
| --- | --- |
| Selecting, pairing, loading, or changing typefaces | [references/typography.md](references/typography.md) |
| Planning page hierarchy, information architecture, grid, responsive layout, or section rhythm | [references/composition.md](references/composition.md) |
| Defining palette, themes, semantic color, or contrast roles | [references/color.md](references/color.md) |
| Adding, reviewing, or substantially changing animation | [references/motion.md](references/motion.md) |
| Designing an interaction-heavy flow or direct manipulation | [references/interaction.md](references/interaction.md) |
| Reconciling an existing component ecosystem or creating a primitive | [references/component-systems.md](references/component-systems.md) |
| Choosing Material, Fluent, Carbon, Primer, Polaris, Spectrum, GOV.UK, or another system | [references/design-systems.md](references/design-systems.md) |
| Reviewing generic patterns or checking repeated work across projects | [references/anti-slop.md](references/anti-slop.md) |
| Auditing an incumbent product or planning a redesign/migration | [references/redesign.md](references/redesign.md) |
| Implementing or auditing keyboard, focus, contrast, semantics, or reduced motion | [references/accessibility.md](references/accessibility.md) |
| Implementing mobile/touch/PWA/platform behavior | [references/mobile-web.md](references/mobile-web.md) |
| Shipping a substantial production web UI or running a deterministic implementation audit | [references/web-quality.md](references/web-quality.md) |
| Performing the final rendered review or correction pass | [references/visual-review.md](references/visual-review.md) |

For a redesign, read `redesign.md`, `anti-slop.md`, and `visual-review.md` together. For a new design system, read `design-systems.md` and `component-systems.md` plus only the specific token references needed. For substantial production web UI, pair `web-quality.md` with the platform and accessibility references that apply.

## Minimum internal contract

For any substantial surface, keep a compact working note with:

1. facts and assumptions;
2. Implementation Recon findings when the task is substantial;
3. surface contract;
4. Design Read;
5. selected axes and their consequences;
6. Visual Thesis;
7. composition map;
8. page-level content inventory and primary home for each major entity;
9. three to seven high-signal decisions with `choice`, `because`, and observable `check`;
10. page-level IA preflight findings and disposition;
11. evidence matrix and claim audit;
12. named scenario coverage and results;
13. visual and implementation QA targets, evidence status, and findings;
14. corrections made.

Do not output this contract by default when the user only needs a small implementation. Use it to make the work coherent and auditable.

For small edits, collapse this to three notes: affected component and constraint, the WHY Test for the change, and the verification performed.

## Hard quality rules

- Context outranks habit, trend, library defaults, and the skill author's taste.
- Never reject a typeface, color, layout, or library only because it is popular or familiar.
- Do not use cards, pills, gradients, labels, numbering, borders, shadows, or monospace as decoration without a content or interaction role.
- Avoid repeated hero, section, typography, component, and animation patterns across unrelated work unless the product genuinely shares the same need.
- Existing primitives own behavior; composition owns presentation. System consistency must not become visual conformity.
- Accessibility is the quality floor, not an aesthetic direction.
- A clean detector or lint result cannot replace a rendered visual review, and a good screenshot cannot replace an implementation quality audit.
