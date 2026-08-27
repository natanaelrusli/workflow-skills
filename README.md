# workflow-skills

Claude Code skills for day-to-day development workflow — commits, PRs, TDD, requirements, and unit test generation.

## Skills

| Command | Description |
|---|---|
| `/commit` | Generate a conventional commit message from staged changes |
| `/create-pr` | Push branch and open a structured pull request |
| `/gather-requirements` | Structured Q&A before implementation starts |
| `/gen-tests [file]` | Generate focused unit tests for existing code |
| `/tdd [feature]` | Red-green-refactor loop for new functionality |

## Installation

### Option A — Local (symlinks)

Clone the repo and symlink the skills directory into Claude Code's skill folder:

```bash
git clone https://github.com/natanaelrusli/workflow-skills.git ~/workflow-skills

for skill in commit create-pr gather-requirements gen-tests tdd; do
  ln -s ~/workflow-skills/skills/$skill ~/.claude/skills/$skill
done
```

Skills stay in sync with the repo — no re-copying needed.

### Option B — Plugin (via Claude Code marketplace)

Add this repo as a known marketplace in `~/.claude/settings.json`:

```json
"extraKnownMarketplaces": {
  "workflow-skills": {
    "source": {
      "source": "github",
      "repo": "natanaelrusli/workflow-skills"
    }
  }
}
```

Then install via Claude Code:

```
/plugin install workflow-skills@workflow-skills
```

## Skill Details

### `/commit`

Analyzes `git diff --staged` and generates a [Conventional Commits](https://www.conventionalcommits.org/) message.

```
feat(auth): add password reset functionality

- Add forgot password form
- Implement email verification flow
- Add password reset endpoint
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

---

### `/create-pr`

Diffs the current branch against `main`, pushes if needed, then opens a PR using `gh` with a structured body.

**PR body template:**
```markdown
## What
## Why
## Changes
## Testing
```

---

### `/gather-requirements`

Runs a structured Q&A covering scope, inputs/outputs, edge cases, constraints, and acceptance criteria — then produces a requirements summary before any implementation begins.

**Output:**
```
## Requirements: <feature name>

**Goal:** one sentence

**In scope:** ...
**Out of scope:** ...
**Acceptance criteria:**
- [ ] criterion
```

---

### `/gen-tests [file or function]`

Generates minimal unit tests for existing code, prioritized by failure risk:

1. Happy path
2. Boundary values (min, max, zero, empty, null)
3. Error cases
4. Integration points

Uses the test framework already in your project. No new dependencies added.

---

### `/tdd [feature]`

Runs the red-green-refactor cycle, reporting each iteration:

```
[Red]      test: <what behavior the test checks>
[Green]    impl: <what was written to pass>
[Refactor] changed: <what was cleaned up>
```

Detects your test runner automatically (`jest`, `vitest`, `pytest`, `go test`, `rspec`).

## Structure

```
workflow-skills/
  plugin.yaml
  plugin.json
  skills/
    commit/SKILL.md
    create-pr/SKILL.md
    gather-requirements/SKILL.md
    gen-tests/SKILL.md
    tdd/SKILL.md
```
