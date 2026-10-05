---
name: explain
description: Explain what a file or module does, and how its parts fit together.
allowed-tools: [read_file, list_dir, glob, grep]
---

# Explaining code

1. Read the whole file, not just the part you were pointed at.
2. Trace what it depends on and what depends on it — `grep` for the exported
   names.
3. Answer in this order:
   - What problem does this solve, in one or two sentences?
   - What are the moving parts, and what does each own?
   - What is the flow through it for the common case?
   - What would surprise someone reading it for the first time?
4. Quote real line numbers. If you did not read it, do not describe it.

Change nothing.
