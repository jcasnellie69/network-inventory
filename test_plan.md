1. **Fix malformed CSS block in `index.html`**
   - Use `replace_with_git_merge_diff` to clean up the malformed CSS block spanning lines 271-302. Replace the duplicated and malformed `focus-visible` selectors with a single valid block that correctly targets standard inputs and DataTables elements.
2. **Update 'Clear Filters' logic in `index.html`**
   - Use `replace_with_git_merge_diff` to change `$('select').on('change', ...)` to `$('#filterStatus, #filterPriority, #filterPort, #filterCategory').on('change', ...)` so it only targets our specific filter dropdowns and ignores DataTables generated selects.
   - Use `replace_with_git_merge_diff` to modify `updateClearFiltersBtn()` to check if the DataTable search value is truthy (`table.search()`).
   - Use `replace_with_git_merge_diff` to modify the `#clearFiltersBtn` click handler to explicitly call `table.search('').draw()`.
   - Use `replace_with_git_merge_diff` to add `table.on('search.dt', updateClearFiltersBtn);` so the global search reflects changes on the Clear Filters button.
3. **Document UX learnings**
   - Use `write_file` to create `.Jules/palette.md` with a specific journal entry summarizing how to avoid generic element selectors (`$('select')`) when using libraries like DataTables that inject their own input elements.
4. **Verify Palette Documentation**
   - Use `read_file` to confirm that `.Jules/palette.md` was correctly written.
5. **Verify locally via HTTP server**
   - Run `python3 -m http.server 3000 &` in `run_in_bash_session` to serve the directory.
   - Use `run_in_bash_session` with `curl -s http://localhost:3000/index.html` to confirm the page loads properly and changes are reflected.
6. **Complete pre-commit steps**
   - Complete pre-commit steps to ensure proper testing, verification, review, and reflection are done.
7. **Submit the PR**
   - Call `submit` with the appropriate branch, commit message, and description, requesting user approval.
