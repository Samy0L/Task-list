---
name: unit-tests
description: Writes and runs unit tests for the functions in js/ with node:test, following docs/testing.md. Use when the user asks for unit tests or changes a function in js/. A test bent to match the code hides the bug it should catch.
---

# Unit tests for js/

**Test the code as it is; never change it to make a test pass.**

Copy this checklist into your reply and tick it as you go:

- [ ] 1. Read docs/testing.md. No "Unit tests" section → propose the one
         below, wait for approval, write it there (back to 1).
- [ ] 2. Can each function be loaded in Node as it is: exported, and
         not touching document or window when the file loads?
         No → stop. Say which small change would make it testable;
         the human decides, and it goes in docs/decisions.md.
- [ ] 3. Write tests/unit/<file>.unit.js with node:test and
         node:assert/strict: the normal case, empty input, an edge case.
- [ ] 4. Run the command from docs/testing.md.
- [ ] 5. Report: passed, failed and what is not tested, and why. For
         each failure: the function, the input, expected, received.

The section for docs/testing.md:

    ## Unit tests
    - Tests live in tests/unit/, named <file>.unit.js, with node:test
      (built into Node: no dependency).
    - Run: node --test "tests/unit/*.unit.js"

Not *.test.js or *.spec.js: Playwright runs every file with those names.
