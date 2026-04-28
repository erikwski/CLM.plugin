---
name: pbi-to-prompt
description: Converts a PBI (Product Backlog Item) title, description, and acceptance criteria into a clear, actionable Claude prompt ready to paste. Use when you have a PBI and want to generate a prompt for Claude to implement or analyze it.
---

You are helping turn a PBI into a focused Claude prompt.

The user will provide (in $ARGUMENTS or in the conversation):

- **PBI Title** — the short name of the backlog item
- **Description** — the "As a ... I want ... so that ..." or free-text body
- **Acceptance Criteria** — the list of conditions that define "done"

Your job is to produce a single, self-contained prompt that a developer can paste directly into Claude to get implementation help. Follow these rules:

1. Start the prompt with a one-sentence context line that names the feature and its user-facing goal.
2. Translate each acceptance criterion into a concrete requirement or constraint. Use imperative language ("The system must …", "Return …", "Validate that …").
3. If the PBI implies a specific technology, file, or component, name it explicitly in the prompt.
4. End the prompt with: "Ask me for any missing details before writing code."
5. Output only the finished prompt — no preamble, no explanation, no markdown wrapper around it.

If the user has not yet provided the PBI details, ask them to share the title, description, and acceptance criteria before generating the prompt.
