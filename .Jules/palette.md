## 2026-04-14 - Empty Table Async Fetch
**Learning:** Tables relying on asynchronous JS fetches (like DataTables loading via JSON) present an empty, unhelpful layout to users before the data loads. If the table layout has column headers but no body content, it is confusing and visually jarring when content suddenly pops in. Screen readers also encounter an empty table.
**Action:** Always add a placeholder row with `colspan` equal to the number of columns and an `aria-live="polite"` region inside the `<tbody>` so users (both sighted and non-sighted) receive immediate feedback that data is loading.
## 2026-04-23 - High-Contrast Focus Indicators on Dark Themes
**Learning:** Default browser focus rings (usually blue or black) are often invisible or have insufficient contrast on very dark backgrounds (e.g., #0d1117), making keyboard navigation impossible for accessibility users.
**Action:** Always add explicit, high-contrast `:focus-visible` styles with `outline-offset` for interactive elements when working with dark themes.
## 2026-04-24 - High-Contrast Focus Indicators in Dark Themes
**Learning:** Dark themes (like `#0d1117`) often swallow default browser focus rings, making keyboard navigation difficult or impossible for interactive elements like selects, inputs, and custom pagination buttons.
**Action:** Add explicit `:focus-visible` styles using a high-contrast accent color and `outline-offset` to ensure interactive elements remain distinctly visible during keyboard navigation.
