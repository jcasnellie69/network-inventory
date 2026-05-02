## 2026-04-22 - Explicit Focus Styles on Dark Themes
**Learning:** Default browser focus rings (often blue or faint outlines) can become entirely invisible or provide insufficient contrast against dark backgrounds (like `#0d1117`), making keyboard navigation impossible.
**Action:** Always explicitly define `:focus-visible` styles with a high-contrast outline (`outline: 2px solid var(--accent);`) and space it apart from the element (`outline-offset: 2px;`) to ensure interactive elements are clearly distinguishable for keyboard users.
## 2024-05-24 - High Contrast Focus on Dark Themes
**Learning:** Default browser focus outlines are nearly invisible against very dark background colors (like `#0d1117`), making keyboard navigation extremely difficult for users relying on visual focus indicators.
**Action:** Always implement explicit, high-contrast `:focus-visible` styles with appropriate `outline-offset` when working with dark-themed interfaces to ensure interactive elements are clearly discernible when focused via keyboard.
## 2023-10-27 - High Contrast Focus States in Dark Themes
**Learning:** Default browser focus rings fail WCAG contrast requirements when rendered against the very dark `#0d1117` background used in this UI, making keyboard navigation nearly invisible for many users.
**Action:** Always define an explicit `:focus-visible` state using a high-contrast accent color (like `--accent`) and `outline-offset` to ensure interactive elements are clearly distinguishable during keyboard navigation.
## 2024-05-18 - Dark Theme Focus Rings and Async Tables
**Learning:** Default browser focus rings often have insufficient contrast or disappear entirely against custom dark theme backgrounds (`#0d1117`). Additionally, vanilla DataTables initialized over an empty `<tbody>` while waiting for an asynchronous `fetch` leaves a jarring empty space without feedback for screen readers or visual users.
**Action:** Always explicitly define `:focus-visible` styles (e.g., `outline: 2px solid var(--accent); outline-offset: 2px;`) for interactive elements in dark-themed applications. For tables relying on async data, always hardcode an initial loading row with `aria-live="polite"` before the JavaScript library takes over rendering.
## 2026-04-17 - DataTables Accessibility and Empty States
**Learning:** Vanilla DataTables lacks some accessibility features by default, like visible keyboard focus (`focus-visible`) and distinct hover states on its generated pagination buttons. Also, since it renders asynchronously based on a JSON fetch, users see an awkward, completely empty table outline during loading.
**Action:** Always add `*:focus-visible` generic styles if missing, explicit `cursor: pointer` + hover states to `.paginate_button`, and a hardcoded loading placeholder (`<td colspan="X">`) in the initial HTML `<tbody>` which DataTables will automatically overwrite once the data is loaded.
## 2026-04-14 - Empty Table Async Fetch
**Learning:** Tables relying on asynchronous JS fetches (like DataTables loading via JSON) present an empty, unhelpful layout to users before the data loads. If the table layout has column headers but no body content, it is confusing and visually jarring when content suddenly pops in. Screen readers also encounter an empty table.
**Action:** Always add a placeholder row with `colspan` equal to the number of columns and an `aria-live="polite"` region inside the `<tbody>` so users (both sighted and non-sighted) receive immediate feedback that data is loading.
## 2026-04-23 - High-Contrast Focus Indicators on Dark Themes
**Learning:** Default browser focus rings (usually blue or black) are often invisible or have insufficient contrast on very dark backgrounds (e.g., #0d1117), making keyboard navigation impossible for accessibility users.
**Action:** Always add explicit, high-contrast `:focus-visible` styles with `outline-offset` for interactive elements when working with dark themes.
## 2026-04-24 - High-Contrast Focus Indicators in Dark Themes
**Learning:** Dark themes (like `#0d1117`) often swallow default browser focus rings, making keyboard navigation difficult or impossible for interactive elements like selects, inputs, and custom pagination buttons.
**Action:** Add explicit `:focus-visible` styles using a high-contrast accent color and `outline-offset` to ensure interactive elements remain distinctly visible during keyboard navigation.

## 2026-04-24 - Contextual Filter Resets
**Learning:** In dashboards with multiple dropdown filters, users often get stuck in narrow filtered states and have to manually clear each one. A global "Clear Filters" button that only appears when filters are active significantly reduces friction.
**Action:** Implement contextual reset mechanisms for multi-axis filtering, showing a button to bulk-clear filters only when at least one filter is active to keep the UI clean by default.
## 2026-05-02 - DataTables Selectors and Search Integrations
**Learning:** Broad jQuery event bindings (like `$('select').on('change')`) in interfaces with DataTables are problematic because DataTables injects its own `<select>` elements (e.g., the page length menu), triggering unexpected side-effects. Additionally, a "Clear Filters" mechanism should reset not just custom dropdowns but also the DataTable's native global search, requiring explicit integration with `table.search()` and listening to the `search.dt` event.
**Action:** When implementing custom filters alongside DataTables, always bind to specific filter IDs (`$('#filterStatus, ...')`) rather than generic tags. Always factor in `table.search()` for both the "active filters" check and the reset logic (`table.search('').draw()`).
