# Keeping Git metadata out of security scan inventories

**Independent open-source contribution by Linxiushen. Merged on September 30, 2026.**

## Problem

Codex Security builds file inventories for repository and directory scans. Nested repositories and linked Git worktrees could contribute their `.git` metadata to those inventories. Metadata then appeared alongside source files and inflated the inventory's coverage count.

The correction also needed to handle a less obvious boundary: a scan scope starting inside a `.git` directory. Excluding the directory name alone does not exclude its descendants when ripgrep starts from an explicit directory inside it.

## Change

The patch excludes `.git` entries at every depth and excludes their descendants in both shared inventory generation and scoped rank-input enumeration. Linked-worktree `.git` files are excluded as well.

Committed regression coverage checks nested repositories, root and nested linked worktrees, six scopes inside metadata directories, and MCP inventory preparation and reading. Explicit path assertions retain `.gitignore`, `.github` and ordinary files with names ending in `.git`, along with the surrounding source files.

## Historical validation and limits

The public PR's historical validation section reports **142 passing Python inventory/rank-input tests**, six directory-scope cases failing before the descendant exclusion, a passing MCP inventory Node test, and nine passing compatibility tests. It also records lint and formatting checks and the TypeScript SDK CI build.

These are historical results reported in the PR, not tests rerun for this case study. This portfolio review checked the saved public diff and assertions; it did not independently rerun or audit the original execution logs.

The change concerns directory enumeration. It does not establish a measured improvement in vulnerability detection, scanning performance or production security outcomes.

## Evidence and implementation relevance

[PR #1099](https://github.com/openai/codex-security/pull/1099) and its [changed files](https://github.com/openai/codex-security/pull/1099/files) provide the implementation and committed regressions. Authorship and merged status were rechecked on October 11, 2026.

This illustrates an AI tooling integration problem: an inventory's count should describe the intended files, and explicit scope boundaries deserve their own tests. The work was an independent, AI-assisted open-source contribution, not OpenAI employment, endorsement or a client engagement.
