# Saving workflow structure from the document tree

**Independent open-source contribution by Linxiushen. Merged on September 29, 2026.**

## Problem

A visual workflow editor maintains both the document being edited and the tree used to render it. In FlowGram, moving nodes and immediately exporting JSON could attach a node to its previous parent. A separate display-only branch refinement could also change the parent relationship written to the saved document.

The relevant requirement was precise: exported JSON should describe the current document structure, including when rendering has not yet caught up with an editing operation.

## Root cause

`FlowDocument.toNodeJSON` traversed the origin document tree but obtained each parent through `node.parent`, which reflected the render tree. `dragNodes` updated the origin tree synchronously, while a previous render snapshot could survive until the next layer refresh.

This mixed two sources of truth within one export. Even after a refresh, `END_NODES_REFINE_BRANCH` could introduce a parent relationship intended only for display. Serializing that relationship leaked a presentation choice into persistent workflow data.

## Change

The production change obtains the parent through `this.originTree.getParent(node)`. Existing handling for generated system nodes through `parent.originParent` remains in place.

The fix stays within JSON serialization. It does not change public render-tree getters or rendering schedules. The associated issue concerns broader timing behavior, so this contribution does not claim to resolve every symptom reported there.

## Validation and limits

The regressions use the actual document container and `FlowOperationBaseService.dragNodes`. They prime a render snapshot, move nodes in both cross-branch directions, and check whole-document and subtree exports before refresh. They also check exports after refresh, display-only branch refinement, and collapse.

On the unchanged baseline, the affected document package recorded **three failing new regressions and 52 passing existing tests**. With the fix, **all 55 tests across ten files passed**. Saved validation also records successful dependency builds, the document package build, type checking, and configured lint checks.

These historical checks ran in an isolated Linux environment after a Windows package-manager junction error. They were not rerun for this case study. The tests reproduced a pending render snapshot without a browser renderer; browser end-to-end testing and the full monorepo were not run. No visual or production outcome is claimed.

## Evidence and implementation relevance

[PR #1200](https://github.com/bytedance/flowgram.ai/pull/1200) and its [changed files](https://github.com/bytedance/flowgram.ai/pull/1200/files) provide the patch and review. Authorship and merged status were rechecked on October 4, 2026.

For AI workflow implementation, this demonstrates why editable business logic and its presentation need distinct persistence rules. A small correction can be checked through real editing operations and explicit export assertions. I used an **AI-assisted workflow**; this was independent open-source work, not ByteDance employment or a client project.
