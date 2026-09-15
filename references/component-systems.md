# Component-System Integrity

An existing component system is part of the product's implementation context. Preserve its useful behavior and ownership boundaries while allowing the presentation to express the product. A component system is a means of reliable behavior, not a mandate for one visual composition.

## Inspect before inventing

Before creating a primitive or adding a dependency, inspect the smallest relevant set of:

- existing components and their composition patterns;
- existing variants and state APIs;
- semantic tokens and theme definitions;
- installed dependencies and package-manager conventions;
- project documentation, source, and generated types where available;
- the framework's routing, rendering, and accessibility conventions.

Do not guess an API from memory when the project or library exposes an authoritative source of truth. Record only the findings that change the implementation decision. Recon is useful when it reveals an extension point, an ownership boundary, or a real gap.

## Reuse behavior before appearance

Existing primitives should own behavior; composition should own presentation.

Reuse a mature primitive for focus management, keyboard navigation, dismissal, accessible naming, collision handling, portal behavior, selection logic, and other interaction infrastructure. Compose a visually distinctive surface around it when the product needs a different hierarchy, density, shape, or visual language.

Novel presentation does not justify novel accessibility infrastructure. A custom dialog, menu, drawer, select, tooltip, or popover can still use the project's established primitive underneath. Preserve the primitive's actual API and inspect its documentation; different systems may expose composition through slots, child replacement, render functions, or another mechanism.

This principle does not require using a primitive whose behavior conflicts with the task. Replace or extend it when there is a measured product problem, a missing interaction, or a clear ownership decision.

## Modification hierarchy

Use this as a contextual preference, not a mechanical approval algorithm:

1. existing primitive;
2. existing variant;
3. existing semantic token;
4. an extension to the token or variant system;
5. a local override;
6. a new reusable component;
7. a custom primitive only when the interaction genuinely requires one.

Move down the hierarchy when an earlier choice would obscure the product's needs, create an unsafe workaround, or make the API less coherent. Move up the hierarchy when the same decision is repeated or affects a shared ownership boundary.

## Repetition test

When the same local styling or behavior override appears repeatedly, ask whether it belongs in:

- a semantic token or role;
- a component variant;
- a reusable composed component;
- a shared primitive.

Do not abstract one-off visual composition prematurely. A repeated rectangle is not automatically a component, and a one-off branded surface may be better expressed by local composition. Abstract repeated behavior, state, semantics, or ownership before abstracting shape.

## Tokens and visual authorship

Semantic tokens make a system legible and maintainable: background, text, border, action, focus, selection, and state roles should have consistent meaning. They should not erase brand expression or force every surface into the same treatment.

Map product-specific values onto roles where that improves consistency. Extend the token or variant system when a value has a real repeated role. Keep a local value when the difference is intentionally local and documenting it is cheaper than creating a false global category.

Never confuse system consistency with visual conformity. Reusing behavior and tokens does not mean every page needs the same card, panel, radius, or spacing pattern. Composition still follows the content and Visual Thesis.

## Ownership and extension

Make ownership explicit when the system has layers. App composition may decide page hierarchy and product-specific relationships. Reusable components may own shared visual variants and state contracts. Primitives may own focus, keyboard behavior, positioning, and dismissal.

Before extending a shared component, check:

- whether the new state is meaningful beyond one surface;
- whether the public API names the product concept clearly;
- whether all relevant states remain operable and readable;
- whether the extension preserves current consumers;
- whether the component still has one coherent owner.

A custom primitive is justified only after checking the existing system and documenting what behavior it must own, why existing behavior is insufficient, and how it will be tested.

## Integrity review

- Did the implementation discover the existing system before choosing a pattern?
- Is interaction behavior reused even when presentation is custom?
- Are variants and tokens carrying repeated decisions instead of scattered overrides?
- Are new abstractions supported by repetition, state, semantics, or ownership?
- Is the page still specific to its product rather than visually flattened into a library default?
- Are documentation and source-of-truth checks recorded when the API was uncertain?
