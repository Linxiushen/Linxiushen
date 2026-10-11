# Open-source contribution index

Independent contributions by **[Linxiushen](https://github.com/Linxiushen)**. Snapshot: **October 11, 2026**. GitHub state checked at 2026-10-11T05:44:34.926Z. The linked upstream PR is the authority for implementation, review and merge status.

## Engineering case studies

- **[IBM MCP Context Forge #6049](https://github.com/IBM/mcp-context-forge/pull/6049)** — Preserve saved MCP catalogs after empty OAuth discovery; check retained tool aliases. [Problem, design and validation](../case-studies/ibm-mcp-catalog.md).
- **[OpenAI Codex Security #1099](https://github.com/openai/codex-security/pull/1099)** — Exclude nested Git metadata and linked-worktree pointers from scan inventories. [Problem, design and validation](../case-studies/codex-security-inventory.md).
- **[Semantica #838](https://github.com/semantica-agi/semantica/pull/838)** — Add an optional embedded RDF/SPARQL store with memory and local persistence. [Problem, design and validation](../case-studies/embedded-rdf-store.md).
- **[Hugging Face Accelerate #4326](https://github.com/huggingface/accelerate/pull/4326)** — Return the serialized parallelism configuration instead of None. [Problem, design and validation](../case-studies/parallelism-config-serialization.md).
- **[Tencent AI-Infra-Guard #680](https://github.com/Tencent/AI-Infra-Guard/pull/680)** — Keep remediation text while emitting schema-valid SARIF. [Problem, design and validation](../case-studies/sarif-compatibility.md).
- **[ByteDance FlowGram #1200](https://github.com/bytedance/flowgram.ai/pull/1200)** — Serialize moved-node parents from the authoritative document tree. [Problem, design and validation](../case-studies/workflow-serialization.md).

## Merged contribution index

**47 merged PRs across 28 external repositories.** Own-repository PRs are excluded. This is a dated status index, not an assertion that every PR received the same validation or that every change is deployed in production. Detailed evidence and historical test limits are in the selected case studies; the remaining rows link directly to the upstream record.

| Repository | PR / change | Merged (UTC) |
| --- | --- | --- |
| [TencentCloudADP/youtu-rag](https://github.com/TencentCloudADP/youtu-rag) | [#14: fix(storage): preserve NumPy embeddings in Chroma lookups](https://github.com/TencentCloudADP/youtu-rag/pull/14) | 2026-10-08 |
| [Tencent/WeKnora](https://github.com/Tencent/WeKnora) | [#3802: fix(chat): clear stale file and tool selections on session restore](https://github.com/Tencent/WeKnora/pull/3802) | 2026-10-07 |
| [microsoft/onnxscript](https://github.com/microsoft/onnxscript) | [#3056: Fix last-element indexing mixed with slices or scalar indices](https://github.com/microsoft/onnxscript/pull/3056) | 2026-10-07 |
| [huggingface/datasets](https://github.com/huggingface/datasets) | [#8677: Fix inverted span for minus-strand multi-exon GenBank locations](https://github.com/huggingface/datasets/pull/8677) | 2026-10-05 |
| [Tencent/AI-Infra-Guard](https://github.com/Tencent/AI-Infra-Guard) | [#680: fix(sarif): preserve text remediation in valid results](https://github.com/Tencent/AI-Infra-Guard/pull/680) | 2026-10-03 |
| [Tencent/AI-Infra-Guard](https://github.com/Tencent/AI-Infra-Guard) | [#671: fix(deepteam): RailFence crashes with IndexError when rails <= 1](https://github.com/Tencent/AI-Infra-Guard/pull/671) | 2026-10-03 |
| [IBM/mcp-context-forge](https://github.com/IBM/mcp-context-forge) | [#6049: fix(oauth): preserve gateway catalog on empty fetch](https://github.com/IBM/mcp-context-forge/pull/6049) | 2026-10-02 |
| [Tencent/AngelSlim](https://github.com/Tencent/AngelSlim) | [#387: fix(data): count Hugging Face samples after token packing](https://github.com/Tencent/AngelSlim/pull/387) | 2026-10-01 |
| [openai/codex-security](https://github.com/openai/codex-security) | [#1099: fix(plugin): exclude nested Git metadata from scan inventories](https://github.com/openai/codex-security/pull/1099) | 2026-09-30 |
| [openai/codex-security](https://github.com/openai/codex-security) | [#1098: fix(plugin): preserve source excerpt line numbering](https://github.com/openai/codex-security/pull/1098) | 2026-09-30 |
| [modelscope/evalscope](https://github.com/modelscope/evalscope) | [#1760: fix(perf): keep a rerank request successful when the top score is not a number](https://github.com/modelscope/evalscope/pull/1760) | 2026-09-29 |
| [Tencent/MemoryForge](https://github.com/Tencent/MemoryForge) | [#1: fix: preserve participant IDs when resuming mapping exports](https://github.com/Tencent/MemoryForge/pull/1) | 2026-09-29 |
| [bytedance/flowgram.ai](https://github.com/bytedance/flowgram.ai) | [#1200: fix(document): serialize parents from the origin tree](https://github.com/bytedance/flowgram.ai/pull/1200) | 2026-09-29 |
| [datajuicer/data-juicer](https://github.com/datajuicer/data-juicer) | [#1076: fix(filter): support unary operators in general_field_filter conditions](https://github.com/datajuicer/data-juicer/pull/1076) | 2026-09-28 |
| [huggingface/accelerate](https://github.com/huggingface/accelerate) | [#4326: Fix ParallelismConfig.to_json returning None instead of the config dict](https://github.com/huggingface/accelerate/pull/4326) | 2026-09-25 |
| [Tencent/AngelSlim](https://github.com/Tencent/AngelSlim) | [#384: fix: quant_analyse crashes on per-channel/group weight scales](https://github.com/Tencent/AngelSlim/pull/384) | 2026-09-25 |
| [Tencent/AngelSlim](https://github.com/Tencent/AngelSlim) | [#385: fix: import GLM5 fused experts under transformers>=5.13](https://github.com/Tencent/AngelSlim/pull/385) | 2026-09-25 |
| [OpenHands/automation](https://github.com/OpenHands/automation) | [#306: fix: reconcile model index declarations](https://github.com/OpenHands/automation/pull/306) | 2026-09-25 |
| [bytedance/deer-flow](https://github.com/bytedance/deer-flow) | [#5640: fix(slack): log Socket Mode connect failures instead of dropping them](https://github.com/bytedance/deer-flow/pull/5640) | 2026-09-25 |
| [huggingface/datatrove](https://github.com/huggingface/datatrove) | [#528: fix(filters): GopherRepetitionFilter raises ZeroDivisionError on empty documents](https://github.com/huggingface/datatrove/pull/528) | 2026-09-24 |
| [Tencent-Hunyuan/HunyuanOCR](https://github.com/Tencent-Hunyuan/HunyuanOCR) | [#131: fix(train_verl): keep parenthesised text when parsing format3 spotting answers](https://github.com/Tencent-Hunyuan/HunyuanOCR/pull/131) | 2026-09-24 |
| [Tencent-Hunyuan/AuK](https://github.com/Tencent-Hunyuan/AuK) | [#24: fix(pe): remove the temp file left behind when torchaudio.save fails](https://github.com/Tencent-Hunyuan/AuK/pull/24) | 2026-09-22 |
| [datajuicer/data-juicer](https://github.com/datajuicer/data-juicer) | [#1073: fix(app): avoid KeyError when no filter OP provides tunable stats](https://github.com/datajuicer/data-juicer/pull/1073) | 2026-09-22 |
| [datajuicer/data-juicer](https://github.com/datajuicer/data-juicer) | [#1074: fix(analysis): refine overall stats columns by the first non-null value](https://github.com/datajuicer/data-juicer/pull/1074) | 2026-09-22 |
| [modelscope/modelscope-studio](https://github.com/modelscope/modelscope-studio) | [#128: fix(antdx): FileCard / FileCard.List.Item crash when `src` is a file dict without `url`](https://github.com/modelscope/modelscope-studio/pull/128) | 2026-09-22 |
| [modelscope/evalscope](https://github.com/modelscope/evalscope) | [#1757: fix: give logger calls a placeholder for their extra positional arguments](https://github.com/modelscope/evalscope/pull/1757) | 2026-09-21 |
| [modelscope/evalscope](https://github.com/modelscope/evalscope) | [#1758: fix(agent): remove the temporary HOME after codex/hermes/gemini-cli runs](https://github.com/modelscope/evalscope/pull/1758) | 2026-09-21 |
| [modelscope/ms-swift](https://github.com/modelscope/ms-swift) | [#10217: fix(ui): catch TypeError in the more_params handlers](https://github.com/modelscope/ms-swift/pull/10217) | 2026-09-21 |
| [Tencent/WeKnora](https://github.com/Tencent/WeKnora) | [#3495: fix: remove temp file when TempFileContext write fails inside __enter__](https://github.com/Tencent/WeKnora/pull/3495) | 2026-09-21 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | [#863: [fix] float16 下 attention mask 的 -1e9 溢出成 -inf，导致整条序列输出 NaN](https://github.com/jingyaogong/minimind/pull/863) | 2026-09-20 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | [#860: [fix] train_tokenizer 读预训练语料时产出 0 条文本，静默训出空词表](https://github.com/jingyaogong/minimind/pull/860) | 2026-09-20 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | [#865: [fix] requirements.txt 缺 fastapi/uvicorn，按 README 跑 serve_openai_api.py 直接崩](https://github.com/jingyaogong/minimind/pull/865) | 2026-09-20 |
| [jingyaogong/minimind](https://github.com/jingyaogong/minimind) | [#864: [fix] serve_openai_api 非流式端点的 max_tokens 不生效，与流式端点行为不一致](https://github.com/jingyaogong/minimind/pull/864) | 2026-09-20 |
| [OpenHands/automation](https://github.com/OpenHands/automation) | [#303: perf: remove redundant readiness query](https://github.com/OpenHands/automation/pull/303) | 2026-08-20 |
| [0xsline/awesome-deepseek-harness](https://github.com/0xsline/awesome-deepseek-harness) | [#378: docs: add dsh-workflow-isolate](https://github.com/0xsline/awesome-deepseek-harness/pull/378) | 2026-08-18 |
| [Anil-matcha/awesome-vibecoded-saas](https://github.com/Anil-matcha/awesome-vibecoded-saas) | [#27: docs: add dsh-workflow-isolate](https://github.com/Anil-matcha/awesome-vibecoded-saas/pull/27) | 2026-08-18 |
| [imsai-sh/awesome-deepseek-harness-plugins](https://github.com/imsai-sh/awesome-deepseek-harness-plugins) | [#57: catalog: add dsh-workflow-isolate](https://github.com/imsai-sh/awesome-deepseek-harness-plugins/pull/57) | 2026-08-18 |
| [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | [#720: fix(updater): discard stale version hints](https://github.com/alibaba/open-code-review/pull/720) | 2026-08-17 |
| [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | [#717: fix(opencode): separate per-file and overall timeouts](https://github.com/alibaba/open-code-review/pull/717) | 2026-08-14 |
| [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | [#732: fix(agent): stabilize review item fingerprints](https://github.com/alibaba/open-code-review/pull/732) | 2026-08-14 |
| [a2aproject/a2a-go](https://github.com/a2aproject/a2a-go) | [#391: fix(tck): advertise extended agent card support](https://github.com/a2aproject/a2a-go/pull/391) | 2026-08-11 |
| [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | [#739: fix(viewer): stack suggested code panels](https://github.com/alibaba/open-code-review/pull/739) | 2026-08-10 |
| [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | [#716: feat(config): make per-file token limit configurable](https://github.com/alibaba/open-code-review/pull/716) | 2026-08-07 |
| [alibaba/open-code-review](https://github.com/alibaba/open-code-review) | [#738: feat(viewer): collapse secondary session sections](https://github.com/alibaba/open-code-review/pull/738) | 2026-08-06 |
| [semantica-agi/semantica](https://github.com/semantica-agi/semantica) | [#838: feat(triplet-store): add embedded Oxigraph backend](https://github.com/semantica-agi/semantica/pull/838) | 2026-08-06 |
| [OpenHands/automation](https://github.com/OpenHands/automation) | [#301: fix: normalize SQLite telemetry timestamps](https://github.com/OpenHands/automation/pull/301) | 2026-08-06 |
| [mastra-ai/mastra](https://github.com/mastra-ai/mastra) | [#20736: fix(github-signals): suppress noisy activity notifications](https://github.com/mastra-ai/mastra/pull/20736) | 2026-08-05 |

## Browse current work

[Authored open PRs](https://github.com/pulls?q=is%3Apr+is%3Aopen+author%3ALinxiushen) · [Authored merged PRs](https://github.com/pulls?q=is%3Apr+is%3Amerged+author%3ALinxiushen) · [Profile](../README.md)

Open PRs are proposals under review. They are not presented as merged work. These contributions do not establish employment or organizational endorsement.
