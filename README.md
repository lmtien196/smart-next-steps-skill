# Smart Next Steps

A Codex skill that suggests three useful next actions based on the task just completed.

It looks for concrete opportunities across product features, UI/UX, backend, testing, accessibility, and performance. Suggestions explain what to improve and why, stay grounded in the actual result, and remain optional.

## Install in Codex

Ask Codex:

```text
Use skill-installer to install https://github.com/lmtien196/smart-next-steps-skill/tree/main/skills/smart-next-steps
```

The skill will be available on your next turn. If it is already installed, ask Codex to update the existing skill from this repository.

## Use

```text
Dùng $smart-next-steps để đề xuất 3 việc tiếp theo hữu ích, bám sát task vừa hoàn thành.
```

Or in English:

```text
Use $smart-next-steps to suggest three valuable next actions based on the work we just completed.
```

Implicit invocation is enabled. Codex can select the skill after substantial work, but skill selection and clickable follow-up rendering depend on the host. Explicit invocation is the most reliable way to request it.

## What makes a good suggestion?

- Connect it to a specific result from the completed task.
- Propose one bounded improvement with a clear benefit and completion check.
- Avoid duplicate, already completed, speculative, or generic maintenance tasks.
- Offer three distinct choices when justified; fewer when context is thin.
- Finish the current task first. Do not repackage unfinished obligations as next steps.
- Respect requests for a brief answer or no extra suggestions.
- Never execute suggested work until the user chooses it.

For example, after adding product filters, useful follow-ups might include shareable filter URLs, recovery from empty results, or focused regression coverage for a demonstrated edge case. These are examples, not fixed categories.

## Files

- [Skill instructions](skills/smart-next-steps/SKILL.md)
- [Codex metadata](skills/smart-next-steps/agents/openai.yaml)
- [Research sources and design notes](skills/smart-next-steps/references/design-notes.md)

The skill is independently written. The design notes distinguish verified sources from inspiration; this is not a reproduction of Manus internals.
