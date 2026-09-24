# Visual Review

Visual review is an evidence loop after implementation, not a final compliment pass. A screenshot is evidence; source code is only an implementation hypothesis. This is separate from the deterministic implementation audit in [web-quality.md](web-quality.md): visual evidence cannot prove semantics, state persistence, hydration, or runtime behavior, and source inspection cannot prove visual hierarchy or feel.

Use this file as the review protocol for `playbooks/review.md` and as the bounded finish pass for other playbooks. It does not replace the task classifier, Visual Thesis, or implementation gate.

## Capture

Use the project's existing browser or preview workflow. When tooling permits, capture:

- a representative desktop viewport;
- a representative mobile viewport;
- a key interactive state, such as open navigation, validation, selected content, or an error;
- a long-content or dense state when geometry depends on content length.

Use real or realistic content. A screenshot with placeholder text cannot prove hierarchy, wrapping, or density.
Record the evidence level honestly: `screenshot reviewed`, `rendered preview reviewed`, or `source-only - visual review blocked`.

## Critique order

Review in this order so low-impact polish does not distract from structural problems:

1. hierarchy: what is seen first, second, and last;
2. task clarity: whether the next action and system state are obvious;
3. composition: balance, masses, alignment, whitespace, and rhythm;
4. typography: role contrast, measure, wrapping, metrics, and legibility;
5. color: semantic roles, contrast, salience, and theme behavior;
6. components: consistency, boundaries, states, and repetition;
7. identity: what belongs specifically to this product;
8. responsive behavior: order, overflow, density, and touch use;
9. motion: causality, interruption, and reduced-motion behavior.

## Self-critique prompts

- What is the first thing the eye sees? Is that what should dominate?
- What is the second thing? Does it support the first?
- Does every major section have a reason to exist?
- Are there too many competing focal points?
- Is any decoration carrying no information or personality?
- Are cards being used where grouping by spacing would work?
- Are borders compensating for weak hierarchy?
- Is muted text too muted?
- Does type have hierarchy without depending only on font size?
- Does every section use the same composition by habit?
- Could this page belong to an unrelated SaaS product?
- What is unique to this product?
- What would a senior designer remove?
- What feels accidental or like an LLM default?

## Correction protocol

Write no more than three findings for the first pass, ordered by impact. Each finding should describe the visible problem, why it matters to the user's task, and the smallest useful correction. Fix the highest-impact finding, then re-check all affected viewports and states.

Do at least one correction pass for any substantial UI change. Stop when the hierarchy is clear, the correction no longer creates a new problem, and remaining differences are intentional tradeoffs rather than unexamined defaults.

If browser or screenshot tooling is unavailable, inspect the closest rendered preview and report the limitation. Do not claim that source inspection is equivalent to visual QA.

## Ship gate

The surface is ready when:

- its dominant element matches the primary user goal;
- its Visual Thesis is visible in the composition without being explained;
- the visual language is coherent but not mechanically repetitive;
- content and states survive realistic length and responsive changes;
- text, visible focus, contrast, and reduced-motion presentation remain usable;
- at least one evidence-based correction has been made.

The separate implementation quality gate must also confirm semantics, keyboard operation, state behavior, platform behavior, and runtime quality before the surface is called ship-ready.
