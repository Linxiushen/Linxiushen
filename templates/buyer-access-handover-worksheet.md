# Buyer worksheet: consultant access and workflow handover

Use this planning worksheet with the person commissioning one AI workflow and the people who will operate it. Choose the next decision, record the access actually granted and agree the evidence needed before accepting the handover.

**No exercises have been run.** Every exercise below starts as `not_run`; dates, observations and evidence are blank. A proposed check does not establish that the current tools support it. Confirm the available controls before agreeing the acceptance plan. Keep passwords, tokens and confidential records out of this worksheet.

## 1. Define the workflow and its owners

| Field | Agreed value |
| --- | --- |
| Workflow / engagement reference | |
| Decision this work should support | |
| One input and its authoritative source | |
| Intended destination and evidence of completion | |
| Business owner who accepts or holds an output | |
| Access administrator who grants or removes access | |
| Technical operator who diagnoses, pauses or restores work | |
| Change approver | |
| Route when a named owner is unavailable | |
| Approved environment and test workspace | |
| Included users, systems and operations | |
| Excluded data, operations and environments | |
| Approved synthetic or redacted examples | |
| Acceptance criteria and agreed limits | |
| Review point before expanding the boundary | |

An assessment, a connection experiment, a draft and a live write are separate grants. Record the lowest access stage that can answer the agreed question; expand it only through the client's authorized decision route.

## 2. Make an access register that can be closed

Use separate rows for the consultant's human account and the identity used by the running workflow. Record a reference to secret storage, never a credential value.

| Record | Human account | Runtime identity |
| --- | --- | --- |
| Identity / account reference | | |
| Client-controlled account, project or workspace | | |
| Client access owner | | |
| Purpose and current access stage | | |
| Environment | | |
| Records, fields and attachments that may be accessed | | |
| Requested operations and permissions | | |
| Permissions actually granted | | |
| Differences between requested and actual grants | | |
| Approval needed before a write | | |
| Secret-storage reference, without the secret | | |
| Review or expiry point | | |
| Removal steps and provider-documentation reference | | |
| Other workflows that may be affected by removal | | |
| Person who will verify removal | | |

Read access can expose data outside the intended task. Check the actual accessible records, rather than relying only on a promise to use one folder. If the tool cannot enforce the agreed limit, decide whether to use approved samples, an isolated workspace, a narrower experiment or no connection.

## 3. Agree the access and recovery exercises

The proposed observations below are questions for the acceptance plan. Adapt them to the real tool and environment. Agree an authorized test method before changing permissions or removing a grant; revocation can affect other clients or workflows.

| ID | Proposed exercise | Observation to inspect | Status | Observed result | Evidence / date / reviewer |
| --- | --- | --- | --- | --- | --- |
| A1 | Inspect the identity's effective read access | Agreed source records are accessible; records and attachments outside the boundary are checked | not_run | | |
| A2 | Exercise an operation outside the granted boundary | Actual controls reject or route the operation as agreed; any coarse-permission limit is visible | not_run | | |
| A3 | Prepare a draft without a live write grant | The owner can find the draft and its input reference; the proposed live-write boundary is checked | not_run | | |
| A4 | Change the input or destination after review | The workflow's treatment of the changed operation matches the agreed approval rule | not_run | | |
| A5 | Exercise a rejected request and a tool execution failure | The operator sees the actual outcome, attempt reference and next decision owner | not_run | | |
| A6 | Exercise a write whose acknowledgement is unavailable | The original destination result is reconciled or left unresolved before any retry decision | not_run | | |
| A7 | Reconnect or change access in the approved test environment | Current discovery and the permitted operation reflect the actual account boundary; gaps are recorded | not_run | | |
| A8 | Remove the consultant's human access | The intended access is blocked; the chosen client-owned continuation or retirement route is inspected | not_run | | |
| A9 | Remove the runtime grant for a retired pilot | The relevant trigger and operation reach the agreed stopped state; unresolved attempts and other dependencies are recorded | not_run | | |

Do not treat a disconnected badge as proof that every invitation, application grant or key is removed. Document each grant and any removal check that the available tools cannot support. Revoking access does not establish deletion of previously copied data.

## 4. Build the handover index

Separate contractual rights to deliverables from the practical responsibility for operating them. Repository access alone does not settle either question.

| Item | Accepted reference / agreed value | Remaining question / owner |
| --- | --- | --- |
| Delivered materials and contractual use rights | | |
| Third-party licenses and reusable-component limits | | |
| Accepted repository, export or release version | | |
| Workflow configuration and prompt versions | | |
| Input and destination schemas | | |
| Environment, deployment and external dependencies | | |
| Human and runtime access-register location | | |
| Evaluation examples, actual results and test environment | | |
| Untested conditions and known limits | | |
| Operator guide: start, inspect, hold, pause and recover | | |
| Configured monitoring mechanism and failure-report route | | |
| Conditions that require a pause or renewed evaluation | | |
| Version-restoration process and supported limits | | |
| Recurring software costs and account owner | | |
| Separately agreed support scope, owner and end point | | |

## 5. Rehearse the handover with the designated client operator

Use the approved environment and agreed examples. The client operator performs the steps using the guide; record where the guide or controls need improvement. Synthetic or test-workspace results remain evidence for that tested boundary.

| ID | Proposed exercise | Observation to inspect | Status | Observed result | Evidence / date / reviewer |
| --- | --- | --- | --- | --- | --- |
| H1 | Run one agreed normal example from the operating guide | The client operator finds the actual destination record and checks the agreed fields | not_run | | |
| H2 | Handle a missing-input or review-held example | The operator finds the held item and uses the named decision route | not_run | | |
| H3 | Pause new triggers | The operator checks new work and work already in progress; unresolved attempts are retained for reconciliation | not_run | | |
| H4 | Restore the accepted version when supported | The documented process is followed and the relevant operation is checked again | not_run | | |
| H5 | Change one agreed permission, schema or configuration | The change approver can identify what needs another evaluation and record the resulting version | not_run | | |
| H6 | Follow the continue or retire route after consultant removal | The client can inspect the intended runtime state and outstanding access, data and operating decisions | not_run | | |

## 6. Close data handling and the next decision

| Field | Agreed value / evidence |
| --- | --- |
| Locations of samples, logs, exports and backups | |
| Allowed retention and responsible owner | |
| Deletion or retention evidence to request | |
| Provider capabilities and items that cannot be verified | |
| Unfinished runs and reconciliation owner | |
| Outstanding acceptance gaps and decision owner | |
| Continue, extend the scope or retire | |
| Accepted operating boundary | |
| Additional work and support explicitly agreed | |
| Decision date and authorized client decision-maker | |

This is a planning and evidence record. It does not run code, grant access, establish ownership rights, certify a workflow or promise continued support.

## Related open guides

- [What access should an AI consultant need to connect business tools?](https://leon-ai-workflows.pages.dev/guides/consultant-access-business-tools)
- [Who owns an AI workflow after the pilot?](https://leon-ai-workflows.pages.dev/guides/ai-workflow-pilot-handover-ownership)
- [Assessment or pilot: what to commission first](https://leon-ai-workflows.pages.dev/guides/ai-workflow-assessment-vs-pilot)
- [MCP integration reliability checklist](https://leon-ai-workflows.pages.dev/guides/mcp-integration-reliability-checklist)
- [Short project inquiry](https://leon-ai-workflows.pages.dev/start-project)
