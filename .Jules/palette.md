## 2024-05-24 - High Contrast Focus on Dark Themes
**Learning:** Default browser focus outlines are nearly invisible against very dark background colors (like `#0d1117`), making keyboard navigation extremely difficult for users relying on visual focus indicators.
**Action:** Always implement explicit, high-contrast `:focus-visible` styles with appropriate `outline-offset` when working with dark-themed interfaces to ensure interactive elements are clearly discernible when focused via keyboard.
