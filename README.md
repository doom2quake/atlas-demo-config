# atlas-demo-config

This is the **demo config codebase** that [Atlas](https://github.com/doom2quake/atlas) — an
autonomous data-ops agent (All Things Agentic) — remediates against.

`payments.yaml` holds the live payment-provider routing, one active provider (and a
fallback) per region. When Atlas detects and root-causes a payment incident (e.g. a
spike in EMEA/Adyen failures wiping out revenue), its **closed-loop remediation** does
not just alert — it opens a **real Pull Request** here that flips the affected region's
`active_provider` to its `fallback` (e.g. EMEA `adyen` → `stripe`). A human reviewer
merges the PR to ship the fix.

Every PR title/body is Atlas's incident summary: the detected failure, the quantified
$ revenue impact, and the proposed failover. This makes the agent's autonomy auditable
— each remediation is a clickable, reviewable artifact.

> This repo intentionally contains only config. It is safe to open PRs against.
