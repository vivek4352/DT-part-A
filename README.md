# Daily Reflection Tree

This is a deterministic reflection agent designed around 3 axes:
1. Locus (Victim vs Victor)
2. Orientation (Entitlement vs Contribution)
3. Radius (Self vs Others)

## Structure
- JSON-based tree
- Deterministic branching
- No LLM usage at runtime

## How to read
Each node contains:
- id
- parentId
- type
- options → branching logic