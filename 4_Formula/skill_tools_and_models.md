# 🛠 Configuring Allowed Tools and Models in Skills

## Overview
When creating skills for your AI agent, you can explicitly define **which tools** the skill is allowed to use and **which model** should execute the skill. This is done by adding a YAML frontmatter block at the very top of your `skill.md` file.

## The Frontmatter Configuration

Here is an example of how to configure a skill using frontmatter (based on `allowed-tools-model.png`):

```yaml
---
name: codebase-onboarding
description: Helps new developers understand how the system works.
allowed-tools: Read, Grep, Glob, Bash
model: sonnet
---
# Codebase Guide
[Your Markdown Instructions Here]
```

### 1. `allowed-tools`
The `allowed-tools` field restricts the AI agent to a specific set of capabilities when executing this skill.
- **Why use it?** It enforces security and prevents unintended actions. For example, if a skill is only meant to read and analyze code, you can restrict it to read-only tools (`Read`, `Grep`, `Glob`) and completely omit tools that modify files (`Write`, `Replace`).
- **Example Tools:** `Read`, `Grep`, `Glob`, `Bash`, `Write`, `Replace`.

### 2. `model`
The `model` field pins the skill to a specific AI model tier (e.g., `sonnet`, `haiku`, `opus`).
- **Why use it?** Pinning a model makes it incredibly easy to optimize for speed and cost without needing to manually toggle your global model settings. 
- **The Core Benefit:** For basic actions (like formatting code, checking syntax, or simple file reads), you can pin the skill to a faster, more cost-effective model. When the skill is triggered, the agent automatically switches to the designated model just for this task, saving you time and optimizing resources.

## Seamless Model Switching

Defining the `model` in the skill's frontmatter streamlines your workflow:
1. **Automated Delegation:** You don't need to stop your workflow to change settings. If you ask the agent to do a basic onboarding task, it seamlessly delegates that action to the pinned model (e.g., `sonnet`).
2. **Resource Efficiency:** You can run your main conversational session on your most powerful model, but offload basic, repetitive actions to faster models behind the scenes.
3. **Consistent Execution:** Ensures that specific, predictable tasks are always handled by the model best suited for them, guaranteeing consistent execution speed and cost every time the skill is activated.

## Summary
Using YAML frontmatter to define `allowed-tools` and `model` elevates your skills from simple text prompts to secure, auto-optimized mini-agents.
