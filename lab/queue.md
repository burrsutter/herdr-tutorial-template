# Herdr lab: worker queue and attention board

The human maintains this file. It does not automatically dispatch work.

| Worker / harness | Repo | Current task | Work state | Needs human / reason | Next queued task |
|---|---|---|---|---|---|
| hello-builder / Claude | hello | none | idle | none | H0 TypeScript greeting |
| hello-reviewer / Codex | hello | none | idle | none | Review H0 |
| api-builder / Claude | api | none | idle | none | A1 TypeScript HTTP API |
| api-reviewer / Codex | api | none | idle | none | Review A1 |
| web-builder / Claude | web | none | idle | none | W1 HTML renderer |
| web-reviewer / Codex | web | none | idle | none | Review W1 |
| batch-builder / Claude | batch | none | idle | none | B1 inventory summary |
| batch-reviewer / Codex | batch | none | idle | none | Review B1 |

Work states: ready, working, waiting-human, blocked-dependency,
awaiting-review, accepted, failed, idle. Record actual pane/task evidence.
An agent's Done/idle badge is separate from human acceptance.
