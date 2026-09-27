# urb-agents-context

A template for the `AGENTS/` folder — a context layer for AI coding agents: Claude Code, OpenAI Codex
and others that read `AGENTS.md`. The folder holds the agent's instructions, its memory, the project
documentation and scripts for working with the environment. Research, tasks and plans are stored in
the urb-research and urb-workbench MCP servers.

## Why

A harness — Claude Code, Codex — handles execution: the loop, tools, subagents. Its memory is flat:
one pile of entries with no purpose, lifetime or owner. Team standards, the project's design and notes
on the current task settle there mixed together. Over time the agent leans on stale and wrong entries,
and there is nothing to sort them with.

Some wrappers do provide structure, but it is tied to the wrapper itself. The context lives inside one
tool: switch tools and you move everything again.

`AGENTS/` solves three problems:

- It does not depend on the harness. Claude Code and Codex read the same instructions from one file.
- It moves to a new project. The shared standard moves as a folder; project specifics are cut off as a
  folder.
- It keeps order. Every fact has one place, every folder has an index, so the context can be checked
  and cleaned up.

## How it works

Folders are split not by topic but by whose knowledge they hold and whether it moves to another
project.

| Path | What it holds | To a new project |
| --- | --- | --- |
| `agent-primary.md` | Instructions for the agent. In a project, the `CLAUDE.md` and `AGENTS.md` symlinks point to it | As a template |
| `docs/` | Approaches and conventions useful in any project, by zone | Yes |
| `work/` | This project's documentation: subsystems, decisions, open problems | No |
| `tools/` | Scripts for working with the project's environment, e.g. queries to a local database | No |
| `memory/` | One-line rules and gotchas; the agent reads them every session | No |
| `research/` | A shortlist of research codes from urb-research | No |
| `tasks/` | The project's binding to a urb-workbench workspace | No |
| `tmp/` | Drafts and one-off reports; never part of the context | No |
| `agents/` | Manual instructions: setup and context cleanup. The user pastes them into the chat or points to the file; the agent never opens them on its own | — |

At session start the agent reads memory, the task binding and every index under `docs/` and `work/`.
It enters a task already knowing what the project has decided and where it is written down. It opens
docs only in the zones the task touches. Before relying on an entry, it checks it against the code: the
code wins, and the agent fixes the stale doc in the same pass.

Claude's memory moves into `AGENTS/memory/`: setup merges it with the template and replaces the
harness folder with a symlink. Memory stays in the project, not in the harness's private storage.

## Getting started

1. Copy only the `AGENTS/` folder from this repository into the root of your project's repository —
   no need to clone this repository or add it as a submodule. If an `AGENTS/` folder is already
   there, move it away first — setup does not merge folders.
2. Paste the contents of `AGENTS/agents/setup/agent-setup.md` into the agent chat, or just point the
   agent to that file.
3. The agent checks the MCP servers, asks for the task workspace code, creates the `CLAUDE.md` and
   `AGENTS.md` symlinks and moves memory. If you agree, it builds a script for querying a local
   database. It never replaces an existing `CLAUDE.md` or `AGENTS.md` without your decision.
4. At the end the agent shows a report: what was done, what was skipped and why, what will not work
   until you act. Restart the agent or IDE.

## Requirements

- [urb-research](https://github.com/TurkovBogdan/urb-research) — research.
- [urb-workbench](https://github.com/TurkovBogdan/urb-workbench) — tasks and plans.

Without them setup still completes, but research and tasks will not work.
