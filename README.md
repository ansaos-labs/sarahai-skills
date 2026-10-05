SarahAI Skills
==============

Skills for [SarahAI](https://github.com/ansaos-labs/sarahai).

A skill is a directory with a `SKILL.md` in it: YAML frontmatter (`name`,
`description`, `allowed-tools`) and a body of instructions. SarahAI lists the
skills it finds and loads a body into context only when you invoke it — so a
large library costs nothing until you actually use a skill from it.

## Install

Clone this repository to the place SarahAI looks for user skills:

```sh
git clone https://github.com/ansaos-labs/sarahai-skills ~/.sarahai/skills
```

SarahAI also reads `.sarahai/skills/` inside a workspace, which is where
project-specific skills belong. A project skill wins if the names clash.

## The skills

| Skill | What it does |
|---|---|
| `commit` | Reads the diff, stages the right files, writes a message about why |
| `review` | Reviews a diff for real defects — reports, changes nothing |
| `test-fix` | Runs the suite and fixes failures one at a time |
| `explain` | Reads a file or module and explains how it fits together |
| `refactor` | Restructures without changing behaviour, tests as the guard |
| `init` | Writes a `SARAH.md` describing how the project works |

## Using one

In a SarahAI session, as a slash command:

```
/commit
/review the changes on this branch
```

or by asking in words — the model has a `skill` tool and loads the skill itself
when the task matches.

## Writing your own

```
my-skill/
  SKILL.md
```

```markdown
---
name: my-skill
description: One line saying when to use this.
allowed-tools: [read_file, edit_file]
---

Instructions for the model.
```

`name` is what you type after the slash. `description` is what the model sees
when deciding whether to load the skill, so make it say *when* to use the skill,
not just what it is. `allowed-tools` is advisory: it tells the model what the
skill expects, but SarahAI's permission gate is still the gate.

## Licence

MIT — see `LICENSE`. These skills are original; nothing here is copied from
another project's skill collection.
