# Redesign

A redesign changes an existing product, not an empty canvas. Preserve what already helps users work, make the cost of change visible, and introduce a new visual language in a controlled order.

## Incumbent audit

Before proposing a direction, record:

- `KEEP`: identity, patterns, content structures, and behaviors users already understand;
- `CHANGE`: visible or behavioral problems that block the product goal;
- `REMOVE`: decoration, duplication, or conventions with no useful role;
- `INTRODUCE`: missing hierarchy, states, affordances, or product-specific expression.

Separate evidence from taste. Use analytics, support reports, content constraints, accessibility findings, existing user behavior, and the rendered interface where available. If evidence is missing, mark the assumption and keep the change reversible.

## Migration shape

Define the boundary of the redesign before implementation:

1. identify the surface and states that will change;
2. map incumbent tokens, components, and interaction behavior to the new direction;
3. preserve semantics, keyboard order, URLs, and task-critical behavior unless there is a specific reason to change them;
4. introduce the new language in one coherent surface or flow before spreading it;
5. compare the old and new rendered states at realistic content lengths and viewports.

Do not rename or replace healthy primitives merely to make the code look new. A visual change is successful when it improves comprehension, task flow, or product identity without creating avoidable migration debt.

## Redesign WHY Test

For each proposed change, answer:

- What incumbent problem does this solve?
- What user or product evidence supports the change?
- What must remain familiar for existing users?
- What is the smallest change that proves the improvement?

If a change has no answer beyond "it looks more modern", defer it until the product need is clearer.
