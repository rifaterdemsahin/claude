# Claude Skills Formula

## What are Claude Skills?
Skills in Claude Code are reusable markdown files that teach Claude how to perform a specific task or adhere to a standard. Instead of repeating instructions (like coding standards, PR review formats, or commit message guidelines) in every conversation, you define them once as a Skill. Claude automatically matches your request against available skill descriptions and loads the relevant skill on-demand.

## Key Concepts
- **On-Demand Loading**: Unlike `claude.md` which loads into every conversation and consumes context, Skills only load their full instructions when their description matches the current task.
- **Automatic Execution**: Unlike slash commands which require you to manually invoke them, Skills apply automatically when Claude recognizes the situation.

## Skill Storage Locations
Depending on who needs the skill, you store them in different locations:

1. **Personal Skills (`~/.claude/skills`)**
   - Follow you across all your local projects.
   - Ideal for: Personal preferences, how you like code explained, your personal commit message style.
2. **Project Skills (`.claude/skills/` in repo root)**
   - Committed to version control; anyone who clones the repo gets them.
   - Ideal for: Team coding standards, brand guidelines, shared PR checklists, deployment instructions.

## How to Build a Skill
1. Create a new directory for your skill (e.g., `.claude/skills/pr_review/`).
2. Inside that directory, create a `skill.md` file.
3. Add a clear description at the top of the file. **Claude uses this description to decide whether to activate the skill.**
4. Write out the markdown instructions, resources, or scripts that define the skill.

## Example Use Cases
- Code review standards and checklists
- Consistent commit message formatting
- Design system and brand guidelines
- Troubleshooting procedures for specific services
