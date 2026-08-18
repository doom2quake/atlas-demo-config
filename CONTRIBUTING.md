# How Atlas uses this repo

Atlas targets `payments.yaml`. On remediation it:

1. reads the base branch head SHA,
2. creates a branch `atlas/remediate-<run_id>`,
3. updates the affected region's `active_provider` to its `fallback`,
4. opens a PR whose title/body are the incident summary.

Nothing here auto-merges; a human reviews and merges to apply the fix.
