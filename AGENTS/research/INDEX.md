# research — registry

All research lives in the `urb-research` MCP: its body (write-up, areas, notes, cited
sources) is stored there and nowhere else. This folder holds only this file — a shortlist of the
`RESEARCH@` codes that matter for the project. There are no per-research files or folders here.

## Rules

- Before any research the user asks for: read the shortlist below, then run
  `mcp__urb-research__research_list` / `research_get`.
- Conduct and store new research in the MCP: `research_create` → `area_create` → `body_add` /
  `note_create`, citing kept sources as `SOURCE@`.
- Get a skill with `skills_list` / `skill_get` when its guidance is needed.
- Get the `mermaid` skill before drawing a diagram the user asks for.
- Never copy findings, conclusions or numbers out of the MCP into a repo file — a copy rots and
  diverges from the original silently. Keep only the reason to open one, here in the shortlist.
- After creating or updating a research that matters for the project, add or refresh its row in
  the same pass.

## Shortlist (example)

Curated pointer to the `RESEARCH@` codes that matter for this project specifically — hand
maintained, not a full export of the MCP catalogue.

The row below is example data, illustrating the shape a real entry takes; replace it once the
project has its own research.

| Code | Why it matters here |
| --- | --- |
| Example: `RESEARCH@f94a6b8077` | The concept this repository implements: the agent context layer — four folder groups split by content owner, the file layout inside each, agent instructions, and the session read order. |
