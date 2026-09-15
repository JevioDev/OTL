# Web Quality Gate

Implementation quality is a deterministic evidence layer separate from visual review. A screenshot can reveal hierarchy, composition, density, visual identity, rhythm, and generic AI patterns. A source and runtime audit can reveal broken semantics, missing labels, focus failures, invalid interaction primitives, content overflow risks, state persistence problems, performance hazards, localization failures, and hydration issues. Neither replaces the other.

Use this gate for substantial production web UI and for flows whose behavior or content can fail independently of appearance. Scale it to the risk: a small static surface does not need every state in this document.

## Audit loop

`inspect/test -> find deterministic defects -> fix -> verify`

Start with the actual framework, runtime, components, and content. Inspect the source and run the relevant checks, then exercise important states in the browser when available. Record what was verified and what could not be observed. Keep subjective visual critique in [visual-review.md](visual-review.md).

## Semantics and interaction

- Use native semantic elements before recreating their semantics with ARIA or generic containers.
- Match the element to the action: use a button for an action and a link for navigation so expected browser behavior is preserved.
- Give every control an accessible name that remains meaningful without its icon, color, or surrounding decoration.
- Keep focus order logical and move focus deliberately after dialogs, navigation, validation failures, and other context changes.
- Ensure keyboard users can reach, operate, cancel, and recover from the same important actions. Native controls already provide keyboard behavior; do not add manual key handlers where they would duplicate or conflict with it.
- Preserve visible focus and ensure sticky headers, footers, and overlays do not hide the focused element.
- Make async status, validation, and important state changes perceivable without forcing a user to watch animation.

Use [accessibility.md](accessibility.md) for the cross-cutting accessibility floor, contrast, reduced motion, and detailed focus review. This document checks that those concerns are implemented and verified as part of a production audit.

## Forms

Check each relevant form and field:

- labels are programmatically associated and clickable;
- names and `autocomplete` values support the field's purpose;
- `type`, `inputmode`, and keyboard hints match the expected data;
- placeholders, when used, show an example or affordance and do not replace a label;
- paste remains available, especially for codes, passwords, and externally generated values;
- invalid state is associated with the field and the inline error explains the problem and the next step;
- important validation failures move focus or otherwise make the first problem discoverable;
- submit, pending, error, success, retry, and disabled states are distinct and recoverable;
- input values are controlled with a change path or intentionally left uncontrolled;
- unsaved changes are protected when leaving would reasonably lose user work.

Do not use one form pattern for every product. The right autocomplete, validation timing, disabled behavior, and focus response depend on the task and the cost of interruption.

## Content resilience

Content is a runtime input to composition. Test the cases that are relevant to the surface:

- a long title or button label;
- localization or language expansion;
- empty content and empty arrays;
- missing or failed media;
- very short content;
- multiline or user-generated content;
- large numeric values, dates, currencies, and identifiers;
- loading, error, and retry states;
- a dense dataset or unusually many items.

Text containers must have a deliberate response to long content: wrap, grow, truncate with a useful alternative, or break words where that is appropriate. Flex and grid children must be able to shrink when the design expects them to. Do not hide a failure merely to protect an ideal screenshot.

Run only the relevant cases. A small isolated icon button does not need to render a full application state matrix; a data table or form does.

## Media and loading

- Reserve dimensions or a stable aspect ratio for images and other media when their late arrival could shift the layout.
- Choose loading priority from user value and viewport position. Critical media should not be lazy by habit; below-fold media should not block the first task without a reason.
- Provide useful alternative text for meaningful images and an empty alternative for decorative media.
- Give meaningful video or audio an appropriate control, caption, transcript, or description where required.
- Provide a still or reduced-motion experience for motion media when it could distract or create a barrier.
- Prefer media formats and loading behavior that match the product's performance budget rather than defaulting to the easiest asset.

## Navigation and state

Evaluate meaningful state for:

- reload persistence;
- back and forward navigation;
- deep linking;
- sharing and bookmarking;
- restoration after an error or interrupted request.

If users reasonably expect to reload, share, bookmark, navigate back to, or recover a state, evaluate whether it belongs in navigation or persistent state rather than ephemeral component memory. This does not mean every local state value belongs in the URL. Use the product's routing and privacy conventions.

Use real links for navigable destinations so users retain open-in-new-tab, copy-link, and history behavior. Confirm destructive actions before committing them or provide a meaningful undo window.

## Runtime and hydration

- Check server and client output for values that can differ at render time, including dates, times, locale, random identifiers, and browser-only state.
- Treat hydration warnings as defects unless the differing region is deliberately isolated and the reason is documented.
- Ensure controlled inputs have a change path and that browser-only behavior does not erase user input during hydration.
- Keep asynchronous responses associated with the current request and visible state; stale work must not overwrite a newer choice.
- Avoid layout reads or other browser-only measurement in render. Batch necessary reads and writes and prefer CSS layout when it expresses the constraint.

## Performance that affects use

Focus on observable user cost:

- unnecessary layout work or repeated measurement;
- expensive animation or main-thread work during direct manipulation;
- large unvirtualized or unpaginated collections when scrolling or input actually suffers;
- layout shift from late content, fonts, or media;
- large assets or blocking font behavior that delay the primary task;
- controlled input updates that become expensive per keystroke.

Do not turn an arbitrary threshold or optimization technique into a universal law. Virtualize, memoize, preload, or add a dependency when the measured interaction benefits and the ownership cost is justified.

## Internationalization

Where the product supports or may support multiple locales:

- format dates and times with locale-aware APIs;
- format numbers, currencies, and percentages with locale-aware APIs;
- allow for language and label expansion in layout and validation;
- keep pluralization and grammatical agreement with the locale;
- preserve brand names, code tokens, and identifiers from accidental translation where the platform supports that intent;
- check right-to-left or bidirectional content when it is in scope.

Do not burden a small static task with an enterprise localization system. Do test any locale-sensitive or user-generated content that can change geometry or meaning.

## Gate questions

- Can the user identify and operate every important action with the semantics and input methods the platform provides?
- Do forms preserve labels, data, paste, validation, and recovery?
- Does realistic content survive without clipping, overflow, or accidental layout collapse?
- Are media and loading behavior stable enough for the primary task?
- Does meaningful state survive the navigation events users reasonably expect?
- Are runtime, hydration, and async state transitions coherent?
- Is there a user-visible performance problem worth correcting?
- Are locale and language concerns handled where they affect meaning or geometry?
- Which checks were run, which states were exercised, and which limitations remain?
