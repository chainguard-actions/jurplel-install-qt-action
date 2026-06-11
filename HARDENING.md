<!-- markdownlint-disable -->

# Hardening Report: jurplel--install-qt-action/v4.3.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **jurplel--install-qt-action/v4.3.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

action.yml references two external actions using mutable tag-based refs instead of pinned full-length SHA commit hashes. This exposes the action to supply-chain attacks if the referenced tags are moved or overwritten.

Failing references:
- `uses: actions/setup-python@v5` — should be pinned to a full 40-character SHA (e.g. `actions/setup-python@<sha> # v5`)
- `uses: jurplel/install-qt-action/action@v4` — should be pinned to a full 40-character SHA (e.g. `jurplel/install-qt-action/action@<sha> # v4`)

Locations:

- `action.yml:88`
- `action.yml:92`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned two unpinned action references in actions/hardened/jurplel--install-qt-action/v4.3.0/action.yml:
1. `actions/setup-python@v5` → `actions/setup-python@a26af69be951a213d495a4c3e4e4022e16d87065 # v5`
2. `jurplel/install-qt-action/action@v4` → `jurplel/install-qt-action/action@48d3ad6db93f3627c8ee7a0454bc6f3744f7e730 # v4`

SHAs were resolved using lookup_action_sha to ensure correctness.

