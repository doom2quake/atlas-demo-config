# How Atlas uses this repo

Atlas targets `payments.yaml`. On remediation it:

1. reads the base branch head SHA,
2. creates a branch `atlas/remediate-<run_id>`,
3. updates the affected region `active_provider` to its `fallback`,
4. opens a PR whose title and body are the incident summary.

Nothing here auto-merges. A human reviews and merges to apply the fix.
