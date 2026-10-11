# Chen Xulin · Linxiushen

**Independent FDE engineer / AI implementation consultant.** I build workflow integrations and contribute fixes to the tools behind them: MCP gateways, agent workflows, Python AI tooling and workflow data integrity.

[Contribution index](contributions/README.md) · [Engineering case studies](case-studies/README.md) · [Website](https://leon-ai-workflows.pages.dev/) · [Email](mailto:m15178824683@gmail.com)

## Selected merged contributions

Each entry links to the upstream implementation, review and merge record. The case studies explain the problem, design choice, validation and limits.

| Project | What changed | Evidence | Merged (UTC) |
| --- | --- | --- | --- |
| IBM MCP Context Forge | Preserve saved MCP catalogs after empty OAuth discovery; check retained tool aliases. | [PR #6049](https://github.com/IBM/mcp-context-forge/pull/6049) · [Case study](case-studies/ibm-mcp-catalog.md) | 2026-10-02 |
| OpenAI Codex Security | Exclude nested Git metadata and linked-worktree pointers from scan inventories. | [PR #1099](https://github.com/openai/codex-security/pull/1099) · [Case study](case-studies/codex-security-inventory.md) | 2026-09-30 |
| Semantica | Add an optional embedded RDF/SPARQL store with memory and local persistence. | [PR #838](https://github.com/semantica-agi/semantica/pull/838) · [Case study](case-studies/embedded-rdf-store.md) | 2026-08-06 |
| Hugging Face Accelerate | Return the serialized parallelism configuration instead of None. | [PR #4326](https://github.com/huggingface/accelerate/pull/4326) · [Case study](case-studies/parallelism-config-serialization.md) | 2026-09-25 |
| Tencent AI-Infra-Guard | Keep remediation text while emitting schema-valid SARIF. | [PR #680](https://github.com/Tencent/AI-Infra-Guard/pull/680) · [Case study](case-studies/sarif-compatibility.md) | 2026-10-03 |
| ByteDance FlowGram | Serialize moved-node parents from the authoritative document tree. | [PR #1200](https://github.com/bytedance/flowgram.ai/pull/1200) · [Case study](case-studies/workflow-serialization.md) | 2026-09-29 |

**47 merged PRs in external repositories** in the verified inventory as of October 11, 2026. [Browse all 47](contributions/README.md#merged-contribution-index). This counts merged PRs, not production deployments or ownership of those projects.

These are independent open-source contributions, not employment, client engagements or endorsements by the organizations listed. I use AI-assisted tools. Historical test results and their scope are attributed in each case study.

## Projects I maintain

| Project | Purpose | Start here |
| --- | --- | --- |
| [HarnessLab](https://github.com/Linxiushen/harnesslab) | Record and compare agent execution traces; gate changes to lifecycle, tool and approval behavior. | [Offline quickstart](https://github.com/Linxiushen/harnesslab#30-second-quickstart) · [Static fixture demo](https://linxiushen.github.io/harnesslab/) |
| [dsh-workflow-isolate](https://github.com/Linxiushen/dsh-workflow-isolate) | Experimental QuickJS/WASM workflow provider with guest resource budgets and cancellation controls. | [Architecture](https://github.com/Linxiushen/dsh-workflow-isolate/blob/main/docs/architecture.md) · [Security limits](https://github.com/Linxiushen/dsh-workflow-isolate/blob/main/docs/security-model.md) |
| [dsh-repro-kit](https://github.com/Linxiushen/dsh-repro-kit) | Slice an agent session export into a deterministic, redacted reproduction bundle for debugging. | [CLI and library](https://github.com/Linxiushen/dsh-repro-kit#quick-start) · [Format](https://github.com/Linxiushen/dsh-repro-kit/blob/main/docs/FORMAT.md) |

These are independent projects. The isolate provider is experimental and has not been independently security-audited. Reproduction bundles still need human review before public sharing. Compatibility boundaries are documented in the repositories.

## Applied AI workflows

[Connecting design and office workflows through Codex](case-studies/codex-business-workflows.md) describes an anonymized delivered project: a shared work entry point, reusable company Skills and information flows across business platforms. The article describes the project-level change without publishing client identity or unverified outcome figures.

[Implementation services](services.md) · [Workflow assessment](workflow-assessment.md) · [Prepare a short brief](workflow-brief.md) · [Synthetic workflow demo](https://leon-ai-workflows.pages.dev/demo/)

The website demos use synthetic data and have no live client integrations.

## Work with me

I work remotely in English, with up to **40 hours per week across all engagements**. Scope, meeting overlap, milestones and fees are agreed per engagement.

Email **[m15178824683@gmail.com](mailto:m15178824683@gmail.com)** with the workflow you want to improve and the systems involved. A sanitized example helps make the first discussion concrete.
