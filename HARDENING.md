<!-- markdownlint-disable -->

# Hardening Report: jurplel--install-qt-action/v4.2.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jurplel--install-qt-action/v4.2.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Two `uses:` references in action.yml are pinned to mutable tags rather than immutable 40-character commit SHAs. This exposes the action to supply-chain attacks: if the referenced action's tag is moved (intentionally or by a compromised maintainer), the new code runs automatically without any review.

- `uses: actions/setup-python@v5` (tag `v5` — not a SHA)
- `uses: jurplel/install-qt-action/action@v4` (tag `v4` — not a SHA)

These should be pinned to full commit SHAs, e.g.:
  `uses: actions/setup-python@<40-hex-char-sha> # v5`
  `uses: jurplel/install-qt-action/action@<40-hex-char-sha> # v4`

Locations:

- `action.yml:83`
- `action.yml:87`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned both mutable tag references in hardened/action/action.yml to immutable commit SHAs:
- `actions/setup-python@v5` → `actions/setup-python@a26af69be951a213d495a4c3e4e4022e16d87065 # v5`
- `jurplel/install-qt-action/action@v4` → `jurplel/install-qt-action/action@a9c63c7c123f3069cff414e7e482d95dfa9d8125 # v4`

