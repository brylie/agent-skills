# Contributing to agent-skills

Thank you for your interest in contributing skills to this repository! This guide will help you understand how to create and submit new Agent Skills.

## Before You Start

Please read the [Agent Skills specification](https://agentskills.io/specification) to understand the full format requirements and best practices. This guide covers repository-specific submission guidelines; the specification covers the skill format in detail.

## Skill Structure

Each skill is a directory containing at minimum a `SKILL.md` file:

```
skill-name/
└── SKILL.md          # Required
```

You can optionally include:
- `scripts/` - Executable code (Python, Bash, JavaScript, etc.)
- `references/` - Supporting documentation and reference materials
- `assets/` - Images, templates, and other static resources

## Creating a Skill

### 1. Directory Name

Use lowercase with hyphens (kebab-case):
- Good: `data-analysis`, `code-review`, `pdf-processing`
- Avoid: `DataAnalysis`, `code_review`, `-data-analysis`

### 2. SKILL.md File

Your `SKILL.md` file must include YAML frontmatter followed by Markdown content.

#### Minimal Example

```markdown
---
name: example-skill
description: Brief description of what this skill does and when to use it.
---

## Overview

Detailed instructions on how agents should use this skill.

## Usage

Step-by-step guidance for implementing the skill.
```

#### Frontmatter Fields

**Required:**
- `name` - Skill name (lowercase, hyphens only, no leading/trailing hyphens, max 64 characters)
- `description` - What the skill does and when to use it (max 1024 characters)

**Optional:**
- `license` - License reference (e.g., "Apache-2.0")
- `metadata` - Key-value mapping for additional info (author, version, etc.)
- `compatibility` - Environment requirements (e.g., "Requires Python 3.8+")
- `allowed-tools` - Space-delimited list of pre-approved tools (experimental)

See the [specification](https://agentskills.io/specification) for complete details and examples.

### 3. Body Content

Write clear, practical instructions that help agents perform the task:
- Explain what the skill does and why it's useful
- Provide step-by-step instructions
- Include concrete examples
- Document edge cases and limitations
- Keep the main SKILL.md under 5,000 tokens (roughly 500 lines)

Move detailed reference material to separate files in `references/`.

## Validation

Before submitting, validate your skill using the `skills-ref` tool:

```bash
skills-ref validate path/to/your-skill
```

This ensures your SKILL.md frontmatter is valid and follows all naming conventions.

## Submission Process

### 1. Fork and Branch

Fork the repository and create a branch with a descriptive name:
```bash
git checkout -b add-skill-your-skill-name
```

### 2. Add Your Skill

Create your skill directory under `skills/` with all necessary files.

### 3. Validate Locally

Run `skills-ref validate` to check your skill before committing.

### 4. Commit

Use conventional commit messages:
```bash
git commit -m "feat: add new skill for your-skill-name"
```

### 5. Push and Create Pull Request

Push your branch and create a pull request. In your PR description, include:
- What skill you're adding
- What it does and when it's useful
- How you tested it
- Any special considerations

## Pull Request Guidelines

- **One skill per PR** - Makes review and discussion clearer
- **Complete submission** - Include all documentation and examples
- **Pass validation** - Your skill must pass `skills-ref validate`
- **Clear description** - Help reviewers understand your skill's purpose and usage
- **No sensitive data** - Never include API keys, passwords, or personal information

## Code of Conduct

This project follows a Code of Conduct to ensure a welcoming environment for all contributors. Please be respectful and constructive in all interactions.

## Questions?

If you have questions about the skill format or need clarification, please:
1. Check the [Agent Skills specification](https://agentskills.io/specification)
2. Review existing skills in the `skills/` directory for examples
3. Open an issue to ask for help

Thank you for contributing!
