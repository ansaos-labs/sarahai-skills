---
name: test-fix
description: Run the test suite, then fix the failures one at a time.
allowed-tools: [run_command, read_file, edit_file, glob, grep]
---

# Fixing failing tests

1. Find how tests are run in this project — read the manifest (`package.json`,
   `pyproject.toml`, `Cargo.toml`, `Makefile`) rather than guessing.
2. Run the suite and capture the failures.
3. Take one failure at a time:
   - Read the test to see what it actually asserts.
   - Read the code under test.
   - Decide whether the code or the test is wrong. Say which, and why.
   - Fix that one thing.
4. Re-run that single test. Then re-run the whole suite.
5. Stop and report if a failure looks like it needs a design decision rather
   than a fix.

Never delete or skip a test to make the suite pass.
