# IMPORTANT: Agents must update this file when making important structural changes to the project.

# Agent Instructions

- This is a deliberately incomplete workshop project. Preserve its educational progression: empty functions and `TODO Task N` comments are intentional unless the request targets that exercise.
- Make changes only for the requested task; do not silently complete later exercises.
- The application uses plain HTML, CSS, and browser JavaScript.
- There are no dependencies, package manager, bundler, framework, or build step.
- Do not introduce a framework or build system unless the task explicitly requires it.
- Keep the app usable as a standalone static site; use browser APIs rather than Node.js APIs.
- Main task data is stored under `kainos-todo:todos`.
- The API key is stored under `kainos-todo:apiKey`.
- `state.todos` is the source of truth for task rendering. Existing task fields include `id`, `text`, `done`, `createdAt`, and `priority`.
- Rendering is coordinated through `render()`, which calls the focused render functions. State-changing operations should save state where appropriate and then render.
- Preserve DOM IDs and classes referenced by JavaScript, including `add-form`, `todo-input`, `todo-list`, `empty-state`, `filter-bar`, `stats`, `progress-bar`, `task-count`, `options-link`, `settings-form`, `api-key-input`, and `save-status`.
- Keep user-generated task text safe when rendering. Do not interpolate untrusted content into HTML without escaping it or using DOM text APIs.
- Keep storage parsing resilient to missing or malformed values so the page can still load.
- Retain the existing visual language and responsive single-card layout unless redesign work is requested.
- Keep implementations approachable for workshop participants. Prefer small named functions and standard browser APIs over abstractions that obscure the exercise.
- Update `README.md` when setup, exercise scope, file responsibilities, or external service requirements change.
- The README specifies OpenRouter for Task 5, while the current settings page says "Anthropic API Key" and uses an Anthropic-style placeholder. Treat this as an existing inconsistency and confirm the intended provider before implementing or documenting the AI request format.
- Never commit API keys or add a real key to examples, fixtures, logs, or source files.
- Ignore the untracked root `gh` executable; it is not application source.

## Validation

- There is no automated test suite. Check edited JavaScript with `node --check <file>`.
- Exercise changed behavior in a modern browser and check the browser console.
- Refresh after persistence changes, verify `options.html` after settings changes, and test UI changes at mobile and desktop widths.
- Verify only the requested exercise; do not assume later exercises are implemented.