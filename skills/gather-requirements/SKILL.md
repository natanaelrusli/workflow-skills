# Gather Requirements Skill

Structured requirements gathering before starting implementation.

## Usage
/gather-requirements

## Behavior
1. Ask clarifying questions to understand the feature/change requested
2. Identify: scope, inputs/outputs, edge cases, constraints, acceptance criteria
3. Confirm understanding with a concise summary before proceeding

## Questions to Ask

### Scope
- What exactly needs to change or be built?
- What is explicitly out of scope?

### Users & Inputs
- Who uses this? What do they provide?
- What are valid vs. invalid inputs?

### Outputs & Side Effects
- What should happen on success?
- What should happen on failure or edge cases?

### Constraints
- Tech stack, performance, security, backwards-compat requirements?
- Any deadlines or dependencies?

### Acceptance Criteria
- How do we know it's done? What can we test?

## Output Format
After gathering, produce a short requirements summary:

```
## Requirements: <feature name>

**Goal:** one sentence

**In scope:**
- item

**Out of scope:**
- item

**Acceptance criteria:**
- [ ] criterion
```

Do not start implementation until requirements are confirmed.
