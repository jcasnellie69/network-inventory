## 2026-04-23 - High-Contrast Focus Indicators on Dark Themes
**Learning:** Default browser focus rings (usually blue or black) are often invisible or have insufficient contrast on very dark backgrounds (e.g., #0d1117), making keyboard navigation impossible for accessibility users.
**Action:** Always add explicit, high-contrast `:focus-visible` styles with `outline-offset` for interactive elements when working with dark themes.
