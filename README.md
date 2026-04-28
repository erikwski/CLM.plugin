# Datacolor Claude Skills Plugin

Shared Claude Code skills for the Datacolor team.

## Skills

| Skill         | Command                           | Description                                                                               |
| ------------- | --------------------------------- | ----------------------------------------------------------------------------------------- |
| PBI to Prompt | `/datacolor-skills:pbi-to-prompt` | Turns a PBI title, description, and acceptance criteria into a ready-to-use Claude prompt |

---

## For designers and POs (claude.ai web app)

Skills are a Claude Code feature and don't exist on the claude.ai web app.
The equivalent is a shared **Project with custom instructions**.

See [docs/claude-project-instructions.md](docs/claude-project-instructions.md) for:
- The instruction block to paste into the Project settings
- Step-by-step setup guide
- An example input/output

---

## How to install (Claude Code / developers)

There are two ways to use these skills.

---

### Option A — Project-level (recommended for shared repos)

Copy the skills into any project that already uses Claude Code. The skills will be available to everyone who works in that project.

```bash
# From the root of the target project:
git clone https://github.com/erikwski/CLM.plugin /tmp/clm-plugin
cp -r /tmp/clm-plugin/skills .claude/skills
```

Then inside Claude Code:

```
/datacolor-skills:pbi-to-prompt
```

> The `.claude/skills/` folder is loaded automatically by Claude Code. Commit it so the whole team shares it.

---

### Option B — User-level (available in every project you open)

```bash
git clone https://github.com/erikwski/CLM.plugin /tmp/clm-plugin
cp -r /tmp/clm-plugin/skills "$HOME/.claude/skills"
```

The skills are now available globally in all your Claude Code sessions.

---

### Option C — Plugin marketplace (when `/plugin` commands are available)

If your Claude Code version supports the plugin marketplace:

```
/plugin marketplace add erikwski/CLM.plugin
/plugin install datacolor-skills@erikwski-CLM.plugin
```

---

### Keeping skills up to date

```bash
git -C /tmp/clm-plugin pull
cp -r /tmp/clm-plugin/skills .claude/skills   # or $HOME/.claude/skills for user-level
```

---

## How to use the PBI-to-Prompt skill

1. Open Claude Code in any project where the skills are installed.
2. Type `/datacolor-skills:pbi-to-prompt`.
3. Provide your PBI details when Claude asks:
   - **Title** — e.g. "Export report as PDF"
   - **Description** — the full backlog item body
   - **Acceptance Criteria** — the numbered or bulleted list of conditions
4. Claude returns a polished, self-contained prompt you can paste into a new conversation to start implementation.

---

## Adding new skills

1. Clone this repo.
2. Create `skills/<skill-name>/SKILL.md` — the folder name becomes the command suffix.
3. Add a `description` frontmatter field and write the instructions for Claude.
4. Open a PR against `main`.

### Skill file template

```markdown
---
name: my-skill
description: One sentence — what this skill does and when to use it.
---

Instructions for Claude go here.
Use $ARGUMENTS to capture anything the user types after the command name.
```

---

## Contributing

Open a PR against `main`. Keep each skill focused on a single task.
