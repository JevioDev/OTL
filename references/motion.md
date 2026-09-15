# Motion

Motion is a communication channel. It can explain causality, confirm an action, direct attention, preserve a spatial relationship, or express a product personality that the context supports. It is not a default layer of polish, and it is not a substitute for a clear state.

## Motion decision process

Run these questions in order. Early answers may remove the need for motion entirely.

### 1. Should this move at all?

Consider interaction frequency, user intent, task urgency, repeated exposure, and whether the change is already clear from the resulting state. High-frequency and keyboard-driven actions usually need immediate state changes with little or no ceremony. Occasional or meaningful moments may support more expression when it helps the user.

Do not turn frequency into universal thresholds. A product's operating rhythm and audience determine the cost of delay.

### 2. What job does it perform?

Give each non-trivial animation one primary job:

- feedback: confirm that the system received an input;
- continuity: connect content before and after a change;
- attention: bring a meaningful change into view;
- orientation: explain navigation or a spatial relationship;
- expression: mark a product-specific or meaningful moment.

If the answer is only that it looks polished, remove it or make the state change static. Data users are reading or acting on should not move merely to create atmosphere.

### 3. How frequently will the user encounter it?

Expression budget should generally decrease as frequency increases. Repeated actions should stay quick and stable. Medium-frequency transitions can provide brief continuity. Rare, first-time, or milestone moments can carry more personality if the user can remain in control.

### 4. What must remain understandable?

Identify the state, object identity, focus, selection, and spatial relationship that must survive the change. Anchored overlays should feel related to their trigger. A detail view may preserve the identity of a selected thumbnail. A sheet should have a comprehensible relationship to the edge it enters from. A global modal does not need to pretend it came from a local point.

This is causal geometry: motion should preserve the cause-and-effect relationship that helps the user understand what changed. It is a perceptual goal, not a requirement to use a particular `transform-origin` implementation.

### 5. Must it be interruptible?

Assume that users may act again before the transition ends. Check open -> close, hover -> leave, expand -> collapse, drag -> reverse, submit -> retry, and navigate -> navigate again where relevant.

Use state-driven transitions that can retarget from the current state. Cancel stale asynchronous work where appropriate. Preserve focus and content through reversal. Do not make the user wait for an animation to finish before the interface accepts a correction.

CSS transitions, platform behavior, or a spring-based mechanism may help, but the requirement is coherent interruption, not a particular tool.

### 6. What is the least complex adequate mechanism?

Prefer the mechanism that fully communicates the job while preserving performance, accessibility, and the product's visual language:

- CSS or native behavior for a simple visual state;
- a browser transition or entry mechanism for predetermined motion;
- a platform animation API when programmatic control is needed;
- a motion library or spring when dynamic values, layout continuity, exit coordination, or gesture interruption genuinely require it.

Do not add a library for a fade, and do not reject a library when it is already part of the system or solves a real interaction problem. Inspect existing motion primitives before introducing another path.

### 7. What happens under reduced motion?

Respect `prefers-reduced-motion` and preserve meaning when movement is reduced. Replace non-essential travel, parallax, scale, and looping effects with a static state, a gentler opacity or color change, or no animation. Keep feedback and orientation understandable without requiring motion.

Reduced motion is a behavioral variant, not an afterthought. Check entry, exit, late loading, repeated updates, and error states under the reduced setting.

### 8. How will it be reviewed?

Review the actual rendered interaction, not only the declaration. Check the first frame, perceived response, landing position, causal relationship, interruption, repeated use, focus, touch capability, and reduced-motion variant. Slow the result down or inspect it frame by frame when timing is hard to judge. For gestures, use a real device where possible.

## Motion categories

Use these categories to describe the job, not to fill a quota:

- feedback: press, selection, progress, or completed action;
- continuity: content replacement, expansion, collapse, or shared identity;
- attention: a meaningful update that would otherwise be missed;
- orientation: navigation, overlay relationship, or spatial movement;
- expression: a deliberate moment earned by the product context.

One animation may serve more than one category, but naming a primary job keeps competing effects under control.

## Timing and properties

Choose timing from task urgency, distance, frequency, component scale, and the existing design language. The user should perceive the response early enough to trust it, and the transition should finish before it becomes a gate on the next action. Reuse existing duration and easing tokens when they exist; do not create a parallel scale or import fixed values as universal OTL rules.

Prefer compositor-friendly properties such as `transform` and `opacity` when they express the change without hiding a necessary layout update. Layout properties may be the correct mechanism for an expanding region or content whose geometry must be measured; use them deliberately, keep the work bounded, and test for jank. Explicitly list transitioned properties rather than using an unbounded `transition: all`.

Use the origin and direction that communicate the relationship. A trigger-anchored popover, a centered modal, and a bottom sheet have different spatial causes. Do not force one origin or easing recipe on all of them.

## Direct manipulation

For drag, swipe, resize, and gesture-driven motion, preserve continuity between the user's input and the object. Avoid arbitrary jumps, make cancellation and snap-back legible, and use velocity, resistance, or friction only when it communicates intent or a boundary. Pointer capture, multi-input protection, and touch-axis ownership belong in the interaction and mobile-platform implementation when relevant.

Provide non-gesture alternatives unless the gesture is essential. Native scrolling and snapping are preferable when they fully express the product behavior.

## Motion review

- Does motion have a job the static state cannot perform as clearly?
- Is the amount of ceremony proportional to frequency and task urgency?
- Does the user see an immediate response to direct input?
- Does the transition preserve object identity, focus, selection, and causal geometry?
- What happens when the user reverses or repeats the action before completion?
- Is the mechanism as simple as the interaction allows and no simpler?
- Does reduced motion preserve meaning and control?
- Was the rendered result checked at realistic content, viewport, and input conditions?

Motion should make the interface easier to understand or more specifically itself. When it does neither, deletion is a valid and often useful correction.
