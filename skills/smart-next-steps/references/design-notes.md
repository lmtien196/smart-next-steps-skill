# Design basis and maintenance

Research date: 2026-10-09. This is an independently written personal Codex skill. It does not reproduce Manus internals or restore the user's lost original skill.

## Sources and what they support

- [birdsigh/Skills — suggest-next](https://github.com/birdsigh/Skills/blob/main/suggest-next/SKILL.md). The source was read through GitHub's public contents API. It proposes contextual continuations after work or discussion, draws on the full conversation, and discourages generic padding. Its multi-section output differs from the three compact actions requested here. No upstream implementation was installed or copied.
- [Microsoft HAX: Show contextually relevant information](https://www.microsoft.com/en-us/haxtoolkit/guideline/show-contextually-relevant-information/). Supports adapting suggestions to the current task and environment. Here this becomes the context anchor required for each proposal.
- [Microsoft HAX: Support efficient dismissal](https://www.microsoft.com/en-us/haxtoolkit/guideline/support-efficient-dismissal/). Supports keeping unwanted AI assistance easy to ignore. Here it motivates opt-out handling and presenting choices without executing them.
- [Intercom: RICE prioritization](https://www.intercom.com/blog/rice-simple-prioritization-for-product-managers). Separates reach, impact, confidence, and effort. This skill borrows qualitative attention to value, confidence, and effort, not a formal RICE calculation: ordinary chats seldom supply measured reach or trustworthy estimates.
- [Manus: Recommended connectors](https://manus.im/blog/manus-recommended-connectors). A documented adjacent example of recommendations tied to task needs with user confirmation before enabling a connector. It does not document the three-task recommendation mechanism shown in the user's screenshot, so it is not evidence for how that mechanism works.

The user's screenshot establishes the desired presentation: three short action choices connected to recent work. The Codex follow-up syntax comes from this host's supplied artifact-follow-up contract. Exact appearance and automatic skill selection depend on the host; a Markdown skill cannot force a particular visual layout or guarantee invocation on every turn.

## Decision checks for future edits

Use realistic task outcomes, not a generic instruction to recommend improvements. Check:

1. **Relevance:** Can a reviewer point to the completed work or user goal that motivates each task?
2. **Incremental value:** Does each action improve something beyond the completed scope?
3. **Evidence:** Are unknowns visible rather than converted into asserted bugs?
4. **Scope:** Does each choice have one primary outcome and a feasible finish?
5. **Independence:** Can a user select any choice without silently requiring the other choices first?
6. **User control:** Does a narrow request, opt-out, or unfinished obligation suppress suggestions appropriately?
7. **Presentation:** Are there three distinct, concise, actionable choices when justified, with self-contained prompts in the user's language?

Evaluate the content as well as its formatting. Passing a frontmatter validator does not establish useful product judgment.

## Calibration examples

- After adding catalog filters, URL persistence can make results shareable; a recovery action can help when the combination returns no products. Avoid suggesting those again once implemented.
- After a frontend duplicate-submission fix, inspecting server handling of repeated requests is grounded. Asserting that the endpoint is vulnerable without inspecting it is not grounded.
- For a salon frontend prototype with mock appointments, designing the booking API contract is a selectable next task. A separate availability prototype can use existing mock data. Shipping a live backend, staff console, and production deployment in one suggestion is too broad.
- After a requested bug fix whose required regression test still fails, complete the current work instead of offering that test as a new follow-up.
- After a one-word correction with an explicit request for no extras, give only the result.

Use these as calibration, not fixed categories or reusable boilerplate recommendations. Re-run relevant scenarios when editing selection or output rules. Keep test artifacts outside the installed skill to avoid loading evaluation fixtures in normal use.
