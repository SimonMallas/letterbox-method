# The Letterbox Method

*How a team of agents — and one person — keep a memory that stays honest.*
Version 0.1, October 2026. Two pages; the kit does the rest.

---

## 1. The shape

Every message between agents — and every message from you, from your phone,
your menu bar, or a chat app — is a **letter**: addressed, dated, kept.
Letters are the record. The record is **append-only**: nothing is edited in
place, and a correction is a new letter that names what it replaces.

Over the record sit two things:

- **QEM** — the exact-answer machine. A read-only query over letter envelopes:
  *what's owed to me? which version stands? did that ever happen?* Answers are
  counted and scoped. An empty answer names where it looked — it is never
  dressed up as "no".
- **Notes** — the map. Each agent keeps quick-reference notes: decisions,
  reasons, preferences. Every factual claim cites the letter it rests on.
  Notes carry an as-of cursor so any reader can ask what the record has seen
  since. Notes are derived: safe to delete, cheap to rebuild, never the source
  of truth.

That's all of it. Letters, one exact query, honest notes.

## 2. The rules (the whole discipline)

1. **The old letter stays; a later letter says which stands; a note that
   disagrees gets fixed.** This is the rule people quote. Learn this one.
2. **Never rewritten; deleted only by tombstone.** If something must be
   removed (a pasted secret, someone's data), the content goes and a marker
   letter records who, when, why, and which id. Removal then walks every
   derived copy — notes, caches, indexes. A rebuild must never bring it back.
3. **Everything above the record is disposable.** Delete the notes, rebuild
   them from letters, lose nothing. If a layer can't survive that test, it
   doesn't belong above the record.
4. **State is computed, not copied.** If QEM can answer it ("what version
   shipped?"), don't write it in a note — notes hold what the record can't
   compute: why, not what.
5. **A scoped empty is not absence.** "I found nothing in this mailbox" is an
   honest answer. "That never happened" is not.
6. **The person is a seat, not a supervisor.** You write letters like anyone
   else. The record doesn't rank its authors.
7. **Never destroy work you didn't create.** No `git checkout`/`reset`/`clean`
   on changes of unknown provenance; no deleting anything you didn't write.
   If it might matter, preserve it first (a branch, a stash, a copy) — then
   test, then ask. A wrong revert of your own work costs a redo; a wrong
   revert of someone else's costs work you can't redo.

## 3. The habits

- **Session start**: register your surface, check your inbox, read what's
  unhandled. The letter is the message; the doorbell is only a knock.
- **Tasks**: acknowledge, work, report. A result cites the letters it rests
  on — letter ids, not memory.
- **Notes**: cite the letter, name the threads, carry the cursor. When the
  record moves past your cursor, refresh or rebuild.
- **Disagreement**: write the letter that says which stands. Silence is not
  consensus; absence of a dispute is not agreement.

## 4. Two machines, one rule

A second machine may copy letters in; it never rewrites one; every letter has
one home. Crossing machines is delivery with a receipt — not replication, not
consensus, not a new daemon. (The research on what more is possible lives
elsewhere; the kit ships this line and no more.)

## 5. The exit

The kit installs nothing you can't remove. Delete the derived layers — notes,
indexes, caches — and the record rebuilds them or doesn't miss them. The
letters remain, plain Markdown in plain folders, readable with `cat`.
If you walk away from every tool tomorrow, the record is still yours.

---

*The Method is a practice, not a package. The software it assumes is Agent
Letterbox (any edition) plus, for a person on a phone, Agent Letter Bridge.
The kit beside this document installs both.*
