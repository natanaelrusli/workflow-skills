# Create PR Skill

Create a well-structured pull request for the current branch.

## Usage
/create-pr

## Behavior
1. Check current branch and diff vs. base branch
2. Summarize what changed and why
3. Push branch if not already pushed
4. Open PR with a clear title and description

## Steps
```bash
git diff main...HEAD --stat          # What changed
git log main...HEAD --oneline        # Commit history
git push -u origin <branch>          # Push if needed
gh pr create --title "..." --body "..."
```

## PR Title Format
`<type>: <short imperative description>` (max 72 chars)

Types: feat, fix, refactor, chore, docs, test

## PR Body Template
```markdown
## What
Brief description of what this PR does.

## Why
Context: why this change is needed.

## Changes
- specific change 1
- specific change 2

## Testing
How to verify this works.
```

## Rules
- Never force-push to main/master
- Never push if there are uncommitted changes — commit or stash first
- Set base branch to `main` unless the project uses a different default
- Do not add co-authors unless they contributed commits
