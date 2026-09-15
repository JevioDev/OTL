# Typography

Typography is a structural and semantic choice. It controls comprehension, scanning, density, tone, and the perceived confidence of the product. Choose a face because its behavior supports the content and audience, not because it is unusual or currently fashionable.

## Selection procedure

1. Identify the jobs: UI labels, long-form reading, data, code, display, navigation, or mixed editorial content.
2. Decide whether one family can perform all jobs. One excellent family is better than a forced pairing.
3. Test real strings from the product, including the longest labels, headings, numerals, punctuation, and the target language.
4. Check x-height, vertical metrics, cap alignment, numeral quality, punctuation, language coverage, available weights, variable axes, and rendering at the smallest important size.
5. Set hierarchy through role, weight, measure, spacing, and placement before adding a second family.
6. Load only the weights and subsets needed. Provide a deliberate fallback stack and verify that fallback metrics do not break layout.

## UI type versus display type

UI type must survive scanning, small sizes, mixed case, disabled states, tables, forms, and localization. Evaluate open counters, ambiguous glyphs, digit shapes, punctuation, tabular versus proportional figures, and the relationship between cap height and controls.

Display type may carry more personality or tension. Evaluate its proportions, rhythm, line breaks, relationship with imagery, and whether it still supports the subject instead of merely announcing a mood.

Do not add an expressive display face just to make a page feel designed. Use a second family only when it creates a useful role distinction that the primary family cannot provide.

## Layout decisions

- Set measure from reading difficulty and content, not a universal pixel rule. Long prose usually benefits from a controlled line length; dense operational interfaces may require wider rows and stronger column structure.
- Use line-height as a reading and density control. Tight display type and comfortable body text often need different ratios.
- Do not rely on font size alone for hierarchy. Contrast, weight, measure, whitespace, alignment, and placement should cooperate.
- Avoid tracking out sentence-case UI or using all caps as a default label treatment. If capitalization is meaningful, test it at the actual size and language.
- Use tabular numerals for comparison columns and proportional numerals for prose or compact inline values when the typeface supports both.
- Preserve text as content. Do not shorten, clip, or turn useful labels into decorative fragments just to maintain a layout.

## Testing checklist

Test the actual interface at desktop and mobile widths with:

- the longest realistic heading and button label;
- an empty, error, and disabled state where relevant;
- numerals, dates, currency, percentages, and identifiers;
- the supported languages or at least a language with comparable expansion;
- browser zoom or increased text size;
- font loading failure or delayed loading;
- keyboard focus and selected states.

If a type choice fails one of these tests, fix the type or layout relationship. Do not hide the failure with unexplained truncation or tiny text.

## Why test

For every prominent type decision, be able to say: "I chose this family, weight, measure, or pairing because the product's content requires this reading behavior and this audience can use it at the relevant size." If the only reason is that it looks distinctive, keep evaluating.
