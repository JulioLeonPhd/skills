---
name: write-matlab-walkthrough
description: Create or improve executable MATLAB guides and examples; teach an algorithm through a runnable walkthrough when an artifact is appropriate, rather than a brief explanation or snippet.
---

# Write MATLAB walkthrough

Create or improve a walkthrough that lets an engineer understand, run, and interpret an algorithm through its public API without first reverse-engineering the implementation.
Use this for an executable learning artifact; answer brief conceptual questions or snippet requests directly.

Support MATLAB R2025a+ plain-text Live Scripts (`.m`) initially.
Keep this skill portable across projects: discover local conventions rather than imposing project names, paths, roles, or infrastructure.

## Dependency

Read the installed `matlab-create-live-script` skill before authoring or modifying a Live Script.
It owns file syntax, equations, appendix metadata, execution, output embedding, and rendering mechanics; apply those instructions rather than copying them here.
Locate it through the active environment's skill discovery or readable skill files, without assuming a particular invocation tool or installation path.
If unavailable, disclose the missing dependency and stop Live Script authoring; report any completed source inspection and what is needed to continue.

## Workflow

1. **Establish the teaching contract.** Read applicable repository instructions and discover existing walkthroughs, public API documentation, setup conventions, approved decisions, and relevant tests or reference results.
   For an existing walkthrough, read its narrative and human notes before editing.
   Identify the reader, the engineering question, prerequisites (MATLAB release, products, data, and setup), the runnable entry point and launch location, and the intended observations.
   Resolve discoverable facts from sources; ask only about unresolved consequential scope or behavior choices.
   Finish this step with a source-backed scope and artifact location, preserving approved behavior and the existing teaching intent when improving an artifact.

2. **Build the engineering story.** Organize sections around the question: purpose and assumptions, setup and inputs, processing stages, observations, and interpretation with limitations.
   Explain important design choices and their recorded rationale; distinguish approved choices from proposals and unknowns.
   Around each public API call, show the configuration that matters, identify the processing stages it represents, and explain relevant input/output units, dimensions and axis meanings, rates or time bases, and state/reset behavior.
   Define mathematical symbols and assumptions near their use.
   Include only details that affect understanding or correct use, with enough explanation for the reader to follow the transformations.
   Keep production execution at the public API boundary; explain internals from authoritative sources rather than duplicating private algorithms.
   If that boundary is too opaque to explain honestly, report the specific API or documentation gap and its effect; keep redesign outside this task unless separately authorized.
   Finish with a section sequence whose calls, transformations, and expected observations are understandable without opening private implementation files.

3. **Author the runnable artifact.** Use the dependency's format and the repository's established setup and example conventions.
   Make prerequisites and the exact entry point visible near the beginning, including required data provenance and how the reader obtains authorized inputs.
   Make initialization and reset behavior explicit so the documented starting state is reproducible.
   Prefer a small, informative scenario over a broad demonstration harness.
   Use transparent analytical expectations where useful: show assumptions, equations or simple calculations, and tolerances with their basis.
   Label an expectation derived from the same implementation or shared assumptions as a teaching aid, not an independent correctness oracle.
   Pair meaningful displayed values or plots with what the reader should observe and why; label axes, units, dimensions, and comparisons as relevant.
   Close with what the observations teach, known limits, and pointers to existing tests or independent evidence for stronger claims.
   When improving a walkthrough, preserve human annotations and intentional narrative detail; explain any necessary change to teaching intent rather than silently replacing it.
   Finish with a complete artifact that a reader can run from the documented starting state, or clearly disclose any unresolved prerequisite that prevents this.

4. **Respect execution ownership.** Before any run, embedding, or export, establish who is authorized to execute, the allowed session or environment, and the permitted output locations and side effects.
   Preserve existing human workspace variables, paths, open documents/models, and unsaved changes.
   Serialize shared-session calls unless isolation is established; a session labeled disposable or fresh is not proof of isolation.
   Inspect setup and called code for file changes, external connections, hardware access, credentials, and expensive work; use only authorized inputs and actions.
   A writing request alone does not authorize installation, environment reconfiguration, external operations, or hardware execution.
   If execution belongs to another owner or is not authorized, hand off the exact entry point and prerequisites without running it.
   When authorized tools are available, follow the dependency's execution, embedding, and rendering workflow; apply locally mandatory checks, including MATLAB Code Analyzer when available; retain only requested deliverables and evidence in approved locations.
   If MATLAB, required products, data, or preview tools are unavailable, disclose that limitation and leave the artifact explicitly unexecuted or unrendered as applicable.
   Finish with each requested check either evidenced or explicitly marked skipped, unavailable, or failed, with its reason.

5. **Inspect and hand off.** Inspect the finished narrative against the teaching contract and sources, accounting for every intended observation and preserving human notes and approved behavior.
   Report the artifact path, prerequisites, entry point, material changes, unresolved gaps, and checks actually performed.
   Keep evidence dimensions separate:

   | Dimension | Report precisely |
   | --- | --- |
   | Source inspection | Which sources support the explanation; which claims remain uncertain |
   | Execution | Whether the code ran, in which environment, and with which inputs; execution alone does not establish correctness |
   | Embedded outputs | Whether saved outputs were generated from this artifact and run; distinguish stale or absent outputs |
   | Rendering | What was inspected; HTML export is an approximation, not proof of native Live Editor appearance |
   | Correctness | Which claims have independent evidence and where it lives; walkthrough expectations alone are not independent validation |
   | Review and approval | Agent review, independent validation, and human approval are distinct; report only approvals actually recorded |

   Completion means the artifact answers the stated question, documents a reproducible entry point, explains its meaningful observations and limits, and accurately reports evidence and outstanding prerequisites.
   When checks or approvals remain pending, identify their owner or required next action without implying they passed.
