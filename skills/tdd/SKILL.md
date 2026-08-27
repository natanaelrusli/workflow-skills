# TDD Skill

Red-green-refactor cycle for new functionality.

## Usage
/tdd [feature or function name]

## Cycle
1. **Red** — write a failing test for the smallest next behavior
2. **Green** — write the minimum code to make it pass, nothing more
3. **Refactor** — clean up without changing behavior; tests must still pass
4. Repeat until feature is complete

## Rules
- Run tests after every step — never move forward on a broken suite
- One failing test at a time; don't write tests ahead of the cycle
- Green means passing, not perfect — refactor is its own step
- If a test is hard to write, the design is wrong — redesign, don't hack the test
- Delete tests that no longer add coverage after refactoring

## Commands (run after each step)
Detect and use the project's test runner:
- Node/TS: `npm test` / `npx jest` / `npx vitest`
- Python: `pytest`
- Go: `go test ./...`
- Ruby: `bundle exec rspec`

## Output per iteration
```
[Red]   test: <what behavior the test checks>
[Green] impl: <what was written to pass>
[Refactor] changed: <what was cleaned up, if anything>
```

Stop and summarize when all acceptance criteria are covered by passing tests.
