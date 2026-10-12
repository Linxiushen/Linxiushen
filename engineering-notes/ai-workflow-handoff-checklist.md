# Before an AI workflow pilot: test the handoff

By Chen Xulin (Linxiushen) · October 12, 2026

A demo can return a good answer while the workflow still fails in the next system. The tool catalog disappears after reconnecting. A report looks readable but the receiver rejects it. A workflow looks right on screen and comes back differently after saving.

I have contributed fixes for each of those boundaries in open-source projects. Here is a small acceptance worksheet you can adapt before connecting more systems. You can use it without hiring me.

## Pick one boundary

Write down one input, the operation allowed to happen and the result the next system must receive. For example:

> A reviewer accepts a synthetic asset. The integration may attach that asset to one test task. It must keep the source reference, show a confirmed attachment and distinguish a failed write from success.

That is an illustrative pilot, not a client result. A useful scope is small enough that another person can check the destination independently.

## Three failures worth making visible

**Empty is a result with meaning.** In [IBM MCP Context Forge #6049](https://github.com/IBM/mcp-context-forge/pull/6049), the fix preserves the saved catalog when the whole OAuth discovery result is empty. Partial, nonempty discovery still reconciles entries; preserving everything would hide a different problem. For your pilot, decide what an empty response means before it triggers deletion or replacement.

**Readable output still needs to meet the receiving format.** In [Tencent AI-Infra-Guard #680](https://github.com/Tencent/AI-Infra-Guard/pull/680), remediation prose had been placed in SARIF `fixes`, which requires artifact changes. The correction retained the advice in the message and `properties.suggestion`. An integration should validate against the receiver's actual contract and document any fields its consumers need to migrate. [Full SARIF explanation](sarif-remediation.md).

**The saved record must reflect the authoritative state.** In [ByteDance FlowGram #1200](https://github.com/bytedance/flowgram.ai/pull/1200), moved nodes needed to serialize their parent from the document tree. For a workflow editor, compare the saved and reloaded structure with the intended one. A correct-looking screen alone does not establish that the handoff worked.

These PRs are merged independent contributions, rechecked on October 12, 2026. They are implementation evidence within their recorded scope, not customer engagements or measured business results. This article does not rerun their historical tests.

## Copy these acceptance checks

| Check | Evidence to retain |
| --- | --- |
| Normal input reaches the intended destination | Sanitized input, destination record and actual readback |
| Empty input follows the agreed policy | Before/after state and a reason to preserve, clear or defer |
| Partial data is handled deliberately | Which records were retained, updated or removed, and why |
| Output meets the consumer's contract | The actual validator result or documented receiver check |
| Saved work survives a reload | Comparison of the intended and reloaded fields or structure |
| A failed write stays visibly failed | Error, observed destination state and the next permitted action |
| A retry avoids unintended duplicates | A controlled retry and destination readback; don't assume this property |
| Missing permission stops the operation | A test account or fixture with denied access and the observed result |
| The designated owner can operate the workflow | A handover exercise, exception notes and unresolved gaps |

The last four are proposed checks for your own pilot, not claims about capabilities demonstrated by the three PRs. Use representative, permitted examples. Start in a test environment and agree any side effects before running them.

For each check, record the observed result and mark it **passed**, **failed** or **not run**. Leave missing evidence visible. A passing checklist is not a security certification or permission to launch into production.

## A worksheet you can keep

Copy the [Markdown acceptance plan](../templates/workflow-acceptance-plan.md) into your project notes, or use the [JSON version](../templates/workflow-acceptance-plan.json). The JSON is a record template, not an executable validator. Every check starts as `not_run`, and the template grants no operations.

Keep the chosen boundary, evidence, owner and unresolved questions together. Agree the success criteria before changing the implementation. If access, a receiver contract or a decision owner is missing, recording that gap may be the most useful assessment result.

If a team wants help with a specific handoff, I offer a [focused workflow assessment](https://leon-ai-workflows.pages.dev/assessment). Start with the process and the two systems involved; fees, scope and dates are agreed separately.

*Independent FDE engineering / AI implementation consulting. Prepared with AI-assisted tools and linked public implementation evidence.*
