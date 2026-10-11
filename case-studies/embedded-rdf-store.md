# Adding an embedded RDF storage option

**Independent open-source contribution by Linxiushen. Merged on August 6, 2026.**

## Problem

Semantica's `TripletStore` needed a documented embedded backend with memory and local persistence alongside its other store options. The contribution gives development, tests and local workloads an optional Oxigraph store that can query RDF in the same process.

The requirement included compatibility with the existing interface: named graphs, SPARQL result shapes, and RDF literal language and datatype metadata needed to survive the storage boundary.

## Change

The contribution adds `OxigraphStore` through an optional PyOxigraph dependency and connects it to `TripletStore(backend="oxigraph")`. The store runs in memory by default or persists to a local directory supplied through `path`.

The implementation includes batch loading, reads and deletion, named-graph support, SPARQL result mapping, and preservation of literal metadata. Documentation and install examples explain the new extra. PyOxigraph is imported when the backend is constructed, so baseline imports work without the extra installed.

Review identified that the outer `TripletStore` wrapper masked the missing optional dependency as a generic processing failure. The follow-up preserves `ImportError` and its install hint, with a regression exercising the public wrapper.

## Historical validation and limits

The public PR and the author's review reply report **318 tests passed and 37 subtests passed** for `python -m pytest tests/triplet_store -q`, along with a wheel build and formatting/lint checks. The PR reports that the new backend tests also passed with the declared minimum dependency, `pyoxigraph==0.5.0`.

The committed integration tests exercise CRUD and literal metadata, named-graph isolation, SELECT/ASK/CONSTRUCT result shapes, reopening persisted data, invalid inputs and the missing-dependency message. The module skips when PyOxigraph is absent; the public review reply records that upstream CI did not run the Python test suite.

These are historical PR validation results, not tests rerun for this case study. This portfolio review inspected the saved code and test assertions but did not audit the original execution logs. No performance benchmark or distributed production deployment was validated. The documentation continues to recommend server-backed stores for distributed production use.

## Evidence and implementation relevance

[PR #838](https://github.com/semantica-agi/semantica/pull/838), its [changed files](https://github.com/semantica-agi/semantica/pull/838/files), and the [validation follow-up](https://github.com/semantica-agi/semantica/pull/838#issuecomment-5193161237) provide the implementation and review. Authorship and merged status were rechecked on October 11, 2026.

For AI and knowledge applications, this shows how an optional storage adapter can support local work while preserving an existing interface and providing a clear dependency failure. This was independent open-source work, not a customer deployment or a Semantica employment relationship.
