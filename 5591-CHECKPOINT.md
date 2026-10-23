# Issue #5591 — implementation pending

Session date: 2026-10-23.

Implementation has not started. Resume implementation this afternoon.
No model catalog, workflow, resolver, or installer changes have been made.

## Starting point

- Approved enhancement: https://github.com/open-gsd/gsd-core/issues/5591
- Branch: `feat/5591-codex-model-choices`, created from `next`.
- Base commit: `6ddd0cef9cb26673bd8321c5480c0814a92d54cb`.
- The working tree was clean before this checkpoint.

## Findings and validation limits

- Codex CLI 0.163.0 returned all seven requested model identifiers and their
  reasoning efforts through App Server `model/list`.
- The queried App Server used an isolated sandbox home without authentication.
  Account availability and actual model execution remain unverified.
- `check:env` passed the minimum Node/npm versions and lockfile checks, but
  failed the version pin: Node 26.7.0 is active while `.nvmrc` requires Node 24.
- `npm ci` failed in the sandbox; a retry with a writable local cache recorded
  network access errors (`EACCES`) for the npm registry.
- Build, focused tests, lint, full tests, and real execution have not run.

## Resume

1. Check the working tree and applicable repository instructions.
2. Activate Node 24, finish `npm ci`, and establish the focused test baseline.
3. Confirm model availability through the authenticated Codex runtime.
4. Extend the existing catalog and settings workflows within the approved scope.
   Preserve tier keys, GPT-5.6 defaults, override precedence, the `ultra` policy,
   and the passive Codex installer posture.
5. Validate saved configuration, resolved models, emitted TOML, and actual
   execution separately. Record remaining limitations before preparing a PR.

This checkpoint is not an implementation or a passing test report.
No PR has been opened.
