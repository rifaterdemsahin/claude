# 🛠 Formula: PR Description Skill Showcase

This document showcases the `pr-description` agent skill, designed to standardize and automate the process of writing consistent, high-quality Pull Request descriptions.

## 🎯 Skill Goal
To ensure that all PRs have clear context, explaining the "what" and "why", along with a comprehensive list of changes, facilitating an easier review process.

## 📝 The Skill Definition

The skill is defined in `.gemini/skills/pr-description.md` and contains the following instructions:

```markdown
---
name: pr-description
description: Writes pull request descriptions. Use when creating a PR, writing a PR, or when the user asks to summarize changes for a pull request.
---

When writing a PR description:

1. Run `git diff main...HEAD` to see all changes on this branch
2. Write a description following this format:

## What
One sentence explaining what this PR does.

## Why
Brief context on why this change is needed

## Changes
- Bullet points of specific changes made
- Group related changes together
- Mention any files deleted or renamed
```

## 🚀 How to Use It
1. Once your code is ready, run your standard git commands.
2. Ask the agent to "write a PR description" or "summarize changes for a pull request".
3. The agent will automatically trigger this skill, check the diff, and structure the response exactly as dictated by the formula.

> [!TIP]
> This ensures that no matter who works on the repository, the PR structure remains uniform and clean!
