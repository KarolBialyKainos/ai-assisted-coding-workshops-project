---
name: pr-creation
description: "Create a GitHub pull request from the current branch. Use when asked to open, create, prepare, or submit a PR, or when a change needs a review-ready PR description with overview, images, testing, and completion checklists."
---

# Pull Request Creation

Use this workflow when creating a GitHub PR:

1. Inspect `git status`, the current branch, the base branch, and the diff. Do not discard unrelated user changes.
2. Run the repository's relevant tests, lint, typecheck, and build checks. For UI changes, capture before/after screenshots when possible.
3. Use a concise title and the template below. Mark checkboxes only after verifying them; report skipped or failed checks honestly.
4. Confirm the repository, branches, title, body, and authentication before creating the PR.
5. Report the created PR URL and any validation gaps.

## PR Body

```markdown
## Overview

<!-- What changed and why. -->

- 

## Images

<!-- Include screenshots for visual changes; otherwise write `Not applicable`. -->

### Before

<!-- image or `Not applicable` -->

### After

<!-- image or `Not applicable` -->

## Testing

- [ ] Unit tests: `<command or Not applicable>`
- [ ] Integration/end-to-end tests: `<command or Not applicable>`
- [ ] Lint/formatting: `<command or Not applicable>`
- [ ] Typecheck/build: `<command or Not applicable>`
- [ ] Manual verification: `<steps or Not applicable>`

## Checklist

- [ ] Change is scoped to the request.
- [ ] Relevant tests and validation pass.
- [ ] Tests cover changed behavior where practical.
- [ ] Documentation is updated when needed.
- [ ] Accessibility and responsive behavior checked for UI changes.
- [ ] No secrets, credentials, or generated artifacts are included.
- [ ] Breaking changes and follow-up work are documented.

## Notes

<!-- Limitations, skipped checks, migrations, or reviewer context. Remove if empty. -->
```

Prefer an authenticated GitHub integration. Otherwise use:

```sh
gh pr create --base <base-branch> --head <head-branch> --title "<title>" --body-file <body-file>
```

The head branch must be pushed or explicitly authorized for pushing. Never force-push, amend, merge, or close PRs unless requested. Stop and report the blocker if authentication or required information is unavailable.
