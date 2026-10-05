---
name: refactor
description: Restructure code without changing what it does.
allowed-tools: [read_file, edit_file, write_file, glob, grep, run_command]
---

# Refactoring

The contract: behaviour must not change. If it does, that is a bug fix, not a
refactor, and it belongs in a separate change.

1. Before touching anything, find the tests that cover this code. If there are
   none, say so and propose adding them first.
2. Run those tests and confirm they pass, so you have a baseline.
3. Make one structural change at a time.
4. After each change, re-run the tests.
5. If a test fails and you cannot explain why in one sentence, revert that step.

Do not rename public API, change signatures, or alter output formats unless the
user asked for it explicitly.
