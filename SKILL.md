---
name: otl
description: "Context-led design judgment for coding agents building, refining, redesigning, reviewing, or systematizing frontend interfaces."
metadata:
  short-description: Context-led frontend design and visual QA
---

# OTL

OTL helps coding agents make interface decisions that belong to the product, audience, content, and use context. It preserves a short reasoning chain:

`context -> Visual Thesis -> justified decisions -> shape -> implementation -> evidence`

The goal is specificity and clarity. A familiar pattern, typeface, card, gradient, or centered hero is valid when the product gives it a job. Do not turn style preferences into bans.

## Task classifier

Choose the narrowest class before choosing a workflow:

- **Local edit:** one copy, style, spacing, or state correction with no change to page hierarchy or shared language.
- **Refine:** the incumbent visual system remains while hierarchy, type, spacing, responsiveness, interaction, or polish improves.
- **Redesign:** product truth and core behavior remain while the visual world or information architecture may change.
- **New surface:** a new screen, page, or flow lacks enough incumbent visual truth.
- **Design system:** shared tokens, primitives, component language, or visual rules change across consumers.
- **Review:** the request primarily asks for critique, audit, validation, or assessment.

Use the matching playbook for every class except a local edit. A local edit uses the compact contract: affected component/context, constraint, WHY, and verification.

## Surface mode

Choose a mode for the specific surface:

- **Persuade:** attention, narrative, proof, and conversion.
- **Operate:** task completion, scanning, predictability, and state clarity.
- **Read:** comprehension, hierarchy, and reading rhythm.
- **Experience:** artifact dominance, atmosphere, and interface recession.

Mode changes priorities, not aesthetics. A developer tool landing page may be `Persuade`; the tool may be `Operate`; its documentation may be `Read`.

## Shared reasoning contract

For non-local work, keep four compact blocks. Do not create a separate artifact when its information fits one of these blocks:

1. **Context:** product, user, surface mode, constraints, content/data range, and relevant implementation facts.
2. **Direction:** one Visual Thesis and three to five decisions, each with `choice`, `because`, and observable `check`.
3. **Shape:** hierarchy, route and content ownership, composition, responsive transformation, and important states.
4. **Evidence:** visual, behavior, implementation, IA/accessibility evidence, plus blocked or unverified claims.

Use axes, content inventories, detailed scenario lists, and evidence tables only when they change a decision or substantiate a material claim.

## Visual Thesis and WHY Test

The Visual Thesis is one product-specific sentence connecting the product, user, key tension, visual mechanism, and job that mechanism performs.

Weak: "A modern, premium, minimal interface."

Strong: "Make invisible routing behavior understandable through directional relationships and calm operational surfaces, so a non-specialist can diagnose a path without reading a network diagram."

For each prominent decision, ask:

- What product fact, user need, content property, or interaction requires it?
- Is it encoding hierarchy, information, interaction, identity, or useful pacing?
- Would it still be the right decision for an unrelated product?
- Would removing it improve clarity?

If the reason collapses to a mood word, revisit the decision. Keep the test inside the decision ledger; do not run it as a second ceremony.

## Universal implementation invariants

- Read product and implementation context before changing a substantial surface.
- Preserve the existing stack, healthy primitives, semantic HTML, accessibility behavior, and ownership boundaries.
- Define route topology and content ownership before naming component sections.
- Required content does not automatically become global navigation. Keep global navigation to stable product-level destinations; place records, collections, campaigns, and editorial items in contextual content unless they are true top-level areas.
- In the default state, give each record, collection, or person one primary presentation. Repeat it only when the user takes an action or the new context adds a materially different task or evidence.
- Treat mobile as a recomposition. Test long content, important states, and touch or keyboard use when they affect the surface.
- Do not add decorative complexity that cannot survive realistic content or the mobile layout.
- Keep anti-slop diagnostic: a choice needs a product reason, and familiar patterns remain valid when they serve the task.

## Progressive disclosure

Load the matching playbook first:

- [playbooks/refine.md](playbooks/refine.md)
- [playbooks/redesign.md](playbooks/redesign.md)
- [playbooks/new-surface.md](playbooks/new-surface.md)
- [playbooks/design-system.md](playbooks/design-system.md)
- [playbooks/review.md](playbooks/review.md)

The playbook selects the smallest set of domain references that can affect the current decision. Do not read every reference by default. References contain knowledge; playbooks contain process, evidence, and stop conditions.

## Evidence and completion

Source code is not visual evidence. A screenshot is not implementation evidence. A build or detector result is not design proof. Keep evidence layers separate and make claims no stronger than what was observed.

For substantial web UI, run the visual and implementation gates described by the selected playbook. Use bounded review: one capture and critique pass, one batch of material corrections, and at most one confirmation pass. Do not manufacture a correction when no material finding exists. Stop when structural and legibility problems are resolved or explicitly blocked/out of scope, and remaining differences are preference-level.

## Small edit

For a local edit, inspect the owning component and nearby tokens, state the constraint and WHY Test, make the focused change, and run the narrowest useful verification. Skip Visual Thesis, surface mode, axes, and the substantial playbook unless the scope expands.
