# Accessibility Quality Floor

Accessibility is a quality floor shared by every visual direction. Do not make a surface less clear, less operable, or less adaptable in pursuit of expression.

## Semantics and interaction

- Use semantic elements and native controls where they express the behavior.
- Ensure every interactive element has an accessible name and a visible focus state.
- Preserve logical keyboard order, especially when visual order changes responsively.
- Support keyboard activation, escape behavior, focus return, and focus containment for overlays where relevant.
- Keep touch targets large enough for the platform and provide adequate separation.
- Do not communicate state through color alone; pair it with text, shape, iconography, or position.
- Make loading, empty, error, disabled, selected, and success states understandable without motion.

## Visual adaptation

Check text and controls at the required contrast, browser zoom, text scaling, and viewport widths. Treat contrast as a relationship between actual foreground, background, size, weight, and state - not as a palette property in isolation.

Do not make secondary text so faint that it stops being usable. Do not use placeholders as the only labels. Ensure focus remains visible against every surface treatment, including images, gradients, overlays, and dark themes.

## Content and resilience

Test long labels, localization expansion, high zoom, missing images, slow font loading, validation errors, and dynamic content updates. Prevent important information from being clipped, hidden on hover, or dependent on precise pointer movement.

Respect `prefers-reduced-motion`. Provide a useful experience when animation is disabled and when a user navigates by keyboard or assistive technology.

## Review questions

- Can a user understand the task without seeing the color or animation?
- Can they complete it with a keyboard?
- Can they find the current focus and state?
- Does text remain readable when enlarged?
- Do errors explain what happened and how to recover?
- Does the responsive composition preserve meaning and order?
