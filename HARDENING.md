<!-- markdownlint-disable -->

# Hardening Report: jurplel--install-qt-action/v4.2.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **jurplel--install-qt-action/v4.2.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The root action.yml contains two `uses:` references pinned to mutable tags rather than full 40-character SHA commit hashes. This exposes the action to supply-chain attacks: if the referenced action's tag is moved (intentionally or by a compromised maintainer), the new code runs automatically without any review.

- `uses: actions/setup-python@v5` (line 83) — should be pinned to a full SHA, e.g. `actions/setup-python@a26af69be951a213d495a4c3e4e4022e16d87065 # v5`
- `uses: jurplel/install-qt-action/action@v4` (line 88) — should be pinned to a full SHA

Locations:

- `action.yml:83`
- `action.yml:88`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned both mutable tag references in actions/hardened/jurplel--install-qt-action/v4.2.1/action.yml to full commit SHAs:
- `actions/setup-python@v5` → `actions/setup-python@a26af69be951a213d495a4c3e4e4022e16d87065 # v5` (line 83)
- `jurplel/install-qt-action/action@v4` → `jurplel/install-qt-action/action@48d3ad6db93f3627c8ee7a0454bc6f3744f7e730 # v4` (line 88)

