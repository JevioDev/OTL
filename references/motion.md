# Motion

Motion is a communication channel. It should explain causality, confirm an action, direct attention, preserve spatial relationships, or express a product personality that the context supports. It is not a default layer of polish.

## Choose a motion job

Assign each non-trivial animation one primary job:

1. feedback: show that an action was received;
2. continuity: show where content came from or where it went;
3. attention: bring a meaningful change into view;
4. orientation: explain spatial relationships or navigation;
5. expression: make a deliberate brand or subject-specific moment.

If an animation has no job, remove it. If several animations compete, keep the one that carries the most information.

## Motion budget

Set motion intensity from the Design Read. Low intensity may use state feedback and short continuity transitions. Medium intensity may include one orchestrated entry or meaningful view transition. High intensity is justified only when the product itself is spatial, cinematic, playful, or exploratory and the motion remains controllable.

Avoid automatic fade-up on every section, stagger-everything sequences, bounce or elastic easing, scale-on-hover everywhere, and permanently floating decoration. These patterns are not forbidden; they need evidence from the interaction or subject.

Prefer motion that is:

- short enough to preserve task flow;
- interruptible when the user acts again;
- stable under repeated use;
- tied to the element that changed;
- understandable without animation.

Use CSS or existing platform primitives for simple transitions. Add a library only when it solves a real interaction problem or an existing stack already depends on it.

## Reduced motion and failure

Respect `prefers-reduced-motion`. Replace non-essential travel, parallax, scale, and looping effects with opacity, instant state changes, or no animation. Never hide information behind motion. Test when content enters, exits, loads late, errors, and is updated repeatedly.

## Why test

For each visible animation, finish: "I used this motion because the user needs to understand, confirm, follow, or feel X at this moment." "It looks polished" is not a sufficient reason.
