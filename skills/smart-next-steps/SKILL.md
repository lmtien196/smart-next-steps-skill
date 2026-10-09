---
name: smart-next-steps
description: Use after completing a substantial user task to suggest useful follow-on actions grounded in its actual outcome, or when the user asks what to improve or do next. Especially relevant to product features, UI/UX, backend, testing, and performance. Skip unsolicited suggestions for greetings, simple factual answers, tiny edits, or requests for only the result.
---

# Smart Next Steps

Help the user see three worthwhile next moves they might not have thought of. Tie each to the work just completed and an outcome the user cares about. Use the user's language; default to Vietnamese in Vietnamese conversations.

## Choose the moment

Append suggestions once, after the substantive completion summary. When explicitly asked for next steps, answer directly without repeating that summary.

Complete outstanding authorized work and required verification first. A failing required test, a regression introduced by the change, or unfinished requested functionality belongs to the current task. Continue that work; when genuinely blocked, explain the blocker. Suggestions must not turn unfinished obligations into optional new tasks.

Respect requests for brevity, a particular format, or no suggestions. For a tiny edit or an informational reply, omit automatic suggestions. An explicit request for next steps can still activate the skill.

## Find useful opportunities

Use the conversation and artifacts already inspected to establish the user's goal, what actually changed, what was verified, important constraints, and ideas already rejected or completed. Do not start a broad audit or web research just to fill three slots. If a requested recommendation depends on an unknown fact, make a bounded inspection the proposed action rather than claiming a defect exists.

Consider several plausible opportunities across whichever dimensions fit:

- **Capability:** the adjacent user job now enabled, a useful workflow shortcut, or a small feature that removes a real obstacle.
- **Experience:** a concrete interaction, recovery path, accessibility need, content problem, or visual inconsistency on the surface just touched.
- **Engineering:** a relevant API/data boundary, reliability risk, integration gap, measured performance issue, or targeted behavioral check.

These are lenses, not three mandatory categories. Broaden naturally for research, documents, or other tasks. Avoid habitual suggestions to add dashboards, AI, authentication, payments, dark mode, analytics, or tests without a clear connection. A useful feature or UX improvement can outrank another engineering check.

For each candidate, identify: **context anchor → proposed action → user benefit → completion check**. Distinguish an observed problem from a proposed enhancement. Treat uninspected code, unknown performance, and assumed missing features as unknown. Put any assumption that affects execution into the follow-up prompt.

Rank by connection to the user's goal, concrete benefit, confidence in the evidence, and effort proportional to the project. Prefer a small high-value change over an impressive but speculative feature. Use qualitative judgment; invent neither metrics nor numeric prioritization scores.

## Select three coherent choices

Default to three distinct suggestions, strongest first. Each is a selectable task with one primary outcome and a clear finish. Include relevant verification inside its task, rather than spending another slot on tests for the same hypothetical change.

Check the set before presenting it:

- Each task adds value beyond work already completed; none repeats rejected advice.
- Each task is useful if selected alone. If it depends on an unbuilt prerequisite, propose a bounded design/prototype/inspection or state the prerequisite explicitly. Never silently assume another suggestion was executed.
- No item bundles unrelated backend, redesign, administration, and deployment projects. Separate or narrow it.
- Benefits describe a plausible improvement, not a guaranteed conversion or performance gain.
- Existing stack, offline/local-only requirements, excluded features, and relevant authorization limits carry into each prompt.

If evidence supports fewer than three worthwhile actions, present fewer rather than padding. Never invent defects to reach a quota.

## Render as actionable follow-ups

In Codex, use one unescaped Markdown list item per selected action (normally three) in this supported format, with a blank line before the list:

`- :codex-followup[Action and short benefit]{prompt="A self-contained request describing the target, bounded action, relevant constraint, and concrete completion check."}`

Write a short verb-led visible label, preferably including the benefit. Keep the prompt to one to three sentences; name the actual page, flow, feature, or artifact. Avoid closing brackets in labels and escape double quotes inside prompt attributes. Do not wrap real directives in a code fence. Without support for these controls, use a plain numbered list with one concise sentence per action.

Example after finishing working catalog filters:

- :codex-followup[Lưu bộ lọc trên URL để chia sẻ kết quả]{prompt="Bổ sung đồng bộ bộ lọc danh mục và giá của trang danh mục sản phẩm vào URL. Dùng router hiện có; kiểm tra tải lại trang và nút Back khôi phục đúng bộ lọc."}

Present suggestions only; do not execute them, create tasks, install dependencies, deploy, or schedule follow-ups merely because they appear. A selected suggestion becomes a new user request subject to its stated scope and the host's permissions.

For maintaining or evaluating this skill, see [design-notes.md](references/design-notes.md); routine suggestion generation does not require that reference.
