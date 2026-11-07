# The notes conventions (the map habit)

Notes are derived. They exist to be fast, not to be true — the letters are
true. These conventions keep the gap between them checkable.

## The note header

Every standing note carries four lines at the top:

```
as-of: <UTC time this note has read up to, e.g. 2026-11-01T12:00:00Z — an id here is reported as not-a-time by the tools>
threads: <the letter threads this note summarizes>
covers: <mailboxes/sources read — and what was skipped>
rule: the old letter stays; a later letter says which stands; a note that disagrees gets fixed
```

The `as-of` cursor makes staleness a query, not a judgment: *what landed in
these threads since this cursor?* is an exact question QEM answers.

## What goes in a note

- Decisions and their reasons ("we chose X because Y — letter abc123").
- Preferences and constraints ("the operator wants low-key notes — letter def456").
- Lessons with a **when-this-matters** trigger line ("before a push: …").

## What does NOT go in a note

- State QEM can compute ("what's open", "what shipped") — ask, don't copy.
- Anything without a letter behind it. A note claiming a fact with no letter
  id is a draft, not a fact.
- Copies of letter bodies. Cite the id; read the letter when you need it.

## Disagreement

When a note and a letter disagree: the letter wins, the note gets fixed, and
the fix is visible. When two letters disagree and nothing says which stands:
the disagreement is the state of the record — say so, don't pick quietly.

## Forget

When a tombstone letter lands, forget walks every derived copy — this note,
any index, any cache. A rebuild must never bring tombstoned content back.
