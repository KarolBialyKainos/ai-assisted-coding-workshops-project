---
name: pr-creation
description: "Create a GitHub pull request from the current branch. Use when asked to open, create, prepare, or submit a PR, or when a change needs a review-ready PR description with overview, images, testing, and completion checklists."
---

# Pull Request Creation

Inspect the diff and branches, preserve unrelated changes, run relevant checks, and capture UI screenshots when applicable. Use a concise title and the template below. Check items only when verified; report failures or skipped checks. Confirm repository, branches, body, and authentication before creating the PR, then report its URL.

## PR Body

```markdown
## Overview

What changed and why.

## Images

### Before

<!-- image or Not applicable -->

### After

<!-- image or Not applicable -->

## Testing

- [ ] Tests: `<command or Not applicable>`
- [ ] Lint/typecheck/build: `<command or Not applicable>`
- [ ] Manual verification: `<steps or Not applicable>`

## Checklist

- [ ] Scoped to the request and tested.
- [ ] Documentation updated when needed.
- [ ] UI accessibility and responsiveness checked when applicable.
- [ ] No secrets or generated artifacts included.
- [ ] Breaking changes and follow-up work documented.

## Notes

<!-- Limitations, skipped checks, migrations, or reviewer context. -->
```

Use an authenticated GitHub integration or:

```sh
gh pr create --base <base-branch> --head <head-branch> --title "<title>" --body-file <body-file>
```

Push the head branch only when authorized. Never force-push, amend, merge, or close PRs unless requested. Stop on authentication or missing-information blockers.
