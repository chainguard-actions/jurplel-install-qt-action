<!-- markdownlint-disable -->

# Hardening Report: jurplel--install-qt-action/v4.3.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **jurplel--install-qt-action/v4.3.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

action.yml references two external actions using mutable version tags instead of pinned full-length SHA commit hashes. This exposes the action to supply-chain attacks where a tag could be moved to point to malicious code. Failing references: `actions/setup-python@v6` and `jurplel/install-qt-action/action@v4`. Both should be pinned to a full 40-character commit SHA (e.g. `actions/setup-python@<sha> # v6`).

Locations:

- `action.yml:82`
- `action.yml:87`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned both unpinned action references in action.yml to full 40-character SHA commit hashes: (1) actions/setup-python@v6 → actions/setup-python@a309ff8b426b58ec0e2a45f0f869d46889d02405 # v6; (2) jurplel/install-qt-action/action@v4 → jurplel/install-qt-action/action@48d3ad6db93f3627c8ee7a0454bc6f3744f7e730 # v4. Original tag names preserved as comments for readability.

