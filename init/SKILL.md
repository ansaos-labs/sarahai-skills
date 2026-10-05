---
name: init
description: Write a SARAH.md that tells the agent how this project works.
allowed-tools: [read_file, write_file, list_dir, glob, grep]
---

# Writing SARAH.md

Read the project before writing anything: the manifest, the README, the
directory layout, and how tests and builds are run.

Then write `SARAH.md` at the project root, covering:

- What this project is, in two sentences.
- How to build, test and lint it — the exact commands.
- The layout: which directories matter and what lives in each.
- Conventions that are not obvious from the code: naming, error handling,
  where new files go.
- Anything a newcomer gets wrong.

Keep it short. It is read at the start of every session, so every line costs
context. Do not restate what the code already says clearly.
