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

### 1. Establish the teaching contract

Purpose: identify the reader, engineering question, reproducible starting point, and source-backed scope.

Read applicable repository instructions and discover existing walkthroughs, public API documentation, setup conventions, approved decisions, and relevant tests or reference results.
For an existing walkthrough, read its narrative and human notes before editing.
Identify prerequisites (MATLAB release, products, data, and setup), the runnable entry point and launch location, and the intended observations.
Resolve discoverable facts from sources; ask only about unresolved consequential scope or behavior choices.
Finish with a source-backed scope and artifact location, preserving approved behavior and the existing teaching intent when improving an artifact.

### 2. Build the engineering story

Purpose: make the algorithm and its public-API stages understandable without reverse-engineering the implementation.

Organize a navigable sequence of numbered section headings with short purpose statements.
Let the reader's question determine the sections and their order; do not impose a fixed template.
Introduce the walkthrough's purpose and starting requirements, then conclude with the lessons and limits the observations support.
Use concise engineering facts, choosing prose, bullets, tables, or a diagram when each best clarifies the material.
Explain important design choices and their recorded rationale; distinguish approved choices from proposals and unknowns.
For each public API call, put relevant configuration, assumptions, input units and dimensions, rates or time bases, and transparent expectations before the call; explain relevant state/reset behavior around it, and after it document returned output units, dimensions and axis meanings and interpret the observations.
Define mathematical symbols and assumptions near their use.
Keep production execution at the public API boundary; explain internals from authoritative sources rather than duplicating private algorithms.
Finish only when the processing stage represented by every public API call is explicit, and its transformations and observations can be understood without opening private implementation files.
If that boundary is too opaque to explain honestly, report the specific API or documentation gap and its effect; keep redesign outside this task unless separately authorized.

### 3. Author the runnable artifact

Purpose: turn the teaching story into an executable, interpretable walkthrough.

Use the dependency's format and the repository's established setup and example conventions.
Make prerequisites and the exact entry point visible near the beginning, including required data provenance and how the reader obtains authorized inputs.
Make initialization and reset behavior explicit so the documented starting state is reproducible.
Prefer a small, informative scenario over a broad demonstration harness.
Use transparent analytical expectations where useful: show assumptions, equations or simple calculations, and tolerances with their basis.
Label an expectation derived from the same implementation or shared assumptions as a teaching aid, not an independent correctness oracle.
Pair meaningful displayed values and plots with what the reader should observe and why.

- Choose zoom and dynamic range that keep relevant behavior interpretable without concealing important features.
- Label axes with units; describe synthetic, uncalibrated amplitudes as dimensionless. For dB plots, name the measured quantity and reference (for example, dB relative to amplitude 1); do not imply physical units or calibration that the source does not establish. Explain how exact zeros and invalid samples are handled through any logarithmic conversion.
- Use common scales and references when comparing streams; use separate panels when an overlay makes them hard to distinguish.
- Choose axis limits and panel count for the data and question; no fixed panel layout or universal dB limits are required. Orient annotations for readability and size the figure canvas for its content when useful, without promising a particular Live Editor display size.

When a walkthrough needs local helper functions, place them in a clearly titled final section, numbered consistently with the other sections. Explain each helper's purpose and any setup or cleanup side effects, and distinguish walkthrough helpers from the algorithm and public API. Do not add helpers when direct code is clearer.

When improving a walkthrough, preserve human annotations and intentional narrative detail; explain any necessary change to teaching intent rather than silently replacing it.
Finish with a complete artifact that a reader can run from the documented starting state, or clearly disclose any unresolved prerequisite that prevents this.

### 4. Respect execution ownership

Purpose: run, embed, or render only within an authorized environment and scope.

Before any run, embedding, or export, establish who is authorized to execute, the allowed session or environment, and the permitted output locations and side effects.
Preserve existing human workspace variables, paths, open documents/models, and unsaved changes.
Serialize shared-session calls unless isolation is established; a session labeled disposable or fresh is not proof of isolation.
Inspect setup and called code for file changes, external connections, hardware access, credentials, and expensive work; use only authorized inputs and actions.
A writing request alone does not authorize installation, environment reconfiguration, external operations, or hardware execution.
If execution belongs to another owner or is not authorized, hand off the exact entry point and prerequisites without running it.
When authorized tools are available, follow the dependency's execution, embedding, and rendering workflow; apply locally mandatory checks, including MATLAB Code Analyzer when available; retain only requested deliverables and evidence in approved locations.
If MATLAB, required products, data, or preview tools are unavailable, disclose that limitation and leave the artifact explicitly unexecuted or unrendered as applicable.
Finish with each requested check either evidenced or explicitly marked skipped, unavailable, or failed, with its reason.

### 5. Obtain independent review

Purpose: have another agent scrutinize the actual walkthrough and the strength of its claims.

After the first complete authoring pass, request an independent agent review of the actual executable walkthrough, not only its plan or outline.
Have the reviewer inspect the narrative and code, mathematical expectations, available outputs, and the limits of the evidence presented.
An author self-check, plan review, or production tests do not substitute for this independent review.
Resolve review findings, and request another independent review after material corrections.
If an independent reviewer is unavailable, report review as pending and do not imply the walkthrough is complete.

### 6. Inspect and hand off

Purpose: report what the artifact teaches and keep every evidence and approval dimension distinct.

Inspect the finished narrative against the teaching contract and sources, accounting for every intended observation and preserving human notes and approved behavior.
Report the artifact path, prerequisites, entry point, material changes, unresolved gaps, and checks actually performed.
Keep evidence dimensions separate:

| Dimension | Report precisely |
| --- | --- |
| Source inspection | Which sources support the explanation; which claims remain uncertain |
| Execution | Whether the code ran, in which environment, and with which inputs; execution alone does not establish correctness |
| Embedded outputs | Whether saved outputs were generated from this artifact and run; distinguish stale or absent outputs |
| Rendering | What was inspected; HTML export is an approximation, not proof of native Live Editor appearance |
| Correctness | Which claims have independent evidence and where it lives; walkthrough expectations alone are not independent validation |
| Independent review | Whether an agent reviewed the actual artifact, its findings, their resolution, and any required re-review |
| Human approval and delivery | Approval only when recorded and required by local policy; apply local rules for delivery. This skill does not universally require human approval, tracked files, commits, repository inclusion, or version control; ignored personal learning artifacts may be valid |

Completion means the artifact answers the stated question, documents a reproducible entry point, explains its meaningful observations and limits, and accurately reports evidence and outstanding prerequisites.
Independent review and its findings must be resolved before reporting completion; if review is pending, hand off the artifact as incomplete.
