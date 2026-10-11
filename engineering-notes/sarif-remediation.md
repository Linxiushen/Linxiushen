# Why AI remediation advice isn't a SARIF fix

By Chen Xulin (Linxiushen) · October 11, 2026

Useful advice and an executable fix are different kinds of output. That distinction caused a concrete bug in the SARIF reports produced by AI-Infra-Guard's MCP and Skill scanners.

The scanners could recommend an action in plain language. The formatter put that text into `fixes`, which made the report look reasonable when read as JSON. But SARIF gives that field a more specific meaning.

Here is a shortened excerpt of the old result, not a complete SARIF report:

```json
{
  "fixes": [
    { "description": { "text": "Pass an argument array." } }
  ]
}
```

The recommendation is understandable. It does not say which artifact to edit or which region to replace. The [SARIF 2.1.0 schema](https://docs.oasis-open.org/sarif/sarif/v2.1.0/os/schemas/sarif-schema-2.1.0.json) requires a fix to contain at least one `artifactChange`; each change needs an artifact location and replacements. A description alone cannot satisfy that contract.

In the historical reproduction, both actual formatters produced invalid reports when a nonempty suggestion was present. The validator pointed to `runs[0].results[0].fixes[0]`: `artifactChanges` was missing.

## Keep the advice, change its representation

My correction retained the recommendation in two places. It appends the text to the finding's `message.text`, where a person can read it, and saves the original suggestion in `properties.suggestion`, where another integration can retrieve it.

The corresponding excerpt becomes:

```json
{
  "message": {
    "text": "Unsafe command construction\n\nPass an argument array."
  },
  "properties": {
    "suggestion": "Pass an argument array."
  }
}
```

There is no prose-only `fixes` entry. The finding's rule, severity, location and fingerprint keep their existing values. This is a representation change; it does not make the recommendation more accurate or turn it into a verified patch.

Both scanner formatters received the same correction. Their declared schema URL was also changed to the official OASIS release schema. The [merged PR and complete diff](https://github.com/Tencent/AI-Infra-Guard/pull/680/files) show the implementation, tests and documentation.

## Check the consumer's contract

The new regressions cover English and Chinese output, multiline and non-ASCII advice, missing advice, and unchanged finding identity and location.

During the original PR work, eight of the new cases failed and six passed on unchanged source. All 14 passed with the correction. Against each of two official OASIS schema variants, a 12-case output matrix changed from four invalid reports to zero, while preserving the guidance text.

Those are historical validation results, not a new test run for this article. They were recorded at `88e206d6`; the later PR head `3e43a147` adds only README migration notes, with source and tests unchanged. [PR #680](https://github.com/Tencent/AI-Infra-Guard/pull/680) merged on October 3, 2026. No live GitHub Code Scanning upload or production deployment was tested. The wider Skill suite retained an existing Windows path failure, and the full MCP suite was blocked by a missing local file.

The migration note matters too. A consumer that read `results[].fixes[0].description.text` now needs `results[].properties.suggestion`. A schema correction still changes an integration boundary, even when the recommendation itself stays the same.

## The same check belongs in an AI workflow pilot

When an AI tool hands work to another system, a readable answer is only part of the result. The receiving system also has rules about fields, identity and permitted actions.

For a workflow pilot, I would check the output with the real consumer's validator, include empty and unusual inputs, and test that the change preserves the identity used for tracking. I would also keep proposed advice separate from an action that has the evidence and approval needed to execute.

That gives the team a concrete acceptance check before connecting more systems. It is a useful place to start when a demo works but the next handoff fails.

I work independently on AI workflow and MCP integrations. If your team has a handoff like this, [send a sanitized example and the two systems involved](https://leon-ai-workflows.pages.dev/#contact).

*This was an independent, AI-assisted open-source contribution. It was not a Tencent client engagement or employment relationship. The result demonstrated report-format compatibility within the recorded test scope, not improved vulnerability detection or a measured business outcome.*
