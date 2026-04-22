## 2026-04-22 - Explicit Focus Styles on Dark Themes
**Learning:** Default browser focus rings (often blue or faint outlines) can become entirely invisible or provide insufficient contrast against dark backgrounds (like `#0d1117`), making keyboard navigation impossible.
**Action:** Always explicitly define `:focus-visible` styles with a high-contrast outline (`outline: 2px solid var(--accent);`) and space it apart from the element (`outline-offset: 2px;`) to ensure interactive elements are clearly distinguishable for keyboard users.
