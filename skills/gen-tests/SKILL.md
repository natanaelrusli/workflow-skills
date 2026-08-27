# Generate Unit Tests Skill

Generate focused unit tests for existing code.

## Usage
/gen-tests [file or function]

## Behavior
1. Read the target file/function
2. Identify: happy path, edge cases, error cases, boundary values
3. Write minimal tests that cover real failure modes — no padding

## Test Writing Rules
- One assertion per test where possible
- Test names describe the scenario: `it("returns null when input is empty")`
- No mocking unless crossing a real boundary (network, DB, file system)
- Use the test framework already in the project — don't add new ones
- Delete tests that duplicate what another already covers

## Coverage Targets (in priority order)
1. Happy path — does it work at all?
2. Boundary values — min, max, zero, empty, null
3. Error cases — what should throw or return error?
4. Integration points — does it compose correctly with callers?

## Output
Write tests directly to the appropriate test file. If no test file exists, create one alongside the source file following the project's naming convention (`*.test.ts`, `*_test.go`, `test_*.py`, etc.).

Do not generate tests for trivial getters/setters or one-liners unless explicitly asked.
