---
name: commit
description: Review what changed, then stage and commit it with a message that explains why.
allowed-tools: [run_command, read_file, glob]
---

# Committing changes

1. Run `git status` and `git diff` (and `git diff --staged`) to see exactly what
   changed. Read the diff; do not guess from filenames.
2. If unrelated changes are mixed together, say so and ask whether to split them
   before committing anything.
3. Stage the files that belong to this change, by name. Avoid `git add -A`
   unless the user asked for everything.
4. Write the message about *why*, not *what* — the diff already says what.
   - First line: imperative, under 72 characters, no trailing period.
   - Then a blank line, then a short body if the reason is not obvious.
5. Run `git commit` with that message.
6. Report the commit hash and the first line.

Do not push unless the user asked you to.
