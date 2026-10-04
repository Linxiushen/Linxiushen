# Preserving an MCP gateway catalog after empty OAuth discovery

**Independent open-source contribution by Linxiushen. Merged on October 2, 2026.**

## Problem

An MCP gateway stores tools, resources, and prompts discovered from connected services. When OAuth discovery returned an empty catalog, synchronization needed to preserve existing entries rather than erase useful saved data. The challenge extended beyond keeping rows: tool aliases retained from the UI, API, or older records still had to obey naming and visibility rules.

## Root cause

The synchronization path coupled newly discovered results with cleanup of the existing catalog. An empty response therefore required an explicit preservation policy. As upstream collision checks evolved, retaining local tools also exposed a compatibility boundary: validation had to include aliases that would remain after synchronization, using their persisted visibility and ownership scope.

Checking only incoming tools was insufficient. A retained alias could conflict even though it did not appear in the latest remote discovery result.

## Change

The fix preserves existing catalog entries when OAuth discovery returns no entries and includes retained local aliases in the existing collision guard. It uses the established scope checks rather than introducing a separate definition of which tools may share a name.

Regression coverage exercises empty and populated discovery, retained aliases, conflicting names, and visibility boundaries. The database cases use real SQLite persistence through synchronization, validation, reconciliation, and commit; remote OAuth, notification, and cache boundaries are mocked.

## Validation and limits

The saved gateway test run recorded **441 passed and one existing skip**. A related suite recorded **503 passed and one Windows lock-path assertion failure**; the same failure reproduced on unchanged upstream code. Three original regression cases failed against unchanged source and passed with the fix. Additional database regressions checked retained-alias conflicts, rollback, and public, team, and private visibility.

These are historical contribution results, not tests rerun for this case study. Full-repository coverage, a production gateway, and end-to-end deployment were not validated. No customer uptime or financial impact was measured.

## Evidence and implementation relevance

[PR #6049](https://github.com/IBM/mcp-context-forge/pull/6049) contains the implementation and review; the [changed files](https://github.com/IBM/mcp-context-forge/pull/6049/files) show the code and regressions. Authorship and merged status were rechecked on October 4, 2026.

For enterprise AI implementation, this illustrates a concrete integration concern: defining what an empty external response means for local state, then preserving data without weakening consistency rules. The transferable work is reproduction, a scoped correction, and explicit acceptance evidence.

I used an **AI-assisted workflow**. This was independent open-source work, not employment or a client engagement with IBM.
