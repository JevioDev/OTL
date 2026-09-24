# Redesign Playbook

Use when product truth, content, and core functionality remain, but the visual world or information architecture may be replaced.

## Process

1. **Context:** audit incumbent behavior, content model, brand commitments, routes, shared primitives, and known user problems. Record `KEEP`, `CHANGE`, `REMOVE`, and `INTRODUCE` when they clarify the migration.
2. **Direction:** write a new Visual Thesis that names the product tension and communication mechanism; state what is kept, changed, removed, and introduced.
3. **Shape:** define route topology, content ownership, first-view hierarchy, responsive transformation, and migration boundaries before restyling. Preserve semantics, keyboard order, URLs, and task-critical behavior unless there is a specific reason to change them.
4. **Implement:** preserve required semantics and behavior while replacing presentation deliberately.
5. **Evidence:** compare representative old/new states, exercise material flows, inspect desktop/mobile, and record evidence limits.

## Load

Load `references/composition.md` and `references/visual-review.md` by default. Add `anti-slop` when replacing the visual language or genericity is a material risk; add `component-systems` or `accessibility` when shared behavior changes.

## Stop

Stop when the new direction is coherent, product-specific, usable in the preserved flows, and no material unresolved structural or legibility findings remain.
