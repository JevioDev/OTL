# Interaction Craft

Interaction craft asks how the interface should feel while it is being operated. It connects product intent to feedback, state changes, spatial relationships, and recovery. It is broader than animation: a useful interaction can be immediate and static, while motion is one possible way to explain a change.

## Start with the interaction contract

For each important action, identify:

- the user's input and what counts as an intentional activation;
- the immediate acknowledgement that the system received it;
- the resulting state, including pending, success, failure, and retry where relevant;
- the next useful action or recovery path;
- what must remain stable while the operation is in progress.

Do not make users infer whether a click, tap, drag, submit, or navigation request was received. Feedback may be a state change, an enabled or disabled control, inline status, focus movement, or motion. Choose the least distracting signal that makes the result clear.

## Frequency and expression

The more frequently an interaction happens, the less ceremony it should impose. Treat frequency as a design input, not as a universal numeric threshold.

| Frequency | Interaction character |
| --- | --- |
| High frequency | Immediate, stable, low ceremony, and easy to repeat. Keep repeated delight minimal. |
| Medium frequency | Brief feedback and useful continuity. The user should understand what changed without waiting for a performance. |
| Rare or milestone | A larger expressive budget may be appropriate when it marks meaning, progress, or a consequential moment. |

Expression budget should generally decrease as interaction frequency increases. A rare success moment can carry personality; the same flourish on every row action becomes friction. If a product is playful or ceremonial, the balance may move, but the reason still comes from the product and the user's task.

## Immediate feedback

Direct manipulation should acknowledge input promptly. Check press, selection, drag, submit, toggle, and navigation states separately.

- Press and tap feedback should begin at the point of contact when the platform supports it.
- A selected state should be visible without requiring a second action or an animation to finish.
- A submit should expose pending state, preserve useful input, and make failure recoverable.
- A drag or resize should track the user's action continuously enough to preserve trust.
- Navigation should make the destination and current location clear.

Do not prescribe a particular scale, color, duration, or sound. The right feedback depends on platform, component geometry, interaction frequency, and the product's visual language. An interaction that is already obvious may need no extra flourish.

## Interruptibility

Design state transitions for new input arriving before the previous transition finishes. The interface should represent the latest valid state, not replay a script that assumes the user waits.

Consider at least the relevant reversals:

- open, then immediately close;
- hover, then immediately leave;
- expand, then collapse before completion;
- drag in one direction, then reverse;
- submit, then retry or cancel;
- navigate, then navigate again;
- start an async action, then receive an error or stale response.

Keep controls coherent during interruption. Retarget a transition from the current state, cancel stale work where appropriate, and preserve focus, selection, and content unless the product requires otherwise. Never make the user wait for an ornamental transition before they can correct an action.

Motion-specific implementation choices belong in [motion.md](motion.md). The interaction question comes first: what state should be true if the user changes their mind now?

## Causal geometry

Motion and layout should preserve causal geometry when a spatial relationship helps the user understand a change.

- An anchored popover should feel related to its trigger.
- A thumbnail-to-detail change should preserve identity when the same object is being followed.
- A sheet should have a comprehensible relationship to the edge or surface it enters from.
- A local action may produce a global result without pretending that a global modal came from a precise local point.

This is a perceptual principle, not a requirement to expose transform implementation details. If spatial continuity would mislead or add ceremony, use a clear state change instead.

## Direct manipulation

For drag, swipe, resize, and gesture interactions:

- preserve continuity between the pointer or touch position and the object;
- avoid arbitrary jumps when a gesture starts or changes direction;
- respect velocity when it communicates intent, such as a quick dismissal;
- use resistance or friction at a meaningful boundary instead of an unexplained hard stop;
- capture the active pointer and protect against conflicting inputs where the platform requires it;
- define cancellation, completion, and snap-back behavior;
- provide tap, click, keyboard, or another clear alternative unless the gesture is essential to the task.

Use the browser's native scrolling and snapping behavior when it fully expresses the interaction. A custom gesture should earn its complexity through a product need, not through a preference for physics.

## Cheapest adequate mechanism

Use the least powerful mechanism that fully expresses the interaction. This is a decision rule, not a command to make every interface minimal.

Consider, in order where the context allows it:

- spacing before a separator;
- a separator before a new container;
- a container before a card;
- CSS before JavaScript for a simple visual state;
- native browser behavior before custom behavior;
- an existing accessible primitive before a new primitive;
- an existing dependency before adding another one.

Choose a more powerful mechanism when the simpler one cannot preserve semantics, state, performance, responsiveness, or the required visual relationship. Explain the reason in the implementation recon or WHY Test.

## Interaction review

Before shipping, ask:

- How often will this happen, and is the ceremony proportional?
- What tells the user their input was received immediately?
- Can the user change direction, cancel, retry, or navigate again without a broken intermediate state?
- Does the response preserve a useful spatial or object relationship?
- Does the behavior work with the available input capabilities, not only with a mouse?
- Is there a non-gesture path when the gesture is not essential?
- Does the simplest adequate mechanism preserve the product's intended character?
- Can the user understand the state without animation, timing, or color alone?
