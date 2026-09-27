# memory — index

Loaded every session, so it stays small. A short fact lives here as one or two lines. Facts that
cluster around one topic live in a topic file in this folder, listed in the table below and read
only when the task touches that topic. Keep this file under 150 lines.

The entries below are example data, illustrating the shape a real entry takes; replace them once
real memory exists.

## Rules (example)

- Example: never write to a stand database by hand — go through `AGENTS/tools/db-query/`, it logs
  every query.

## Gotchas (example)

- Example: the queue worker caches config — restart it after editing `.env`, or the old value
  stays live.

## Topic files (example)

| When you need it | Read |
| --- | --- |
| Example: Calling the payment provider's sandbox: test keys, test cards, webhook replay | `payments-sandbox.md` |
