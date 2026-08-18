# atlas-demo-config

This is the demo config codebase that [Atlas](https://github.com/doom2quake/atlas), an
autonomous data-ops agent (All Things Agentic), remediates against.

`payments.yaml` holds the live payment-provider routing, with one active provider (and a
fallback) per region. When Atlas detects and root-causes a payment incident (for example a
spike in EMEA/Adyen failures wiping out revenue), its closed-loop remediation does not just
alert. It opens a real Pull Request here that flips the affected region `active_provider`
to its `fallback` (for example EMEA `adyen` to `stripe`). A human reviewer merges the PR to
ship the fix.

Every PR title and body is Atlas incident summary: the detected failure, the quantified
dollar revenue impact, and the proposed failover. Each remediation is a clickable,
reviewable artifact.

This repo contains only config. It is safe to open PRs against.
