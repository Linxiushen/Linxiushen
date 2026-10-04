# Preserving remediation guidance in valid SARIF reports

**Independent open-source contribution by Linxiushen. Merged on October 3, 2026.**

## Problem

AI-Infra-Guard's MCP and Skill scanners produced SARIF reports containing remediation advice. The advice was useful text, but some reports failed SARIF schema validation. A report that looks understandable to a person still needs to satisfy the structured format expected by downstream security tooling.

The correction needed to retain the recommendation, produce valid output, and explain the field change to integrations that consumed the previous format.

## Root cause

The formatters placed prose recommendations in SARIF `fixes`. A SARIF fix represents concrete artifact edits; a text description alone does not supply the required edit structure. Treating a recommendation as a machine-applicable fix therefore created invalid reports.

Removing the advice would have hidden the schema problem at the expense of useful information. The appropriate representation was a human-readable message plus a separate property for consumers needing the original suggestion.

## Change

The fix updates both scanner formatters to include remediation in `message.text` and preserve it separately in `properties.suggestion`. Prose-only recommendations are no longer emitted as automatic fixes.

Regression tests cover both scanners. English and Chinese README updates document the behavior and migration: consumers that previously read `results[].fixes[0].description.text` should instead read `results[].properties.suggestion`. That makes the compatibility change visible to callers instead of leaving them to infer it from a schema failure or missing field.

## Validation and limits

The saved focused tests changed from **eight failures and six passes** on original source to **14 passes** with the correction. Two official schema variants each checked 12 generated outputs: each had four invalid reports before the fix and none afterward. The recorded Go build also passed.

Validation ran at commit `88e206d6`. A later comparison confirmed that the subsequent PR head, `3e43a147`, changed only four README migration notes; source and tests were unchanged. Tests were not rerun at that later head or for this case study.

No real GitHub Code Scanning upload or production scanner deployment was tested. The full Skill suite retained an existing Windows path failure; the full MCP suite was blocked by a missing local `pre_scan.py` file. This was a report-format defect, not a CVE or a demonstrated attack.

## Evidence and implementation relevance

[PR #680](https://github.com/Tencent/AI-Infra-Guard/pull/680) and its [changed files](https://github.com/Tencent/AI-Infra-Guard/pull/680/files) provide the implementation and review. Authorship and merged status were rechecked on October 4, 2026.

For AI implementation, the lesson is to validate the contract between tools and document consumer migrations alongside code changes. I used an **AI-assisted workflow**; this independent contribution was not a Tencent client engagement or employment relationship.
