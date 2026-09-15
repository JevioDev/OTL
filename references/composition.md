# Composition

Design the page as a hierarchy of attention and action before designing a set of components. The composition should tell the user what matters, where to begin, what can be compared, and what can wait.

## Page map

Write a short map for the surface:

- dominant element and its job;
- first action or reading step;
- supporting explanation, evidence, or navigation;
- secondary actions and lower-priority content;
- quiet zones where the interface can rest;
- states that may change the geometry;
- mobile transformation.

For a substantial surface, sketch the masses rather than a component inventory. For example:

```text
[navigation]        [context / status]

[dominant task or content]   [supporting evidence]

[next action]        [secondary details]
```

This is a thinking tool, not a prescribed layout. The correct map may be a table, canvas, form sequence, article, split view, or a single focused action.

## Information architecture boundaries

Name the role of every prominent region before styling it. Keep these roles distinct:

- **Global navigation:** stable routes that orient the whole product;
- **Contextual navigation:** links or controls for the current collection, record, task, or location;
- **Featured content:** selected material that represents the subject without becoming a route;
- **Promotion:** an invitation or announcement whose purpose is to drive attention or conversion.

Do not place a featured record in global navigation because it is visually prominent. Do not repeat the same entity across sections unless each appearance supports a different user task and adds clear context. A page map should make the relationship between routes, entities, and actions explicit.

For each major region, ask: what does this let the user do, what content model does it represent, and where should the user go next? Remove regions that have no distinct answer. Check the page as a whole for duplicated records, empty columns, orphaned headings, and controls that look like navigation but only decorate a feature.

Before implementation, make a page-level content inventory. Mark each entity as a route, a reusable record, a collection, an editorial explanation, or a utility state. Give each entity a primary home and allow secondary appearances only when the surrounding action or context changes. This prevents a discovery page from repeating the same records merely to fill sections.

Set a section budget for the primary task. Every added region must earn its space by introducing a new action, relationship, or piece of evidence. If two regions answer the same question, combine them or make their distinction explicit. Validate the complete page with realistic data before tuning individual components.

### Page-level IA preflight

Run this check before visual polish and again after the page is populated:

1. **Route check:** every global navigation item maps to a stable destination or documented product utility. A featured collection, campaign, or single record belongs in contextual navigation or content unless it is a true top-level area.
2. **Entity repetition check:** list repeated records, collections, and people across the page. Keep a repeat only when its action or context changes; otherwise use one primary home and link back to it.
3. **Region role check:** label each major region as navigation, content, evidence, utility, or promotion. If a decorative specimen or illustration can be mistaken for a record, label its role or remove it.
4. **Space check:** every column, empty state, heading, and control must have a content or interaction role at the widest and narrowest tested widths.
5. **Mobile affordance check:** when controls or content intentionally scroll horizontally, expose that behavior through clipping, spacing, arrows, or an accessible name; do not make overflow look accidental.

Record failures as structural findings and resolve them before treatment refinements.

## Alignment and rhythm

Choose an alignment system from the content. Left alignment often supports scanning and long labels; centered alignment can support a focused moment or ceremonial content; a mixed system can express an intentional relationship. Do not center content by habit.

Establish section rhythm from changes in meaning. A dense comparison area may need a quiet lead-in; an action-heavy form may need short transitions; an editorial page may need pacing between stories. Repeating identical padding and section templates everywhere erases hierarchy.

Use whitespace to show grouping before adding a border. Use borders when they communicate separation, a boundary, a data relationship, or an interaction state. Avoid making every group a floating box.

## Grid and variance

Select a grid that matches the subject and content. A strict grid is useful for comparison, alignment, and repeated operations. Variable or asymmetric placement is useful when one story, object, or path must dominate. Variance should clarify a relationship; random offsets only add noise.

Set the variance axis deliberately:

- low variance: stable columns, repeated row behavior, conventional reading order;
- medium variance: one or two meaningful shifts, distinct lead region, controlled overlap;
- high variance: a custom spatial grammar that still has obvious anchors and keyboard order.

The user must never have to decode the layout before understanding the task.

## Component boundaries

Create a component boundary when a unit has a repeated behavior, a semantic role, a state model, or an ownership boundary. Do not create a component merely because a rectangle exists. A component can render without a card, and multiple components can share one unboxed section.

Cards are appropriate when the content is independently scannable, selectable, movable, or needs an explicit boundary. Avoid nested cards when spacing, a divider, a heading, or a background shift already communicates the relationship.

## Responsive composition

Treat mobile as a recomposition, not a scaled desktop:

- preserve the primary task and remove secondary competition;
- define what reorders, collapses, scrolls, or becomes a separate view;
- keep controls and labels legible at the longest realistic content;
- prevent horizontal overflow unless the data itself requires it;
- retain the design thesis at small widths even if the layout becomes simpler;
- check focus order after visual reordering.

Stable dimensions matter for toolbars, grids, charts, and tiles. Reserve enough space for loading, focus, long text, and state changes so the layout does not jump.

## Composition critique

Ask:

- What is the first thing the eye sees, and should it be?
- What is the second thing, and does it support the first?
- Are there competing focal points without a reason?
- Is every major section necessary for the user's job?
- Could a section be grouped by spacing instead of a card or border?
- Does each change in rhythm correspond to a change in meaning?
- Does the mobile order still tell the same story?
- Are global, contextual, featured, and promotional regions visibly and semantically distinct?
- Does each repeated entity serve a different task with added context?
- Does every grid column have a content or interaction role, including at narrow widths?
