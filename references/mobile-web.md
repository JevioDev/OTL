# Mobile Web Behavior

Responsive design is geometric. Platform-native behavior is behavioral. A layout that fits a narrow viewport can still feel wrong on a phone because hover, touch, scrolling, viewport chrome, the software keyboard, and safe areas behave differently.

Use this reference when a surface has touch input, mobile-specific layout, a full-screen shell, a sheet or gesture, or an installed/PWA target. It is not a browser-compatibility encyclopedia.

## Detect capability, not device identity

Touch and mouse are not exclusive. A tablet may have a trackpad; a laptop may have a touchscreen; a phone may have a mouse. Prefer input capabilities such as `(hover: hover)` and `(pointer: fine)` over user-agent or screen-width guesses.

Gate hover-only affordances behind the capability that can use them. Provide press or selected feedback that works on touch as well. Do not use JavaScript device-detection hooks to repair a CSS capability problem.

## Input and press behavior

Check:

- press feedback begins promptly and does not depend only on click release;
- the tap highlight is intentional rather than fighting the product's feedback;
- controls do not accidentally select their labels on long press;
- control text remains unselectable only where it is genuinely a control, while content remains copyable;
- focused inputs use a platform-usable text size so the browser does not trigger unwanted input zoom;
- `touch-action` is limited to surfaces that own a gesture and does not block ordinary page scrolling;
- gesture actions also have a tap, click, keyboard, or other usable alternative when the gesture is not essential.

Do not disable zoom to solve an input or layout problem. Fix the input sizing and responsive relationship instead.

## Viewport and safe areas

Choose viewport units from the behavior required by the surface. A visible app shell or bottom-pinned control may need a dynamic viewport; a stable first screen may need a small viewport. Do not apply one viewport unit to every surface by habit.

For full-bleed or fixed UI, account for safe-area insets around notches, camera cutouts, and home indicators. The viewport configuration and the CSS padding strategy must agree. Check headers, bottom bars, sheets, toasts, and fixed action areas rather than padding every element indiscriminately.

If the browser or installed app exposes browser chrome or a status bar, make its color and contrast agree with the surface. Treat the installed PWA as a distinct context when it changes insets, viewport, or navigation behavior.

## Keyboard, scroll, and overscroll

The software keyboard changes the usable viewport and can cover a focused field or submit action. Check the surface with the keyboard open, especially for fixed footers, chat composers, dialogs, and forms. Preserve the active field and make the next action reachable.

Use scroll containment when an inner surface such as a drawer, sheet, chat list, or sidebar should not chain into the page behind it. Prefer `overscroll-behavior` and native scrolling over non-passive touch listeners that prevent default scrolling.

For carousels and custom gestures, make the axis ownership explicit. Native scroll and snap are usually preferable when they fully express the task. A custom surface that claims every axis must not make the rest of the page impossible to scroll.

## Real-device evidence

Emulation is useful evidence, but it cannot validate every touch, viewport, keyboard, overscroll, safe-area, browser-chrome, or installed-mode behavior.

When the surface is mobile-facing, validate on real hardware where possible:

- touch and press feedback;
- hover capability and focus behavior;
- portrait and landscape;
- the software keyboard open and closed;
- inner scrolling, overscroll, and gesture conflicts;
- safe-area edges and fixed controls;
- the target browser and installed mode when relevant.

If real hardware is unavailable, state that limitation. Code inspection and emulation can verify the intended capability rules and many layout conditions, but they do not prove full mobile behavior.

## Mobile review

- Does the primary action remain reachable with browser chrome and the keyboard present?
- Are hover affordances gated by capability, with touch feedback still available?
- Can a user scroll, select content, zoom, and recover from a gesture without fighting the page?
- Do fixed and full-bleed surfaces respect safe areas?
- Does the interface behave coherently in landscape and in an installed context when that context is supported?
- What was verified on real hardware, and what remains an evidence limitation?
