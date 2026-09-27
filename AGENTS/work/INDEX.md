# work — project documentation by zone

What the project's subsystems do, why they were decided that way, and what is still broken. One
folder per zone, each with its own `INDEX.md`. Project-specific — unlike `docs/`, this folder does
not migrate to a new project.

## Zone index (example)

The rows below are example data, illustrating the shape a real routing table takes; replace them
once an actual zone exists — an empty registry beats one describing folders that were never created.

| When you need it | Read |
| --- | --- |
| Example: Touching orders, payments or provider webhooks; interpreting a `status` column | `billing/INDEX.md` |
| Example: Changing login, sessions or throttling | `security/INDEX.md` |
| Example: Checking what is known to be broken before relying on a subsystem | `audit/INDEX.md` |
