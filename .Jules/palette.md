## 2023-10-27 - High Contrast Focus States in Dark Themes
**Learning:** Default browser focus rings fail WCAG contrast requirements when rendered against the very dark `#0d1117` background used in this UI, making keyboard navigation nearly invisible for many users.
**Action:** Always define an explicit `:focus-visible` state using a high-contrast accent color (like `--accent`) and `outline-offset` to ensure interactive elements are clearly distinguishable during keyboard navigation.
