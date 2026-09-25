<!-- markdownlint-disable -->

# Hardening Report: jurplel--install-qt-action/v4.3.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jurplel--install-qt-action/v4.3.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The root action.yml references two external actions using mutable version tags instead of pinned 40-character commit SHAs. This exposes the action to supply-chain attacks: if the referenced tag is moved or the upstream repository is compromised, malicious code could be injected silently.

Failing references:
- `uses: actions/setup-python@v5` (mutable tag `v5`)
- `uses: jurplel/install-qt-action/action@v4` (mutable tag `v4`)

These should be pinned to full SHA digests, e.g.:
  `uses: actions/setup-python@<40-char-sha> # v5`
  `uses: jurplel/install-qt-action/action@<40-char-sha> # v4`

Locations:

- `action.yml:96`
- `action.yml:100`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned both mutable tag references in hardened/action/action.yml:
- `actions/setup-python@v5` → `actions/setup-python@a26af69be951a213d495a4c3e4e4022e16d87065 # v5`
- `jurplel/install-qt-action/action@v4` → `jurplel/install-qt-action/action@a9c63c7c123f3069cff414e7e482d95dfa9d8125 # v4`

SHAs were resolved using lookup_action_sha. README.md references were left unchanged as they are documentation examples, not executable workflow steps.

