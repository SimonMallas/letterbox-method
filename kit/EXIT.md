# The exit path

Everything this kit builds above the record is disposable. Prove it once,
then trust it.

## Uninstall the derived layers

- Notes: delete them. They rebuild from letters, or weren't worth keeping.
- Indexes, caches, any query state: delete. They recompute.
- The registration: `letterbox` keeps a live-surface registry. The surface
  dies with the pane; the row stays until `letterbox <mux> unregister <you>`
  (or re-register on the new surface at next start).

## What remains

The letters. Plain Markdown, plain folders, readable with `cat`. They were
the only thing that mattered.

## The drill (run it once before you trust the setup)

1. Send yourself three letters; take notes that cite them.
2. Delete every note and every cache.
3. Rebuild the notes from the letters alone.
4. Compare: any fact in the new notes without a letter behind it was never
   honest — that's the Method catching you, and it's cheap to fix now.

If a letter was ever removed by hand (with its removal letter beside it),
run the drill against it too: the removed content must not come back from any
copy, snapshot, or cache. If it does, the setup fails here — not in
production.

## Three lines the first drill taught (28 Oct)

- **The record includes your own outbox.** Rebuild from inbox AND outbox
  letters — your replies are letters too. A rebuild that reads only what you
  received will conclude, wrongly, that your answers are lost.
- **Derived vs deliverable.** Delete only derived material: caches, indexes,
  summaries rebuildable from letters. Authored deliverables (a review, a
  draft, a running log) are not cache — letter them first or keep them.
  If it isn't reproducible from letters and it matters, it is a deliverable.
- **Instructions that matter are letters.** If the drill's own premise
  arrives in a terminal, the record can't reconstruct why you acted.
