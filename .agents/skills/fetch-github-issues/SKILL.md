---
name: fetch-github-issues
description: "Fetch and summarize GitHub issues from a repository URL using the gh CLI. Use when asked to get, list, retrieve, inspect, or summarize issues for a given GitHub repository URL."
---

# Fetch GitHub Issues

Use the authenticated `gh` CLI to retrieve issues from a repository URL. This workflow is read-only: do not create, edit, close, label, or comment on issues.

## Inputs

Ask for the GitHub repository URL if it was not provided. Accept optional filters for issue state (`open`, `closed`, or `all`) and result limit. Default to `open` and 30 issues.

## Workflow

1. Confirm that `gh` is installed and authenticated:

   ```sh
   gh --version
   gh auth status
   ```

2. Resolve and validate the repository URL:

   ```sh
   repository="$(gh repo view "<repository-url>" --json nameWithOwner --jq '.nameWithOwner')"
   ```

   Stop and report the error if authentication fails, the URL is invalid, or the repository is inaccessible.

3. Fetch the issues. Replace `<state>` and `<limit>` with the requested values or defaults:

   ```sh
   gh issue list --repo "$repository" --state <state> --limit <limit> \
     --json number,title,state,author,labels,assignees,createdAt,updatedAt,url
   ```

   Use `--search "<query>"` when the user supplies search criteria. Remember that pull requests are not included by `gh issue list`.

4. Present a concise list containing each issue's number, title, state, labels, assignees, updated date, and URL. State the repository and filters used, preserve the CLI's ordering, and say clearly when no issues match.

For machine-readable output, return the JSON from step 3 without reshaping it unless the user requests another format. Never expose authentication tokens or include them in commands, logs, or output.
