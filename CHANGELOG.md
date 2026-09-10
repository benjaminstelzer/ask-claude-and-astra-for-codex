# Changelog

## v2.0.1 - 2026-09-10

- Deliver the Astra opinion directly to the verified calling task instead of
  replaying conversation logs.
- Keep the same destination for follow-ups and report missing delivery instead
  of treating silence as a complete answer.

## v2.0.0 - 2026-09-09

- Run Astra in a fresh normal Codex Desktop project task, preserve the result
  before archiving, and reuse its task ID for explicit follow-ups.
- This is a breaking host change. Codex CLI alone and hosts without normal
  project-task controls are no longer supported.

## v1.0.0 - 2026-09-05

- Added independent Claude and Astra consultations with attributed results and
  partial-failure handling.
- Set Astra to `gpt-6-astra` with `xhigh` effort and Claude to
  `claude-fable-5-1` with `high` effort by default.
- Added an optional Claude timeout. Expiry returns exit 124 without retrying or
  raising the budget.
