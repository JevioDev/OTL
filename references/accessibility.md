# Accessibility Quality Floor

Accessibility is the quality floor shared by every visual direction. Do not make a surface less clear, less operable, or less adaptable in pursuit of expression.

This reference owns accessibility-specific behavior and presentation: semantics, names, focus, keyboard use, contrast, state communication, and reduced motion. For the broader production audit of forms, content resilience, navigation state, runtime correctness, performance, and localization, use [web-quality.md](web-quality.md). For touch, viewport, safe-area, keyboard, and browser-chrome behavior, use [mobile-web.md](mobile-web.md).

## Semantics and operation

- Use semantic elements and native controls where they express the behavior.
- Ensure every interactive element has an accessible name and a visible focus state.
- Preserve logical keyboard order, especially when visual order changes responsively.
- Support keyboard activation, escape behavior, focus return, and focus containment for overlays where relevant.
- Keep touch targets large enough for the platform and provide adequate separation.
- Do not communicate state through color or animation alone; pair it with text, shape, iconography, position, or another perceivable signal.
- Make loading, empty, error, disabled, selected, and success states understandable without motion.

Native controls already provide keyboard semantics. Do not add manual key handlers that duplicate or conflict with them. Use custom keyboard handling only when a genuinely custom interaction requires it, and define the full operation model.

## Visual adaptation

Check text and controls at the required contrast, browser zoom, text scaling, and viewport widths. Treat contrast as a relationship between actual foreground, background, size, weight, and state, not as a palette property in isolation.

Do not make secondary text so faint that it stops being usable. Do not use placeholders as the only labels. Ensure focus remains visible against every surface treatment, including images, gradients, overlays, and dark themes.

## Motion and change

Respect `prefers-reduced-motion`. Provide a useful experience when animation is disabled or reduced, and do not hide information behind motion. Check that focus, state, and errors remain understandable when transitions are shortened or removed.

## Review questions

- Can a user understand the task without seeing the color or animation?
- Can they complete important actions with the available keyboard and assistive technology semantics?
- Can they find the current focus and state after an overlay, navigation, validation failure, or async update?
- Does text remain readable when enlarged or when the viewport changes?
- Do errors explain what happened and how to recover?
- Does the responsive composition preserve meaning and order?
- Does the implementation quality gate cover the relevant form, content, navigation, and runtime cases?
