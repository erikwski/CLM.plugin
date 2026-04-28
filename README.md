# Datacolor Claude Skills Plugin

Shared Claude Code skills for the Datacolor team.

## Skills

| Skill         | Command                           | Description                                                                               |
| ------------- | --------------------------------- | ----------------------------------------------------------------------------------------- |
| PBI to Prompt | `/datacolor-skills:pbi-to-prompt` | Turns a PBI title, description, and acceptance criteria into a ready-to-use Claude prompt |

## How to install

### Prerequisites

- [Claude Code](https://claude.ai/code) installed and authenticated

### Install from this repo

Run this command inside Claude Code (the chat input, not the terminal):

```
/plugin install https://github.com/erikwski/CLM.plugin
```

Replace the URL with the actual GitHub/GitLab URL where this repo is hosted.

### Verify the install

```
/datacolor-skills:pbi-to-prompt
```

Claude will ask you for the PBI details and generate the prompt.

## How to use the PBI-to-Prompt skill

1. Open Claude Code in any project.
2. Type `/datacolor-skills:pbi-to-prompt`.
3. Paste or type your PBI details when prompted:
   - **Title** — e.g. "Export report as PDF"
   - **Description** — the full backlog item body
   - **Acceptance Criteria** — the numbered or bulleted list of conditions
4. Claude returns a polished prompt you can paste into a new conversation to start implementation.

## Adding new skills

1. Clone this repo.
2. Create a new folder under `skills/` — the folder name becomes the slash-command suffix.
3. Add a `SKILL.md` with a `description` frontmatter field and instructions for Claude.
4. Open a PR. Once merged, colleagues can `/plugin install` or run `/reload-plugins` to pick up the new skill.

### Skill file template

```markdown
---
description: One sentence explaining what this skill does and when to use it.
---

Instructions for Claude go here.
Use $ARGUMENTS to capture anything the user types after the command name.
```

## Contributing

Open a PR against `main`. Keep each skill focused on a single task.
