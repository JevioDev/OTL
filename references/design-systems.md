# Design System Selection

Keep these categories separate:

- a design system is a coordinated set of principles, tokens, components, patterns, accessibility behavior, and governance;
- a component library is reusable implementation primitives;
- a visual aesthetic is a surface treatment or art direction;
- a frontend framework is the technical runtime and rendering model.

Tailwind, a React library, glassmorphism, and a color palette are not interchangeable with a design system.

## Selection sequence

1. Describe the product's interaction model: operations, forms, data comparison, content reading, creation, exploration, or another model.
2. Identify platform, ecosystem, compliance, accessibility, localization, density, and theming requirements.
3. Audit the repository for existing primitives, tokens, dependencies, and patterns before adding anything.
4. Compare candidate systems by behavior, states, accessibility, content patterns, and implementation fit.
5. Choose an official or established system when its interaction model and ecosystem match the product.
6. Compose or extend it only where product-specific needs are real. Replace primitives only when their behavior or visual language causes a measured problem.
7. Use a custom visual layer when the product is brand-heavy, editorial, object-focused, or not well served by an operational system. Reuse accessible behavior even when surface styling is custom.

Relevant systems may include Material, Fluent, Carbon, Primer, Polaris, Atlassian, Spectrum, GOV.UK, USWDS, or another system that fits the product. The list is a starting point, not an approved-style list.

## Decision rule

Choose a design system because its interaction model matches the product, not because its screenshots match the moodboard.

## Integration discipline

- preserve the existing stack unless the product has a concrete reason to change;
- inspect component APIs and token semantics before duplicating them;
- map brand values onto semantic roles instead of scattering one-off colors;
- keep component states complete: hover, active, focus, disabled, loading, error, and selected where relevant;
- document deliberate deviations and their reason;
- avoid mixing multiple systems with overlapping primitives without an ownership plan;
- do not introduce a dependency for one decorative effect.

## Custom does not mean inconsistent

A custom system still needs decisions about naming, tokens, spacing, type roles, state behavior, focus, responsive constraints, and ownership. The visual language may be distinctive, but the interaction model should remain learnable.
