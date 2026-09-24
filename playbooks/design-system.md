# Design System Playbook

Use when changing shared tokens, primitives, component language, or the visual rules consumed by multiple surfaces.

## Process

1. **Context:** inventory consumers, ownership boundaries, tokens, primitives, states, accessibility behavior, and migration constraints.
2. **Direction:** define the system problem and three to five decisions with observable checks across more than one consumer.
3. **Shape:** specify token roles, component variants, state behavior, responsive rules, and fallback/migration behavior.
4. **Implement:** update shared ownership boundaries first, then representative consumers; avoid local exceptions that conceal system defects.
5. **Evidence:** test representative components and states, inspect at least two consumers, and record compatibility or adoption gaps.

## Load

Always load `references/component-systems.md` and `references/design-systems.md`. Add `accessibility`, `typography`, `color`, or `motion` when those primitives are affected.

## Stop

Stop when the rule is coherent across representative consumers, states remain accessible, and known migration gaps are explicit rather than silently patched.
