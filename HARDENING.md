<!-- markdownlint-disable -->

# Hardening Report: jurplel--install-qt-action/v4.3.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **jurplel--install-qt-action/v4.3.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Two `uses:` references in action.yml use mutable version tags instead of full 40-character commit SHA digests, making the action vulnerable to supply-chain attacks if the referenced tag is moved or overwritten:
- `uses: actions/setup-python@v6` (tag `v6` is mutable)
- `uses: jurplel/install-qt-action/action@v4` (tag `v4` is mutable)

These should be pinned to their full SHA digests, e.g. `uses: actions/setup-python@<40-hex-sha> # v6`.

Locations:

- `action.yml:88`
- `action.yml:92`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned both mutable tag references in action.yml to full 40-character commit SHAs: actions/setup-python@v6 → @ece7cb06caefa5fff74198d8649806c4678c61a1 # v6, and jurplel/install-qt-action/action@v4 → @a9c63c7c123f3069cff414e7e482d95dfa9d8125 # v4. Original tags preserved as inline comments for readability.

