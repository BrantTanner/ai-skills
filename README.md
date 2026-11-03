# AI Skills

My collection of reusable AI agent skills.

## Install on another device

Install Node.js 22.20 or later and Git, then run:

```sh
npx skills add BrantTanner/ai-skills
```

Choose the skills and coding agents when prompted. To install globally across projects:

```sh
npx skills add BrantTanner/ai-skills -g
```

This repository currently contains no skills. These commands will become useful once skills are uploaded.

## Add a skill

Store each skill in its own folder:

```text
skills/
  my-skill/
    SKILL.md
```

Each SKILL.md needs YAML frontmatter with a name and description, followed by the skill instructions. Include any scripts, references, and assets the skill needs in the same skill folder.

Installation uses the existing [skills CLI](https://github.com/vercel-labs/skills); no separate npm package is required.