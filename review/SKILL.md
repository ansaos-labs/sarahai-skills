---
name: review
description: Review the current diff for bugs, not style. Reports findings, changes nothing.
allowed-tools: [run_command, read_file, glob, grep]
---

# Reviewing a change

Read `git diff` (or the range the user named) and look for defects that would
actually bite:

- Off-by-one errors, wrong comparison operators, inverted conditions.
- Unhandled failure paths: an error swallowed, a null dereferenced, a promise
  never awaited.
- Resource leaks: a file, socket or lock not released on the error path.
- Concurrency: shared state mutated without a guard.
- Boundaries: empty input, a single element, very large input.

Rules:

- Report only what you can point at, with file and line.
- Say what input or state makes it fail. If you cannot, it is not a finding.
- Do not report formatting, naming or taste.
- Do not change any file. This skill only reports.
